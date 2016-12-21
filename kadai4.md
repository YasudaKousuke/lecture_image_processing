#課題4　画像のヒストグラム
**画像の濃度ヒストグラムを生成せよ**
グレースケール変換
---
標準画像「Eden」を原画像とする．この画像は縦512画像，横512画素による正方形のディジタルカラー画像である。  
**ソースコード4_1**
```matlab
ORG=imread('Eden.png'); % 原画像の入力  
ORG = rgb2gray(ORG); colormap(gray); colorbar; % 白黒濃淡画像に変換  
imagesc(ORG); axis image; % 画像の表示
```
によって，原画像を読み込み，白黒濃淡画像に変換して表示した結果を図１に示す。  
**実行結果4_1**  
![原画像](https://github.com/YasudaKousuke/lecture_image_processing/blob/master/image/kadai4_1.png?raw=true)  
図4_1 グレースケール変換
濃度ヒストグラムの生成
---
**ソースコード4_2**  
```matlab
imhist(ORG); % ヒストグラムの表示
```
**実行結果4_2**  
![原画像](https://github.com/YasudaKousuke/lecture_image_processing/blob/master/image/kadai4_2.png?raw=true)  
図4_2 生成した濃度ヒストグラム
