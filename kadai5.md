#課題5 判別分析法
**判別分析法を用いて画像二値化せよ．**
グレースケール変換
---
標準画像「Eden」を原画像とする．この画像は縦512画像，横512画素による正方形のディジタルカラー画像である。  
**ソースコード5_1**
```matlab
ORG=imread('Eden.png'); % 原画像の入力  
ORG = rgb2gray(ORG); colormap(gray); colorbar; % 白黒濃淡画像に変換  
imagesc(ORG); axis image; % 画像の表示
```
によって，原画像を読み込み，白黒濃淡画像に変換して表示した結果を図１に示す。  
**実行結果5_1**  
![原画像](https://github.com/YasudaKousuke/lecture_image_processing/blob/master/image/kadai5_1.png?raw=true)  
図5_1 グレースケール変換
判別分析法を用いた画像の二値化
---
**ソースコード5_2**
```matlab
H = imhist(ORG); %ヒストグラムのデータを列ベクトルEに格納
myu_T = mean(H);
max_val = 0;
max_thres = 1;
for i=1:255
C1 = H(1:i); %ヒストグラムを2つのクラスに分ける
C2 = H(i+1:256);
n1 = sum(C1); %画素数の算出
n2 = sum(C2);
myu1 = mean(C1); %平均値の算出
myu2 = mean(C2);
sigma1 = var(C1); %分散の算出
sigma2 = var(C2);
sigma_w = (n1 *sigma1+n2*sigma2)/(n1+n2); %クラス内分散の算出
sigma_B = (n1 *(myu1-myu_T)^2+n2*(myu2-myu_T)^2)/(n1+n2); %クラス間分散の算出
if max_val<sigma_B/sigma_w
max_val = sigma_B/sigma_w;
max_thres =i;
end;
end;

IMG = ORG > max_thres;
imagesc(IMG); colormap(gray); colorbar;
pause;
```
**実行結果5_2**  
![原画像](https://github.com/YasudaKousuke/lecture_image_processing/blob/master/image/kadai5_2.png?raw=true)  
図5_2 判別分析法を用いた画像の二値化
