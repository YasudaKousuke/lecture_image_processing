#課題9 メディアンフィルタと先鋭化
**メディアンフィルターを適用し，ノイズ除去を体験せよ．**
グレースケール変換
---
標準画像「Eden」を原画像とする．この画像は縦512画像，横512画素による正方形のディジタルカラー画像である。  
**ソースコード9_1**
```matlab
ORG=imread('Eden.png'); % 原画像の入力  
ORG = rgb2gray(ORG); colormap(gray); colorbar; % 白黒濃淡画像に変換  
imagesc(ORG); axis image; % 画像の表示
```
によって，原画像を読み込み，白黒濃淡画像に変換して表示した結果を図１に示す。  
**実行結果9_1**  
![原画像](https://github.com/YasudaKousuke/lecture_image_processing/blob/master/image/kadai9_1.png?raw=true)  
図9_1 グレースケール変換
ノイズ添付
---
**ソースコード9_2**  
```matlab
ORG = imnoise(ORG,'salt & pepper',0.02); % ノイズ添付
imagesc(ORG); colormap(gray); colorbar; % 画像の表示
pause;
```
**実行結果9_2**  
![原画像](https://github.com/YasudaKousuke/lecture_image_processing/blob/master/image/kadai9_2.png?raw=true)  
図9_2 ノイズ添付後の画像  
平滑化フィルタ
---
**ソースコード9_3**  
```matlab
IMG = filter2(fspecial('average',3),ORG); % 平滑化フィルタで雑音除去
imagesc(IMG); colormap(gray); colorbar; % 画像の表示
pause;
```
**実行結果9_3**  
![原画像](https://github.com/YasudaKousuke/lecture_image_processing/blob/master/image/kadai9_3.png?raw=true)  
図9_3 平滑化フィルタで雑音除去後の画像  
メディアンフィルタ
---
**ソースコード9_4**
```matlab
IMG = medfilt2(ORG,[3 3]); % メディアンフィルタで雑音除去
imagesc(IMG); colormap(gray); colorbar; % 画像の表示
pause;
```
**実行結果9_4**  
![原画像](https://github.com/YasudaKousuke/lecture_image_processing/blob/master/image/kadai9_4.png?raw=true)  
図9_4 メディアンフィルタで雑音除去後の画像
フィルタの設計
---
**ソースコード9_5**  
```matlab
f=[0,-1,0;-1,5,-1;0,-1,0]; % フィルタの設計
IMG = filter2(f,IMG,'same'); % フィルタの適用
imagesc(IMG); colormap(gray); colorbar; % 画像の表示
pause;
```
**実行結果9_5**  
![原画像](https://github.com/YasudaKousuke/lecture_image_processing/blob/master/image/kadai9_5.png?raw=true)  
図9_5 フィルタ適用後の画像
