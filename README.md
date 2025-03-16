windows: find . -name "*sensor*" -print | grep camera                                                                                                                    
./Windows/System32/drivers/DriverData/Qualcomm/fastRPC/persist/sensors/registry/registry/qsh_camera_ov08x_2.json.qsh_camera_ov08x_2.sensor_pwr_rail_info
./Windows/System32/drivers/DriverData/Qualcomm/fastRPC/persist/sensors/registry/registry/qsh_camera_ov08x_2.json.qsh_camera_ov08x_2.sensor_pwr_rail_info.vana
./Windows/System32/drivers/DriverData/Qualcomm/fastRPC/persist/sensors/registry/registry/qsh_camera_ov08x_2.json.qsh_camera_ov08x_2.sensor_pwr_rail_info.vana.ldo_pin
./Windows/System32/drivers/DriverData/Qualcomm/fastRPC/persist/sensors/registry/registry/qsh_camera_ov08x_2.json.qsh_camera_ov08x_2.sensor_pwr_rail_info.vio
./Windows/System32/drivers/DriverData/Qualcomm/fastRPC/persist/sensors/registry/registry/qsh_camera_ov02c10_2.json.qsh_camera_ov02c10_2.sensor_pwr_rail_info.vana.ldo_pin
./Windows/System32/drivers/DriverData/Qualcomm/fastRPC/persist/sensors/registry/registry/qsh_camera_ov02e_2.json.qsh_camera_ov02e_2.sensor_pwr_rail_info.vana
./Windows/System32/drivers/DriverData/Qualcomm/fastRPC/persist/sensors/registry/registry/qsh_camera_ov08x_2.json.qsh_camera_ov08x_2.sensor_pwr_rail_info.vio.ldo_pin
./Windows/System32/drivers/DriverData/Qualcomm/fastRPC/persist/sensors/registry/registry/qsh_camera_ov02c10_2.json.qsh_camera_ov02c10_2.sensor_pwr_rail_info
./Windows/System32/drivers/DriverData/Qualcomm/fastRPC/persist/sensors/registry/registry/qsh_camera_ov02c10_2.json.qsh_camera_ov02c10_2.sensor_pwr_rail_info.vana
./Windows/System32/drivers/DriverData/Qualcomm/fastRPC/persist/sensors/registry/registry/qsh_camera_ov02c10_2.json.qsh_camera_ov02c10_2.sensor_pwr_rail_info.vio
./Windows/System32/drivers/DriverData/Qualcomm/fastRPC/persist/sensors/registry/registry/qsh_camera_ov02c10_2.json.qsh_camera_ov02c10_2.sensor_pwr_rail_info.vio.ldo_pin
./Windows/System32/drivers/DriverData/Qualcomm/fastRPC/persist/sensors/registry/registry/qsh_camera_ov02e_2.json.qsh_camera_ov02e_2.sensor_pwr_rail_info
./Windows/System32/drivers/DriverData/Qualcomm/fastRPC/persist/sensors/registry/registry/qsh_camera_ov02e_2.json.qsh_camera_ov02e_2.sensor_pwr_rail_info.vana.ldo_pin
./Windows/System32/drivers/DriverData/Qualcomm/fastRPC/persist/sensors/registry/registry/qsh_camera_ov02e_2.json.qsh_camera_ov02e_2.sensor_pwr_rail_info.vio
./Windows/System32/drivers/DriverData/Qualcomm/fastRPC/persist/sensors/registry/registry/qsh_camera_ov02e_2.json.qsh_camera_ov02e_2.sensor_pwr_rail_info.vio.ldo_pin

~: dmesg | grep ov02c10
[   16.857928] ov02c10 10-0010: chip id mismatch: 5602!=256
[   16.864399] ov02c10 10-0010: failed to find sensor: -6
