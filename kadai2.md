# 課題２　階調数と疑似輪郭
**２階調，４階調，８階調の画像を生成せよ．**
グレースケール変換
---
標準画像「Eden」を原画像とする．この画像は縦512画像，横512画素による正方形のディジタルカラー画像である。  
**ソースコード2_1**
```matlab
ORG=imread('Eden.png'); % 原画像の入力  
ORG = rgb2gray(ORG); colormap(gray); colorbar; % 白黒濃淡画像に変換  
imagesc(ORG); axis image; % 画像の表示
```
によって，原画像を読み込み，白黒濃淡画像に変換して表示した結果を図１に示す。  
**実行結果2_1**  
![原画像](https://github.com/YasudaKousuke/lecture_image_processing/blob/master/image/kadai2_1.png?raw=true)  
図2_1 グレースケール変換

2階調変換
---
256階調のカラー画像を2階調にするために256の半分の値「128」を中心として2つに階調を分ける。  
**ソースコード2_2**
```matlab
% ２階調画像の生成
IMG = ORG>128;
imagesc(IMG); colormap(gray); colorbar;  axis image; % グレースケール変換
pause;  
```
**実行結果2_2**  
![原画像](https://github.com/YasudaKousuke/lecture_image_processing/blob/master/image/kadai2_2.png?raw=true)  
図2_2 2階調変換

4階調変換
---
4階調にするために256/4 = 64 より64間隔で4つに分ける。  
**ソースコード2_3**
```matlab
% ４階調画像の生成  
IMG0 = ORG>64;  
IMG1 = ORG>128;  
IMG2 = ORG>192;  
IMG = IMG0 + IMG1 + IMG2;  
imagesc(IMG); colormap(gray); colorbar; axis image;  
```
**実行結果2_3**  
![原画像](https://github.com/YasudaKousuke/lecture_image_processing/blob/master/image/kadai2_3.png?raw=true)  
図2_3 4階調変換  
8階調変換
---
8階調にするために256/8 = 32 より32間隔で8つに分ける。  
**ソースコード2_4**
```matlab
% ８階調画像の生成  
IMG0 = ORG>32;  
IMG1 = ORG>64;  
IMG2 = ORG>96;  
IMG3 = ORG>128;  
IMG4 = ORG>160;  
IMG5 = ORG>192;  
IMG6 = ORG>224;  
IMG = IMG0 + IMG1 + IMG2 + IMG3 + IMG4 + IMG5 + IMG6;  
imagesc(IMG); colormap(gray); colorbar; axis image;  
```
**実行結果2_4**  
![原画像](https://github.com/YasudaKousuke/lecture_image_processing/blob/master/image/kadai2_4.png?raw=true)  
図2_4 8階調変換  
