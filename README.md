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

--- a/arch/arm64/boot/dts/qcom/x1e80100-dell-inspirion-14-plus-7441.dts
+++ b/arch/arm64/boot/dts/qcom/x1e80100-dell-inspirion-14-plus-7441.dts
@@ -751,7 +751,7 @@ &cci1 {
 
 &cci1_i2c1 {
        camera@10 {
-               compatible = "ovti,ov02e10";
+               compatible = "ovti,ov02c10";
                reg = <0x10>;
 
                reset-gpios = <&tlmm 237 GPIO_ACTIVE_LOW>;
@@ -771,7 +771,8 @@ camera@10 {
                port {
                        ov02e10_ep: endpoint {
                                data-lanes = <1 2>;
-                               link-frequencies = /bits/ 64 <360000000>;
+                               //link-frequencies = /bits/ 64 <360000000>;
+                               link-frequencies = /bits/ 64 <400000000>;
                                remote-endpoint = <&csiphy4_ep>;
                        };
                };
diff --git a/drivers/media/i2c/ov02c10.c b/drivers/media/i2c/ov02c10.c
index 236623b26da0..23b2028c1228 100644
--- a/drivers/media/i2c/ov02c10.c
+++ b/drivers/media/i2c/ov02c10.c
@@ -19,7 +19,8 @@
 #define OV02C10_MCLK                   19200000
 #define OV02C10_RGB_DEPTH              10
 
-#define OV02C10_REG_CHIP_ID            CCI_REG16(0x300a)
+//#define OV02C10_REG_CHIP_ID          CCI_REG16(0x300a)
+#define OV02C10_REG_CHIP_ID            CCI_REG16(0)
 #define OV02C10_CHIP_ID                        0x5602
