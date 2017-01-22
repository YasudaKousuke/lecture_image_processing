#課題7 ダイナミックレンジの拡大
**画素のダイナミックレンジを０から２５５にせよ．**
グレースケール変換
---
標準画像「Eden」を原画像とする．この画像は縦512画像，横512画素による正方形のディジタルカラー画像である。  
**ソースコード7_1**
```matlab
ORG=imread('Eden.png'); % 原画像の入力  
ORG = rgb2gray(ORG); colormap(gray); colorbar; % 白黒濃淡画像に変換  
imagesc(ORG); axis image; % 画像の表示
```
によって，原画像を読み込み，白黒濃淡画像に変換して表示した結果を図１に示す。  
**実行結果7_1**  
![原画像](https://github.com/YasudaKousuke/lecture_image_processing/blob/master/image/kadai7_1.png?raw=true)  
図7_1 グレースケール変換
濃度ヒストグラムの生成、表示
---
**ソースコード7_2**
```matlab
imhist(ORG); % 濃度ヒストグラムを生成、表示
pause;
```
**実行結果7_2**  
![原画像](https://github.com/YasudaKousuke/lecture_image_processing/blob/master/image/kadai7_2.png?raw=true)  
図7_2 濃度ヒストグラムの表示 
ダイナミックレンジの拡大
---
**ソースコード7_3**  
```matlab
ORG = double(ORG);
mn = min(ORG(:)); % 濃度値の最小値を算出
mx = max(ORG(:)); % 濃度値の最大値を算出
ORG = (ORG-mn)/(mx-mn)*255;
imagesc(ORG); colormap(gray); colorbar; % 画像の表示
pause;
```
**実行結果7_3**  
![原画像](https://github.com/YasudaKousuke/lecture_image_processing/blob/master/image/kadai7_3.png?raw=true)  
図7_3 ダイナミックレンジの拡大後の画像  
拡大後の濃度ヒストグラムの生成、表示
---
**ソースコード7_4**  
```matlab
ORG = uint8(ORG);
imhist(ORG); % 濃度ヒストグラムを生成、表示
```
**実行結果7_4**
![原画像](https://github.com/YasudaKousuke/lecture_image_processing/blob/master/image/kadai7_4.png?raw=true)  
図7_3 ダイナミックレンジの拡大後の濃度ヒストグラム  
uint8(ORG)について
---
```matlab
uint8(ORG);
```
はORGを8ビットの符号なし整数への変換を行っている。  
つまり、ORGの出力範囲を0~255の間になるように変換を行っている。
