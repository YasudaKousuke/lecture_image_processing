#課題3 閾値処理
**閾値を4パターン設定し,閾値処理した画像を示せ．**
グレースケール変換
---
標準画像「Eden」を原画像とする．この画像は縦512画像，横512画素による正方形のディジタルカラー画像である。  
**ソースコード3_1**
```matlab
ORG=imread('Eden.png'); % 原画像の入力  
ORG = rgb2gray(ORG); colormap(gray); colorbar; % 白黒濃淡画像に変換  
imagesc(ORG); axis image; % 画像の表示
```
によって，原画像を読み込み，グレースケール変換して表示した結果を図１に示す。  
**実行結果3_1**  
![原画像](https://github.com/YasudaKousuke/lecture_image_processing/blob/master/image/kadai3_1.png?raw=true)  
図3_1 グレースケール変換  
閾値64の場合
---
**ソースコード3_2**
```matlab
IMG = ORG > 64; % 輝度値が64以上の画素を1，その他を0に変換
imagesc(IMG); colormap(gray); colorbar;
pause;
```
**実行結果3_2**  
![原画像](https://github.com/YasudaKousuke/lecture_image_processing/blob/master/image/kadai3_2.png?raw=true)  
図3_2　閾値処理 ( 閾値 = 64 )  
閾値96の場合
---
**ソースコード3_3**  
```matlab
IMG = ORG > 96;
imagesc(IMG); colormap(gray); colorbar;
pause
```
**実行結果3_3**  
![原画像](https://github.com/YasudaKousuke/lecture_image_processing/blob/master/image/kadai3_3.png?raw=true)  
図3_3 閾値処理 ( 閾値 = 96 )  
閾値128の場合
---
**ソースコード3_4**
```matlab
IMG = ORG > 128;
imagesc(IMG); colormap(gray); colorbar;
pause;
```
**実行結果3_4**  
![原画像](https://github.com/YasudaKousuke/lecture_image_processing/blob/master/image/kadai3_4.png?raw=true)  
図3_4 閾値処理 ( 閾値 = 128 )  
閾値192の場合
---
**ソースコード3_5**
```matlab
IMG = ORG > 192;
imagesc(IMG); colormap(gray); colorbar;
pause;
```
**実行結果3_5**  
![原画像](https://github.com/YasudaKousuke/lecture_image_processing/blob/master/image/kadai3_5.png?raw=true)  
図3_5 閾値処理 ( 閾値 = 192 )
