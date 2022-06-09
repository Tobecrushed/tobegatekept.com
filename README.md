<!DOCTYPE html>
<html lang="ja">
  <head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <title>webcam │ sketch of three.js</title>
    <meta name="viewport" content="width=device-width,initial-scale=1,maximum-scale=1,minimum-scale=1">
    <meta name="description" content="play an image from a webcam with a fragment shader.">
    <meta name="keywords" content="undefined, Yoichi Kobayashi, WebGL, three.js">
    <meta name="theme-color" content="#111111">
    <meta name="msapplication-TileImage" content="/sketch-threejs/img/common/ms_tileimage.png">
    <meta name="msapplication-TileColor" content="#111111">
    <link rel="shortcut icon" href="/sketch-threejs/img/common/icon.ico">
    <link rel="apple-touch-icon" sizes="180x180" href="/sketch-threejs/img/common/app_icon.png">
    <link rel="stylesheet" href="/sketch-threejs/css/main.min.css">
    <meta property="og:title" content="webcam │ sketch of three.js">
    <meta property="og:site_name">
    <meta property="og:type" content="website">
    <meta property="og:description" content="play an image from a webcam with a fragment shader.">
    <meta property="og:url" content="http://ykob.github.io/sketch-threejs/sketch/webcam.html">
    <meta property="og:image" content="http://ykob.github.io/sketch-threejs/img/common/ogp_webcam.jpg">
    <meta name="twitter:card" content="summary_large_image">
    <meta name="twitter:title" content="webcam │ sketch of three.js">
    <meta name="twitter:description" content="play an image from a webcam with a fragment shader.">
    <meta name="twitter:image" content="http://ykob.github.io/sketch-threejs/img/common/ogp_webcam.jpg">
  </head>
  <body>
    <div class="l-page l-page--black" data-id="webcam">
      <div class="p-website-outline">
        <h1 class="p-website-outline__title"><a class="c-text-link" href="../" target=""><span class="c-text-link__label">sketch of three.js</span><span class="c-text-link__bg c-text-link__bg--black"></span></a>
        </h1>
        <p class="p-website-outline__description">created by <a class="c-text-link" href="http://www.tplh.net/" target="_blank"><span class="c-text-link__label">yoichi kobayashi.</span><span class="c-text-link__bg c-text-link__bg--black"></span></a>
        </p>
        <div class="p-website-outline__links"><a class="p-website-outline__link" href="https://github.com/ykob/sketch-threejs/" target="_blank">
            <svg width="24" height="23.411042944785276" viewBox="0 0 32.6 31.8">
              <path d="M16.3 0C7.3 0 0 7.3 0 16.3c0 7.2 4.7 13.3 11.1 15.5.8.1 1.1-.4 1.1-.8v-2.8c-4.5 1-5.5-2.2-5.5-2.2-.7-1.9-1.8-2.4-1.8-2.4-1.5-1 .1-1 .1-1 1.6.1 2.5 1.7 2.5 1.7 1.5 2.5 3.8 1.8 4.7 1.4.1-1.1.6-1.8 1-2.2-3.6-.4-7.4-1.8-7.4-8.1 0-1.8.6-3.2 1.7-4.4-.1-.3-.7-2 .2-4.2 0 0 1.4-.4 4.5 1.7 1.3-.4 2.7-.5 4.1-.5 1.4 0 2.8.2 4.1.5 3.1-2.1 4.5-1.7 4.5-1.7.9 2.2.3 3.9.2 4.3 1 1.1 1.7 2.6 1.7 4.4 0 6.3-3.8 7.6-7.4 8 .6.5 1.1 1.5 1.1 3V31c0 .4.3.9 1.1.8 6.5-2.2 11.1-8.3 11.1-15.5C32.6 7.3 25.3 0 16.3 0z"></path>
            </svg></a><a class="p-website-outline__link" href="https://twitter.com/ykob0123" target="_blank">
            <svg width="24" height="19.4976" viewBox="0 0 250 203.1">
              <path d="M78.6 203.1c94.3 0 145.9-78.2 145.9-145.9 0-2.2 0-4.4-.1-6.6 10-7.3 18.7-16.3 25.6-26.5-9.4 4.1-19.3 6.9-29.5 8.1 10.7-6.4 18.7-16.5 22.5-28.4-10.1 6-21.1 10.2-32.6 12.4C191-4.5 158.5-5.5 137.8 14c-13.3 12.5-19 31.2-14.8 49C81.9 60.9 43.4 41.4 17.4 9.4 3.8 32.8 10.7 62.8 33.3 77.8c-8.2-.2-16.1-2.4-23.3-6.4v.6c0 24.4 17.2 45.4 41.2 50.3-7.6 2.1-15.5 2.4-23.2.9 6.7 20.9 26 35.2 47.9 35.6-18.2 14.3-40.6 22-63.7 22-4.1 0-8.2-.3-12.2-.7 23.5 15.1 50.7 23 78.6 23"></path>
            </svg></a><a class="p-website-outline__link" href="mailto:info@tplh.net">
            <svg width="24" height="18" viewBox="0 0 100 75">
              <path d="M100 62.5c0 2.2-.6 4.2-1.6 6L66.8 33.2 98.1 5.9c1.2 1.9 1.9 4.2 1.9 6.6v50zM50 39.6l43.5-38c-1.8-1-3.8-1.6-6-1.6h-75c-2.2 0-4.2.6-6 1.6l43.5 38zm12.1-2.3L52 46.1c-.6.5-1.3.8-2.1.8-.7 0-1.5-.3-2.1-.8l-10.1-8.8-32 35.8c1.9 1.2 4.2 1.9 6.6 1.9h75c2.4 0 4.7-.7 6.6-1.9L62.1 37.3zM1.9 5.9C.7 7.8 0 10.1 0 12.5v50c0 2.2.6 4.2 1.6 6l31.6-35.3L1.9 5.9z"></path>
            </svg></a></div>
      </div>
      <div class="p-sketch-outline">
        <h2 class="p-sketch-outline__title">webcam</h2>
        <p class="p-sketch-outline__date">posted: 2018.5.29 / update: 2018.6.9
        </p>
        <p class="p-sketch-outline__description">play an image from a webcam with a fragment shader.</p>
      </div>
      <canvas class="p-canvas-webgl" id="canvas-webgl"></canvas>
      <div class="p-utility-menu"><a class="c-button c-button--black" href="/sketch-threejs/"><span class="c-button__icon c-button__icon--back c-button__icon--black"></span><span class="c-button__label"><span class="js-split-str">b</span><span class="js-split-str">a</span><span class="js-split-str">c</span><span class="js-split-str">k</span></span></a></div>
    </div>
    <script src="/sketch-threejs/js/main.min.js"></script>
    <script>
      (function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]||function(){
      (i[r].q=i[r].q||[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o),
      m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m)
      })(window,document,'script','https://www.google-analytics.com/analytics.js','ga');
      ga('create', 'UA-70611485-1', 'auto');
      ga('send', 'pageview');
    </script>
  </body>
</html>
