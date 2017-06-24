<h1>Android QR generator with zxing library</h1>

<h3>Build.gradle file</h3>

```gradle
dependencies {
    ...
    compile 'com.google.zxing:core:3.2.1'
    compile 'com.journeyapps:zxing-android-embedded:3.2.0@aar'
    ...
}
```

<h3>Main.java</h3>

```java
MultiFormatWriter multiFormatWriter = new MultiFormatWriter();
try {
  BitMatrix bitMatrix = multiFormatWriter.encode(text2Qr, BarcodeFormat.QR_CODE,200,200);
  BarcodeEncoder barcodeEncoder = new BarcodeEncoder();
  Bitmap bitmap = barcodeEncoder.createBitmap(bitMatrix);
} catch (WriterException e) {
  e.printStackTrace();
}
```
