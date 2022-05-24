---
layout: post
title: "LiTS"

---



# [Tumor detection in medical imaging using neural networks](https://github.com/hamzaokd/LiTS)

## Introduction

In the field of medical imaging, the preprocessing of radiographic images is essential in order to effectively detect cancerous tumours. It also involves locating these tumors and estimating their sizes. In this way, doctors can use this information to diagnose the disease but also monitor the progress of treatment.

In this project, we will seek to detect cancerous tumors in the liver. We will use open access data that have been annotated by experts (radiologists and oncologists): the tumors are therefore known and localized. The figure below gives an idea of ​​the images that will be used.

![Original-Mask](https://github.com/hamzaokd/LiTS/blob/main/media/intro.png)

## Database

The database contains 131 original X-ray images and their corresponding mask images, or 232 images in total, in NII format.
The database can be found in the following links [part1](https://www.kaggle.com/andrewmvd/liver-tumor-segmentation) and [part2](https://www.kaggle.com/andrewmvd/liver-tumor-segmentation-part-2).
## Study of tumors
We will gather the 232 images in a dataframe containing for each of the 131 original images its source file, its name, the source file of its "mask" image and the name of the latter.

After studying the nii images, we managed to understand our data. Indeed, these are 3D images of dimensions 512 x 512 x n, with n changing from one image to another.
 
We add two columns to the dataframe: one that shows whether the image contains a tumor or not and the other displays its percentage.
![dataframe](https://github.com/hamzaokd/LiTS/blob/main/media/database.PNG)


## Image conversion

We chose to use the U-Net neural network, a network designed and applied for the first time in 2015 by Oral Ronneberger for the segmentation of medical images.

In addition to having the correct format for U-Net, having jpg or png images will be very useful since our database is very large (49.9 GB), so the manipulation of x-ray images in the NII format takes a lot of time and memory. With this in mind, we are going to transform the 3D images from NII format into 2D images of regular formats: **a 3D image of dimensions 512x512x n will be transformed into n images 512x512.**

The original images will be transformed into images in jpg format after having preprocessed them thanks to the functions of the fastai library. As for the "mask" images, we will use the png format. This choice is due to the fact that the "labels" 1,2 and 3 contained in an NII "mask" image are lost if this image is transformed into a jpg image, unlike the png format which retains the "labels" well.

After preprocessing we obtain images of the form:
![output](https://github.com/hamzaokd/LiTS/blob/main/media/output.png)

## Implementing U-Net

The implementation, training and prediction part is detailed in the report of another team

* After training the images, we obtain the following predicted images

## Report 
Our report can be found in [here](https://github.com/hamzaokd/LiTS/blob/main/Rapport_LOUTAOUI_OUKADDI.pdf)
***


<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
**French version**

# [Détection de tumeurs avec un réseau de neurones en imagerie médicale](https://github.com/hamzaokd/LiTS)
--- 

## Introduction

Dans le domaine de l'imagerie médicale, le prétraitement des images radiographiques est essentiel afin de détecter efficacement des tumeurs cancéreuses. Il s'agit également de localiser ces tumeurs et d'estimer leurs tailles. De cette manière, les médecins peuvent exploiter ces informations pour diagnostiquer la maladie mais aussi suivre l'évolution du traitement. 

Dans ce projet, nous chercheronls à détecter des tumeurs cancéreuses dans le foie. Nous utiliserons des données en accès libre qui ont été annontées par des experts (radiologistes et oncologues): les tumeurs sont donc connues et localisées. La figure ci-après donne une idée des images qui seront utilisées.

![Original-Mask](https://github.com/hamzaokd/LiTS/blob/main/media/intro.png)

## Base de données

La base de donnée contient 131 images radiographiques originales et leur images "masks" correspondants, soit 232 images au total, en format NII. 
La base données se trouve dans les liens suivants [part1](https://www.kaggle.com/andrewmvd/liver-tumor-segmentation) et [part2](https://www.kaggle.com/andrewmvd/liver-tumor-segmentation-part-2)

## Étude des tumeurs
On va rassembler les 232 images dans un dataframe contenant pour chacune des 131 images originales son fichier source, son nom, le fichier source de son image "mask" et le nom de cette dernière.

Apres l'etude des images nii, On a reussit a comprendre nos donnes. En effet, il s'agit des images 3D de dimensions 512 x 512 x n, avec n qui chnage d'une image a l'autre.
 
On ajoute au dataframe deux colones: une qui montre si l'image contient une tumeur ou pas et l'autre affiche son pourcentage.
![dataframe](https://github.com/hamzaokd/LiTS/blob/main/media/database.PNG)

### Conversion des images NII

Nous avons choisi d'utiliser le réseau de neuronnes U-Net, un réseau conçu et appliqué pour la première fois en 2015 par Oral Ronneberger pour la segmentation d’images médicales.

En plus d'avoir le bon format pour U-Net, avoir des images jpg ou png va être très utile vu que notre base de données est très volumineuse (49,9 Go), donc la manipulation  des images radiographiques sous le format NII prend beaucoup de temps et de mémoire. Dans cette optique, nous allons transformer les images 3D en format NII en images 2D de formats réguliers: **une image 3D de dimensions 512x512x n va être transformée en n images 512x512.**

Les images originaux seront transformées à des images en format jpg après les avoir prétraité grâce aux fonctions de la librairie fastai. Tant que pour les images "mask", nous allons utiliser le format png. Ce choix est dû au fait que les "labels" 1,2 et 3 que contient une image "mask" NII sont perdus si on transforme cette image en une image jpg, contrairement au format png qui conserve bien les "labels".

Apres un pretraitement on obtient des images de la forme:
![output](https://github.com/hamzaokd/LiTS/blob/main/media/output.png)

## Implémentation de U-Net

La partie d'implémentation, d'entraînement et de prédiction est détaillée dans le rapport d'une autre equipe

* Apres l'entraînement des images, on obtient les images prédites suivantes

## Rapport

Notre [rapport](https://github.com/hamzaokd/LiTS/blob/main/Rapport_LOUTAOUI_OUKADDI.pdf)
