# SPDX-License-Identifier: Apache-2.0

cmake_minimum_required(VERSION 3.20.0)
list(APPEND BOARD_ROOT ${CMAKE_CURRENT_SOURCE_DIR})

# EZURIO SONA-IF513
set( FW_IMAGE_NAME ${CMAKE_CURRENT_LIST_DIR}/wifi-host-driver/COMPONENT_WIFI6/resources/firmware/COMPONENT_55500/COMPONENT_SM/55500A1.trxse )
set( NVRAM_IMAGE_NAME ${CMAKE_CURRENT_LIST_DIR}/wifi-host-driver/COMPONENT_WIFI6/resources/nvram/COMPONENT_55500/COMPONENT_SONA-IF513/Ezurio_IF513_NVRAM_Rev.0E_May-30.txt )
set( CLM_IMAGE_NAME ${CMAKE_CURRENT_LIST_DIR}/wifi-host-driver/COMPONENT_WIFI6/resources/clm/COMPONENT_55500/55500A1.clm_blob )

find_package(Zephyr REQUIRED HINTS $ENV{ZEPHYR_BASE})
project(wifi)

FILE(GLOB app_sources src/*.c)
target_sources(app PRIVATE ${app_sources})

zephyr_compile_definitions(BLHS_SUPPORT)

