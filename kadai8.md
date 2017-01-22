#課題8 ラベリング
**二値化された画像の連結成分にラベルをつけよ．**
グレースケール変換
---
標準画像「Eden」を原画像とする．この画像は縦512画像，横512画素による正方形のディジタルカラー画像である。  
**ソースコード8_1**
```matlab
ORG=imread('Eden.png'); % 原画像の入力  
ORG = rgb2gray(ORG); colormap(gray); colorbar; % 白黒濃淡画像に変換  
imagesc(ORG); axis image; % 画像の表示
```
によって，原画像を読み込み，白黒濃淡画像に変換して表示した結果を図１に示す。  
**実行結果8_1**  
![原画像](https://github.com/YasudaKousuke/lecture_image_processing/blob/master/image/kadai8_1.png?raw=true)  
図8_1 グレースケール変換
閾値128による二値化
---
**ソースコード8_2**
```matlab
IMG = ORG > 128; % 閾値128で二値化
imagesc(IMG); colormap(gray); colorbar; % 画像の表示
pause;
```
**実行結果8_2**  
![原画像](https://github.com/YasudaKousuke/lecture_image_processing/blob/master/image/kadai8_2.png?raw=true)  
図8_2 閾値128で二値化した画像  
ラベリング
---
**ソースコード8_3**  
```matlab
IMG = bwlabeln(IMG);
imagesc(IMG); colormap(jet); colorbar; % 画像の表示
pause;
```
**実行結果8_3**  
![原画像](https://github.com/YasudaKousuke/lecture_image_processing/blob/master/image/kadai8_3.png?raw=true)  
図8_3 ラベリング後の画像  
