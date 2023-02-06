# Copyright (c) 2024 GARDENA GmbH
#
# SPDX-License-Identifier: Apache-2.0

zephyr_include_directories(si32Hal/SI32_Modules)

zephyr_sources_ifdef(CONFIG_SPI_SI32 si32Hal/SI32_Modules/SI32_SPI_A_Type.c)
zephyr_sources_ifdef(CONFIG_DMA_SI32 si32Hal/SI32_Modules/SI32_DMADESC_A_Type.c)

if(CONFIG_SOC_SERIES_SIM3U)
  zephyr_include_directories(si32Hal/sim3u1xx)
  zephyr_sources(si32Hal/sim3u1xx/SI32_PBCFG_A_Type.c)
  zephyr_sources_ifdef(CONFIG_DMA_SI32 si32Hal/sim3u1xx/SI32_DMAXBAR_A_Type.c)
endif()
