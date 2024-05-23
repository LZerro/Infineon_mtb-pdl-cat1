from building import *
import rtconfig
Import('RTT_ROOT')

# get current directory
cwd = GetCurrentDir()
src = []
path = []

# The set of source files associated with this SConscript file.
src = Split('''
            drivers/source/cy_sysclk.c
            drivers/source/cy_sysclk_v2.c
            drivers/source/cy_systick.c
            drivers/source/cy_gpio.c
            drivers/source/cy_sysint.c
            drivers/source/cy_syslib.c
            drivers/source/cy_scb_i2c.c
            drivers/source/cy_syspm.c
            drivers/source/cy_syspm_v3.c
            drivers/source/cy_mcwdt.c
            drivers/source/cy_ipc_pipe.c
            drivers/source/cy_ipc_sema.c
            drivers/source/cy_ipc_drv.c
            drivers/source/cy_trigmux.c
            drivers/source/cy_prot.c
            drivers/source/cy_wdt_b.c
            drivers/source/cy_mcwdt_b.c
            drivers/source/cy_scb_common.c
            ''')


if GetDepend(['SOC_CY8C624ABZI_S2D44']):
    src += ['devices/COMPONENT_CAT1A/source/cy_device.c']

if GetDepend(['SOC_CY8C6245LQI_S3D72']):
    src += ['devices/COMPONENT_CAT1A/source/cy_device.c']

if GetDepend(['SOC_CY8C624ALQI_S2D42']):
    src += ['devices/COMPONENT_CAT1A/source/cy_device.c']

if GetDepend(['SOC_CY8C6247BZI_D54']):
    src += ['devices/COMPONENT_CAT1A/source/cy_device.c']

if GetDepend(['SOC_CY8C6347BZI_BLD53']):
    src += ['devices/COMPONENT_CAT1A/source/cy_device.c']

if GetDepend(['SOC_CY8C6244LQI_S4D92']):
    src += ['devices/COMPONENT_CAT1A/source/cy_device.c']

if GetDepend(['SOC_XMC7200D_E272K8384AA']):
    src += ['devices/COMPONENT_CAT1C/source/cy_device.c']

if GetDepend(['RT_USING_SERIAL']):
    src += ['drivers/source/cy_dma.c']
    src += ['drivers/source/cy_dmac.c']
    src += ['drivers/source/cy_scb_uart.c']

if GetDepend(['RT_USING_ADC']):
    if not GetDepend(['RT_USING_ADC']):
        src += ['drivers/source/cy_dma.c']
        src += ['drivers/source/cy_dmac.c']
    src += ['drivers/source/cy_sar.c']
    src += ['drivers/source/cy_sysanalog.c']

if GetDepend(['RT_USING_SDIO']) or GetDepend(['BSP_USING_CYW43012_WIFI']):
    src += ['drivers/source/cy_sd_host.c']

if GetDepend(['RT_USING_PWM']):
    src += ['drivers/source/cy_tcpwm_pwm.c']
    if not GetDepend(['RT_USING_HWTIMER']):
        src += ['drivers/source/cy_tcpwm_counter.c']

if GetDepend(['RT_USING_SPI']):
    src += ['drivers/source/cy_scb_spi.c']

if GetDepend('BSP_USING_RTC'):
    src += ['drivers/source/cy_rtc.c']

if GetDepend('BSP_USING_ON_CHIP_FLASH') or GetDepend('BSP_USING_CYW43012_BT') :
    src += ['drivers/source/cy_flash.c']

if GetDepend(['BSP_USING_SLIDER']):
    src += ['drivers/source/cy_csd.c']

if GetDepend(['RT_USING_WDT']):
    src += ['drivers/source/cy_wdt.c']

if GetDepend(['RT_USING_HWTIMER']):
    src += ['drivers/source/cy_tcpwm_counter.c']

path = [cwd + '/drivers/include',
        cwd + '/drivers/third_party/ethernet/include']

if GetDepend(['SOC_CY8C624ABZI_S2D44']):
    path += [cwd + '/devices/COMPONENT_CAT1A/include']
    path += [cwd + '/devices/COMPONENT_CAT1A/include/ip']

if GetDepend(['SOC_CY8C6245LQI_S3D72']):
    path += [cwd + '/devices/COMPONENT_CAT1A/include']
    path += [cwd + '/devices/COMPONENT_CAT1A/include/ip']

if GetDepend(['SOC_CY8C624ALQI_S2D42']):
    path += [cwd + '/devices/COMPONENT_CAT1A/include']
    path += [cwd + '/devices/COMPONENT_CAT1A/include/ip']

if GetDepend(['SOC_CY8C6247BZI_D54']):
    path += [cwd + '/devices/COMPONENT_CAT1A/include']
    path += [cwd + '/devices/COMPONENT_CAT1A/include/ip']

if GetDepend(['SOC_CY8C6347BZI_BLD53']):
    path += [cwd + '/devices/COMPONENT_CAT1A/include']
    path += [cwd + '/devices/COMPONENT_CAT1A/include/ip']

if GetDepend(['SOC_CY8C6244LQI_S4D92']):
    path += [cwd + '/devices/COMPONENT_CAT1A/include']
    path += [cwd + '/devices/COMPONENT_CAT1A/include/ip']

if GetDepend(['SOC_XMC7200D_E272K8384AA']):
    path += [cwd + '/devices/COMPONENT_CAT1C/include']
    path += [cwd + '/devices/COMPONENT_CAT1C/include/ip']

group = DefineGroup('Libraries', src, depend=[''], CPPPATH=path)
