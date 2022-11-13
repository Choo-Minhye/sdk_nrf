# nRF52840 ble value 전송 prj
p0.03 ADC Nordic ToolBox UART 로 값 전송 

## instructions
1. \examples\ble_peripheral\ble_app_uart\pca10056\s140\ses\ 로 가서 .emproject 열고,
2. main.c file 을 위 첨부된 main.c 로 변경 한다.(ctrl c + ctrl v)

## Merging BLE with ADC
sdk_config.h 로 가서 다음 항목을 변경해준다. 

1. nrf_drv_timer   TIMER_ENABLED 1 (0 to 1),
                   TIMER3_ENABLED 1 (0 to 1, 이하 생략)


2. nrfx_timer      NRFX_TIMER_ENABLED 1
                   NRFX_TIMER3_ENABLED 1


3. nrfx_ppi        NRFX_PPI_ENABLED 1


4. nrf_drv_ppi     PPI_ENABLED 1


5. nrf_drv_saadc   SAADC_ENABLED 1


6. nrfx_saadc      NRFX_SAADC_ENABLED 1


추가 한 라이브러리는 아래와 같다.
  nrf_drv_saadc.h , nrf_drv_timer.h , nrf_drv_ppi.h , nrfx_ppi.h , nrfx_timer.h , nrfx_saadc.h
따라서 해당 c 파일을 찾아서 첨가해주자


1.nrf_drv_ppi.c

2.nrfx_ppi.c

3.nrfx_timer.c

4.nrfx_saadc.c

