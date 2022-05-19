# 資料總覽
問題描述：辨識圖片中的電路板或晶圓片是否有瑕疵，並判斷瑕疵種類。<br/>
資料來源：https://aidea-web.tw/topic/a49e3f76-69c9-4a4a-bcfc-c882840b3f27 <br/>
資料格式： .png <br/>
資料維度：2，分別為Pixel 、RBG <br/>
解析度：512 x 512 <br/>
變數個數： 13+13*4(切割)+13*2(合併) = 共 91個 Haralick-feature (f1,f2,...f13) <br/>
*切割:left-top, left-bottom, right-top, right-bottom
*合併: resize pixel= (256,256) ; (128,128)
## 研究目的：
一、提升模型精準度，找出可辨識的特徵
二、減少模型訓練時間，提升模型的效率

## Introduction
Texture is one of the important characteristics used in identifying objects or regions in an
image. Hence, the paper focus on computable textural features based on gray-tone spatial
dependancies, and illustrate their application with three kinds of image data :
photomicrograph, aerial phtograph, and satellite imagery

We use two kinds of decision rules: piecewise linear decision rule and min-max decision
rule to conduct the image classification studies. Results of studies indicate that the
computable textural features have a general applicability for image-classification
application.

## Concept Explain - Image/Gray-Tone
1. The image in its digital form is usually stored as a two-dimensional array.
2. Suppose image I has N𝘹 and N𝑦 resolution cells in horizontal and vertical directions
respectively, and that gray tone in each cells are quantized to N𝒈 levels.
Let Lx = {1, 2,…,Nx} Ly = {1, 2,...,Ny}be the X and Y spatial domains, and G = {1,
2,…,Ng} be the domain of quantized gray tone.
→ Lx × L𝑦 is the set of resolution cells of the image.
3. The digital image I can be represented as a function which assigns some gray-tone
value G ∈{1,2, ,Ng) to each and every resolution cell in Lx × Ly,
denoted as I: Lx × Ly → G.

## Concept Explain - Textual Features
One important property of tone-texture is the spatial pattern of the resolution cells
composing each discrete tonal feature. When there is no spatial pattern, and the gray-tone
variation between features is wide, a fine texture results. As the spatial pattern becomes
more definite and involves more resolution cells, a coarser texture results. An excellent set
of photographs of different types of texture may be found in.
The procedure for obtaining the textural features of an image is based on the assumption
that the texture information on an image is contained in the overall or average spatial
relationship which the gray tones in the image have to one another

## Concept Explain - Gray-Tone Spatial Dependence Matrix
Our texture information of a image can be extracted from the gray-tone spatial dependence
matrix. We use the information derived from gray-tone spatial dependence matrix to
compute 14 equations (f1 to f14) for measuring textrual features given in Appendix I of this
paper.

We consider a resolution cell to have 8 nearest neighbor
resolution cells as shown in figure . Resolution cells 1 and
5 are 0 degrees nearest neighbors to resolution cell *;
resolution cells 2 and 6 are 135 degrees nearest neighbors
to cell * ; resolution cells 3 and 7 are 90 degrees nearest
neighbors, and so on.
