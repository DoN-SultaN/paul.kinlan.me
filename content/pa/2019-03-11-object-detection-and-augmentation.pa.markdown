---
slug: object-detection-and-augmentation
date: 2019-03-11T20:32:18.307Z
title: 'Object Detection and Augmentation'
link: 'https://github.com/jeeliz/jeelizFaceFilter/blob/master/README.md#features'
tags: [links, qrcode, shapedetection]
---
ਮੈਂ Chrome ਵਿੱਚ [Shape Detection API](https://paul.kinlan.me/face-detection/ https://paul.kinlan.me/barcode-detection/ https://paul.kinlan.me/detecting-text-in-an-image/) ਵਿੱਚ ਬਹੁਤ ਜਿਆਦਾ ਖੇਡ ਰਿਹਾ ਹਾਂ ਅਤੇ ਮੈਨੂੰ ਇਸ ਦੀ ਸੰਭਾਵਨਾ ਬਹੁਤ ਪਸੰਦ ਹੈ, ਉਦਾਹਰਨ ਲਈ ਇੱਕ ਬਹੁਤ ਹੀ ਸਧਾਰਨ [QRCode detector](https://qrsnapper.com) ਮੈਂ ਬਹੁਤ ਲੰਮਾ ਸਮਾਂ ਪਹਿਲਾਂ ਲਿਖਿਆ ਸੀ, ਇੱਕ JS ਪੋਲੀਫਿਲ ਹੈ, ਪਰ ਇਹ ਉਪਲਬਧ ਹੋਣ ਤੇ `new BarcodeDetector()` API ਦੀ ਵਰਤੋਂ ਕਰਦਾ ਹੈ

ਤੁਸੀਂ ਆਕ੍ਰਿਤੀ ਖੋਜ API ਦੀ ਦੂਜੀ ਸਮਰੱਥਾਵਾਂ ਦੀ ਵਰਤੋਂ ਕਰਦੇ ਹੋਏ ਇੱਥੇ ਬਣਾਏ ਗਏ ਕੁਝ ਹੋਰ ਡੈਮੋ ਦੇਖ ਸਕਦੇ ਹੋ: [Face Detection](https://paul.kinlan.me/face-detection/) , [Barcode Detection](https://paul.kinlan.me/barcode-detection/) ਅਤੇ [Text Detection](https://paul.kinlan.me/detecting-text-in-an-image/)

ਜਦੋਂ ਮੈਂ ਹਫ਼ਤੇ ਦੇ ਅੰਤ ਵਿੱਚ [Jeeliz](https://jeeliz.com) ਭਰ ਵਿੱਚ ਠੋਕਰ ਖਾ ਰਿਹਾ ਸੀ ਤਾਂ ਮੈਂ ਖੁਸ਼ੀ ਵਿੱਚ ਹੈਰਾਨ ਸੀ ਅਤੇ ਮੈਂ ਉਨ੍ਹਾਂ ਦੇ ਟੂਲਕਿੱਟ ਦੇ ਪ੍ਰਦਰਸ਼ਨ ਤੋਂ ਪ੍ਰਭਾਵਿਤ ਹੋ ਗਿਆ- ਮੈਨੂੰ ਇੱਕ ਪਿਕਸਲ 3 ਐਕਸਐਲ ਦੀ ਵਰਤੋਂ ਕਰ ਰਿਹਾ ਸੀ, ਪਰ ਚਿਹਰੇ ਦੀ ਪਛਾਣ `FaceDetector` API ਦੇ ਨਾਲ ਸੰਭਵ `FaceDetector` ਤੋਂ ਬਹੁਤ ਤੇਜ਼ ਲੱਗ ਰਿਹਾ ਸੀ.

[Checkout some of their demos](https://jeeliz.com/sunglasses)

<figure>
  <img src="/images/2019-03-11-object-detection-and-augmentation.jpeg">
</figure>

ਇਹ ਮੈਨੂੰ ਬਹੁਤ ਸੋਚਣ ਲੱਗਾ. ਆਬਜੈਕਟ ਖੋਜ ਲਈ ਇਹ ਟੂਲਕਿੱਟ (ਅਤੇ ਇਸ ਦੀ ਤਰਾਂ ਦੇ) ਐਪੀਆਈ ਦਾ ਇਸਤੇਮਾਲ ਕਰਦੇ ਹਨ ਜੋ ਖਾਸਤੌਰ ਤੇ ਕੈਮਰਾ ਐਕਸੈਸ, ਵੈਬਜੀਐਲ ਅਤੇ WASM ਤੇ ਉਪਲਬਧ ਹੈ, ਜੋ ਕਿ Chrome ਦੀ ਸ਼ੈੱਲ ਖੋਜ API ਤੋਂ ਉਲਟ ਹੈ (ਜੋ ਕਿ ਸਿਰਫ Chrome ਵਿੱਚ ਹੈ ਅਤੇ ਸਾਰੇ ਪਲੇਟਫਾਰਮਾਂ ਤੇ ਅਨੁਕੂਲ ਨਹੀਂ ਹੈ ਜੋ Chrome ਚਾਲੂ ਹੈ ) ਨੂੰ ਆਸਾਨੀ ਨਾਲ ਅਮੀਰ ਅਨੁਭਵ ਆਸਾਨੀ ਨਾਲ ਬਣਾਉਣ ਅਤੇ ਅਰਬਾਂ ਹੀ ਉਪਭੋਗਤਾਵਾਂ ਤੱਕ ਪਹੁੰਚਣ ਲਈ ਵਰਤਿਆ ਜਾ ਸਕਦਾ ਹੈ ਜੋ ਸਾਰੇ ਪਲੇਟਫਾਰਮ ਵਿੱਚ ਇਕਸਾਰ ਤਜ਼ਰਬੇ ਵਾਲਾ ਹੈ.

ਵਾਧਾ ਜਿੱਥੇ ਇਹ ਦਿਲਚਸਪ ਹੁੰਦਾ ਹੈ (ਅਤੇ ਅਸਲ ਵਿੱਚ ਜੋ ਮੈਂ ਇਸ ਪੋਸਟ ਵਿੱਚ ਦਿਖਾਉਣਾ ਚਾਹੁੰਦਾ ਸੀ) ਅਤੇ ਜਿੱਥੇ ਤੁਹਾਨੂੰ ਮਿਡਲਵੇਅਰ ਲਾਇਬਰੇਰੀਆਂ ਦੀ ਲੋੜ ਹੈ ਜੋ ਹੁਣ ਪਲੇਟਫਾਰਮ ਵਿੱਚ ਆ ਰਹੇ ਹਨ, ਅਸੀਂ ਉਪਯੋਗਕਰਤਾਵਾਂ ਨੂੰ ਮਾਸਿਕ ਐਪਸ ਇੰਸਟਾਲ ਕਰਨ ਤੋਂ ਬਿਨਾਂ ਮਜ਼ੇਦਾਰ ਸਪੈਨਿਪਟ-ਏਕਸਕ ਫੇਸ ਐਲੀਮੈਂਟ ਐਪ ਬਣਾ ਸਕਦੇ ਹਾਂ ਜੋ ਕਿ ਉਪਭੋਗਤਾ ਡਿਵਾਈਸ ਤੋਂ ਵੱਡੀ ਮਾਤਰਾ ਵਿੱਚ ਕਣਕ ਇਕੱਠੀ ਕਰਦੇ ਹਨ (ਕਿਉਂਕਿ ਸਿਸਟਮ ਲਈ ਕੋਈ ਅੰਦਰੂਨੀ ਪਹੁੰਚ ਨਹੀਂ ਹੈ).

ਮਜ਼ੇਦਾਰ ਡੈਮੋ ਦੇ ਬਾਹਰ, ਉਪਭੋਗਤਾ ਲਈ ਛੇਤੀ ਅਤੇ ਬਸ, ਬਹੁਤ ਹੀ ਵਧੀਆ ਵਰਤੋਂ ਵਾਲੇ ਕੇਸਾਂ ਨੂੰ ਹੱਲ ਕਰਨਾ ਸੰਭਵ ਹੈ, ਜਿਵੇਂ ਕਿ:

* ਸਿੱਧਾ ਚੋਣਕਾਰ ਕੈਮਰੇ ਤੋਂ ਜਾਂ ਉਪਭੋਗਤਾ ਤੋਂ ਫੋਟੋ
* ਕੈਮਰੇ ਤੋਂ ਭਾਸ਼ਾਵਾਂ ਦੀ ਲਾਈਵ ਅਨੁਵਾਦ
* ਇਨਲਾਈਨ QRCode ਖੋਜ, ਇਸ ਲਈ ਲੋਕ ਹਰ ਵੇਲੇ WeChat ਨੂੰ ਖੋਲ੍ਹਣਾ ਨਹੀਂ ਚਾਹੁੰਦੇ :)
* ਕਿਸੇ ਚਿੱਤਰ ਤੋਂ ਆਟੋ ਐਕਸਟਰੈਕਟ ਵੈਬਸਾਈਟ URL ਜਾਂ ਐਡਰੈੱਸ
* ਕ੍ਰੈਡਿਟ ਕਾਰਡ ਦੀ ਪਛਾਣ ਅਤੇ ਨੰਬਰ ਕੱਢਣਾ (ਜਲਦੀ ਨਾਲ ਆਪਣੀ ਸਾਈਟ ਤੇ ਉਪਭੋਗਤਾਵਾਂ ਨੂੰ ਸਾਈਨ ਇਨ ਕਰੋ)
* ਤੁਹਾਡੇ ਸਟੋਰ ਦੇ ਵੈਬ ਐਪ ਵਿੱਚ ਵਿਜ਼ੁਅਲ ਉਤਪਾਦ ਖੋਜ
* ਤੁਹਾਡੇ ਸਟੋਰ ਵੈਬ ਐਪ ਵਿੱਚ ਹੋਰ ਉਤਪਾਦਾਂ ਦੇ ਵੇਰਵੇ ਲਈ ਬਾਰਕੌਂਡ ਖੋਜ.
* ਲੋਕਾਂ ਦੇ ਚਿਹਰੇ &#39;ਤੇ ਪ੍ਰੋਫਾਈਲ ਫੋਟੋਆਂ ਨੂੰ ਤੇਜ਼ ਕਰਨਾ
* ਸਧਾਰਣ ਏ.ਏ.ਏ.ਏ.ਈ.ਆਈ. ਵਿਸ਼ੇਸ਼ਤਾ ਹੈ ਕਿ ਇੱਕ ਚਿੱਤਰ ਨੂੰ ਚਿੱਤਰਾਂ ਵਿੱਚ ਪਾਇਆ ਗਿਆ ਟੈਕਸਟ ਸੁਣਨਾ ਹੋਵੇ.

ਮੈਂ ਇਨ੍ਹਾਂ ਵਰਤਣ ਵਾਲੇ ਕੇਸਾਂ ਬਾਰੇ 5 ਮਿੰਟ ਬਿਤਾਉਂਦਾ ਹਾਂ - ਮੈਂ ਜਾਣਦਾ ਹਾਂ ਕਿ ਇੱਥੇ ਹੋਰ ਬਹੁਤ ਕੁਝ ਹਨ - ਪਰ ਇਸ ਨੇ ਮੈਨੂੰ ਮਾਰਿਆ ਹੈ ਕਿ ਸਾਨੂੰ ਕੈਮਰੇ ਦੀ ਵਰਤੋਂ ਕਰਨ ਵਾਲੀਆਂ ਬਹੁਤ ਸਾਰੀਆਂ ਸਾਈਟਾਂ ਜਾਂ ਵੈਬ ਐਪਲੀਕੇਸ਼ਨ ਨਹੀਂ ਮਿਲਦੀਆਂ, ਸਗੋਂ ਅਸੀਂ ਉਹਨਾਂ ਤੋਂ ਪੁੱਛਣ ਵਾਲੀਆਂ ਬਹੁਤ ਸਾਰੀਆਂ ਸਾਈਟਾਂ ਦੇਖਦੇ ਹਾਂ ਉਪਭੋਗਤਾ ਕਿਸੇ ਐਪ ਨੂੰ ਡਾਉਨਲੋਡ ਕਰਦੇ ਹਨ, ਅਤੇ ਮੈਨੂੰ ਨਹੀਂ ਲਗਦਾ ਕਿ ਸਾਨੂੰ ਅਜਿਹਾ ਕਰਨ ਦੀ ਜ਼ਰੂਰਤ ਹੈ ਤਾਂ ਕਿ ਹੋਰ ਵੀ.

** ਅੱਪਡੇਟ ** ਸਾਡੀ ਟੀਮ &#39;ਤੇ ਥਾਮਸ ਸਟੇਨਨਰ ਸਾਡੀ ਟੀਮ ਵਿਚ ਵਰਣਿਤ ਹੈ ਕਿ ਇਹ ਆਵਾਜ਼ ਲਗਦਾ ਹੈ ਕਿ ਮੈਨੂੰ ਮੌਜੂਦਾ `ShapeDetection` API ਨਹੀਂ ਪਸੰਦ ਹੈ. ਮੈਂ ਇਸ ਤੱਥ ਤੋਂ ਪਸੰਦ ਕਰਦਾ ਹਾਂ ਕਿ ਇਹ API ਸਾਨੂੰ ਹਰੇਕ ਪ੍ਰਣਾਲੀ ਦੇ ਮੂਲ ਸ਼ਿਪਿੰਗ ਲਾਗੂ ਕਰਨ ਦੀ ਪਹੁੰਚ ਦਿੰਦਾ ਹੈ, ਹਾਲਾਂਕਿ ਜਿਵੇਂ ਕਿ ਮੈਂ [The Lumpy Web](/the-lumpy-web/) ਵਿੱਚ ਲਿਖਿਆ ਸੀ, ਵੈਬ ਡਿਵੈਲਪਰ ਪਲੇਟਫਾਰਮ ਵਿੱਚ ਇਕਸਾਰਤਾ ਦੀ ਲਾਲਸਾ ਕਰਦੇ ਹਨ ਅਤੇ [The Lumpy Web](/the-lumpy-web/) ਡਿਟੈਕਸ਼ਨ API ਦੇ ਨਾਲ ਕਈ ਮੁੱਦੇ ਹਨ ਜੋ ਦਾ ਸਾਰ:

1. API ਕੇਵਲ Chrome ਵਿੱਚ ਹੈ
2. Chrome ਵਿੱਚ API ਹਰ ਪਲੇਟਫਾਰਮਾਂ ਤੇ ਬਹੁਤ ਵੱਖਰੀ ਹੈ ਕਿਉਂਕਿ ਉਹਨਾਂ ਦੇ ਅੰਡਰਲਾਈੰਗ ਸਥਾਪਨ ਵੱਖ-ਵੱਖ ਹਨ. ਐਂਡਰੌਇਡ ਸਿਰਫ ਅਜਿਹੇ ਮਾਰਕਸ ਅਤੇ ਅੱਖਾਂ ਜਿਹੇ ਸਥਾਨਾਂ ਲਈ ਪੁਆਇੰਟਸ ਹੈ ਜਿੱਥੇ ਮੈਕੌਸ ਦੀ ਰੂਪ ਰੇਖਾ ਹੈ. ਐਂਡਰੌਇਡ ਤੇ `TextDetector` ਖੋਜੇ ਗਏ ਪਾਠ ਨੂੰ ਵਾਪਸ ਦਿੰਦਾ ਹੈ, ਜਿੱਥੇ ਮੈਕੌਸ ਤੇ &#39;ਪਾਠ ਮੌਜੂਦਗੀ&#39; ਸੂਚਕ ਦਿੰਦੀ ਹੈ ... ਇਹ ਸੁਰਮਾ ਦੇ ਸਾਰੇ ਬੱਗ ਦਾ ਜ਼ਿਕਰ ਕਰਨਾ ਨਹੀਂ ਹੈ.

ਵੰਡਣ ਲਈ ਇੱਕ ਪਲੇਟਫਾਰਮ ਵਜੋਂ ਵੈਬ, ਅਜਿਹੇ ਤਜਰਬਿਆਂ ਲਈ ਬਹੁਤ ਭਾਵ ਰੱਖਦਾ ਹੈ ਜਿਵੇਂ ਕਿ ਮੈਂ ਸੋਚਦਾ ਹਾਂ ਕਿ ਇਹ ਸਾਡੇ ਤੋਂ ਦੂਰ ਨਹੀਂ ਹੋਵੇਗਾ, ਪਰ ਮੁੱਦਿਆਂ ਦੇ ਉਪਰੋਕਤ ਦੋ ਸਮੂਹਾਂ ਵਿੱਚ ਮੈਨੂੰ ਹਰ ਫੀਚਰ ਨੂੰ ਲਾਗੂ ਕਰਨ ਲਈ ਲੰਮੇ ਸਮੇਂ ਦੀ ਲੋੜ &#39;ਤੇ ਸਵਾਲ ਕਰਨਾ ਚਾਹੀਦਾ ਹੈ. ਵੈਬ ਪਲੇਟਫਾਰਮ ਮੂਲ ਰੂਪ ਵਿੱਚ, ਜਦੋਂ ਅਸੀਂ ਅਜਿਹੇ ਪੈਕੇਜ ਵਿੱਚ ਵਧੀਆ ਹੱਲ ਕੱਢ ਸਕਦੇ ਹਾਂ ਜੋ ਅੱਜ ਪਲੇਟਫਾਰਮ ਦੀਆਂ ਵਿਸ਼ੇਸ਼ਤਾਵਾਂ ਜਿਵੇਂ ਵਾਈਜੀਜੀਐਲ, WASM ਅਤੇ ਭਵਿੱਖ ਵਿੱਚ ਵੈਬ GPU ਵਿੱਚ ਭੇਜੇ ਜਾਂਦੇ ਹਨ.

ਕਿਸੇ ਵੀ ਤਰ੍ਹਾਂ, ਮੈਨੂੰ ਇਹ ਤੱਥ ਬਹੁਤ ਪਸੰਦ ਹੈ ਕਿ ਅਸੀਂ ਇਸ ਨੂੰ ਵੈਬ ਤੇ ਕਰ ਸਕਦੇ ਹਾਂ ਅਤੇ ਮੈਂ ਉਨ੍ਹਾਂ ਨਾਲ ਸਾਈਟਾਂ ਨੂੰ ਸਮੁੰਦਰੀ ਵੇਖਣ ਲਈ ਅੱਗੇ ਵੇਖ ਰਿਹਾ ਹਾਂ.