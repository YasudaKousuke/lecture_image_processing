#課題１標本化間隔と空間解像度
**画像をダウンサンプリングして（標本化間隔を大きくして）表示せよ．**
原画像の表示
---
標準画像「Eden」を原画像とする．この画像は縦512画像，横512画素による正方形のディジタルカラー画像である．  
**ソースコード1_1**
```matlab
ORG=imread('Eden.png'); % 原画像の入力  
imagesc(ORG); axis image; % 画像の表示
```
**実行結果1_1**  
![原画像](https://github.com/YasudaKousuke/lecture_image_processing/blob/master/image/org.png?raw=true)
図1_1 原画像
1/2サンプリング
---
原画像を1/2サンプリングするには，画像を1/2倍に縮小した後，2倍に拡大すればよい．なお，拡大する際には，単純補間するために「box」オプションを設定する．  
**ソースコード1_2**  
```matlab
IMG = imresize(ORG,0.5); % 画像の縮小  
IMG2 = imresize(IMG,2,'box'); % 画像の拡大
```
**実行結果1_2**  
![原画像](https://github.com/YasudaKousuke/lecture_image_processing/blob/master/image/kadai1_1.png?raw=true)  
図1_2 1/2サンプリング  
1/4サンプリング
---
同様に原画像を1/4サンプリングするには，画像を1/2倍に縮小した後，2倍に拡大すればよい．すなわち，  
**ソースコード1_3**  
```matlab
IMG = imresize(ORG,0.5); % 画像の縮小  
IMG2 = imresize(IMG,2,'box'); % 画像の拡大
```
**実行結果1_3**  
![原画像](https://github.com/YasudaKousuke/lecture_image_processing/blob/master/image/kadai1_2.png?raw=true)  
図1_3 1/4サンプリング  
1/8 ~ 1/32サンプリング
---
1/8から1/32サンプリングは，  
**ソースコード1_4**  
```matlab
IMG = imresize(ORG,0.5); % 画像の縮小  
IMG2 = imresize(IMG,2,'box'); % 画像の拡大
```
を繰り返す．サンプリングの結果を示す．  
**実行結果1_4_1**  
![原画像](https://github.com/YasudaKousuke/lecture_image_processing/blob/master/image/kadai1_3.png?raw=true)  
図1_4_1 1/8サンプリング  
![原画像](https://github.com/YasudaKousuke/lecture_image_processing/blob/master/image/kadai1_4.png?raw=true)  
図1_4_2 1/16サンプリング  
![原画像](https://github.com/YasudaKousuke/lecture_image_processing/blob/master/image/kadai1_5.png?raw=true)  
図1_4_3 1/32サンプリング  

このようにサンプリング幅が大きくなると，モザイク状のサンプリング歪みが発生する．
