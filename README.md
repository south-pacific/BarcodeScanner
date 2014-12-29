cordova-plugin-BarcodeScanner
=========

基于cordova插件形式开发的条形码、二维码扫描插件。


说明：
========
+ 该版本插件fork自[https://github.com/wildabeast/BarcodeScanner](https://github.com/wildabeast/BarcodeScanner)
+ 插件的功能和调用方式与原版本无异，具体可以参看原版本的说明。
+ android下对zxing重新编译打包，主要修改了扫描框的样式，增加开关闪关灯的功能。
+ ios下则进行了重写，不再使用原版本的代码，使用 AV Foundation framework 实现扫描功能，因此仅支持IOS7以上（包括IOS7）。

安装：
========
1. `cordova plugin add https://github.com/south-pacific/BarcodeScanner.git`
2. `cordova build android` 或者 `cordova build ios`
3. android修改报错信息，例如：xxx.xxx.R。

使用：
========
```javascript
   cordova.plugins.barcodeScanner.scan(
      function (result) {
          alert("We got a barcode\n" +
                "Result: " + result.text + "\n" +
                "Format: " + result.format + "\n" +
                "Cancelled: " + result.cancelled);
      }, 
      function (error) {
          alert("Scanning failed: " + error);
      }
   );
