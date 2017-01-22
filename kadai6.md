#課題6 画像の二値化
**画像を二値化せよ.**
グレースケール変換
---
標準画像「Eden」を原画像とする．この画像は縦512画像，横512画素による正方形のディジタルカラー画像である。  
**ソースコード6_1**
```matlab
ORG=imread('Eden.png'); % 原画像の入力  
ORG = rgb2gray(ORG); colormap(gray); colorbar; % 白黒濃淡画像に変換  
imagesc(ORG); axis image; % 画像の表示
```
によって，原画像を読み込み，白黒濃淡画像に変換して表示した結果を図１に示す。  
**実行結果6_1**  
![原画像](https://github.com/YasudaKousuke/lecture_image_processing/blob/master/image/kadai6_1.png?raw=true)  
図6_1 グレースケール変換
閾値128による二値化
---
**ソースコード6_2**
```matlab
IMG = ORG>128; % 128による二値化
imagesc(IMG); colormap(gray); colorbar; % 画像の表示
pause;
```
**実行結果6_2**  
![原画像](https://github.com/YasudaKousuke/lecture_image_processing/blob/master/image/kadai6_2.png?raw=true)  
図6_2 判別分析法を用いた画像の二値化
ディザ法による二値化
---
**ソースコード6_3**  
```matlab
IMG = dither(ORG); % ディザ法による二値化
imagesc(IMG); colormap(gray); colorbar; % 画像の表示
```
**実行結果6_3**  
![原画像](https://github.com/YasudaKousuke/lecture_image_processing/blob/master/image/kadai6_3.png?raw=true)  
図6_3 ディザ法による二値化
