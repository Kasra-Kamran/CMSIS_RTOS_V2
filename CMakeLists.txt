if(NOT DEFINED CMSIS_DEVICE_HEADER_PATH)
message(FATAL_ERROR "CMSIS Device header path is not set.")
endif()


add_library(CMSIS_RTOS_V2
    Source/ARM/clib_arm.c
    Source/cmsis_os2.c
    Source/freertos_evr.c
    Source/os_systick.c)


target_include_directories(CMSIS_RTOS_V2 PUBLIC Include ${CMSIS_DEVICE_HEADER_PATH})

target_link_libraries(CMSIS_RTOS_V2 PRIVATE freertos_kernel stm32h5-cmsis)