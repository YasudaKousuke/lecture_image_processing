#課題10 画像のエッジ抽出 
**エッジ抽出を体験せよ．**
グレースケール変換
---
標準画像「Eden」を原画像とする．この画像は縦512画像，横512画素による正方形のディジタルカラー画像である。  
**ソースコード10_1**
```matlab
ORG=imread('Eden.png'); % 原画像の入力  
ORG = rgb2gray(ORG); colormap(gray); colorbar; % 白黒濃淡画像に変換  
imagesc(ORG); axis image; % 画像の表示
```
によって，原画像を読み込み，白黒濃淡画像に変換して表示した結果を図１に示す。  
**実行結果10_1**  
![原画像](https://github.com/YasudaKousuke/lecture_image_processing/blob/master/image/kadai10_1.png?raw=true)  
図10_1 グレースケール変換
エッジ抽出（プレウィット法）
---
**ソースコード10_2**
```matlab
IMG = edge(ORG,'prewitt'); % エッジ抽出（プレウィット法）
imagesc(IMG); colormap('gray'); colorbar;% 画像表示
pause; % 一時停止
```
**実行結果10_2**  
![原画像](https://github.com/YasudaKousuke/lecture_image_processing/blob/master/image/kadai10_2.png?raw=true)  
図10_2 エッジ検出（プレウィット法）後の画像  
エッジ抽出（ソベル法）
---
**ソースコード10_3**  
```matlab
IMG = edge(ORG,'sobel'); % エッジ抽出（ソベル法）
imagesc(IMG); colormap('gray'); colorbar;% 画像表示
pause; % 一時停止
```
**実行結果10_3**  
![原画像](https://github.com/YasudaKousuke/lecture_image_processing/blob/master/image/kadai10_3.png?raw=true)  
図10_3 エッジ抽出（ソベル法）後の画像  
エッジ抽出（キャニー法）
---
**ソースコード10_4**  
```matlab
IMG = edge(ORG,'canny'); % エッジ抽出（キャニー法）
imagesc(IMG); colormap('gray'); colorbar;% 画像表示
pause; % 一時停止
```
**実行結果10_4**  
![原画像](https://github.com/YasudaKousuke/lecture_image_processing/blob/master/image/kadai10_4.png?raw=true)  
図10_4 エッジ抽出（キャニー法）後の画像
