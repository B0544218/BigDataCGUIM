��Ʊ���
========================================================
author: ���N�� Yi-Ju Tseng
date: 2017/05/22
autosize: true
font-family: 'Microsoft JhengHei'
navigation: slide


�����ѥ����`
========================================================
[10 ��Ʊ���](http://yijutseng.github.io/DataScienceRBook/datamining.html)

�j��
====================================
type:sub-section 

- ����O��Ʊ���
- Regression �j�k
- Decision Trees �M����

����O��Ʊ���
====================================

**��Ʊ��ɡ]Data mining�^**�O�ΤH�u���z�B�����ǲߡB�έp�Ǫ���e��k�A�b�۹���j������ƶ����o�{�Ҧ����p��L�{�C�ϥθ�Ʊ��ɧ޳N�i�H�إ߱q**��J���**�ǲ߷s��T�A�ܦ����z��**�t��k**��**��ƼҦ�**�A�Ψ�**�w���ƥ�**��**��U�M��**�C�ҥH�A���Ƥ�`��`��`��ż`���ɭԡA��Ʊ��ɪ��ĤO�|�Q�v�T�C

��Ʊ��ɭn���W�γ��A�������H�U����G

- ���@�ǼҦ�/�ҫ��i`��`
- �����w�q�o�ǼҦ�/�ҫ�
- ����ƥi`��`�o�ǼҦ�/�ҫ�

��Ʊ��ɥi���Φb
====================================

- �Ѯ�w��
- �j�M��ĳ�B�ʪ���ĳ
- �ѥ��w��
- �y�����ѡB��������
- �U���l��аO
- ������s

��Ʊ��ɪ�����
====================================

��Ʊ��ɥi����**�ʷ���**�ǲ߻P**�D�ʷ���**�ǲߡA�ʷ����ǲߪ��S�I�O�V�m��Ƥ���**���T����**�A�ѿ�J����M�w����X�Ҳզ��A�Ӻt��k�i�H�ѰV�m��Ƥ��Ǩ�Ϋإߤ@�ӼҦ��A�è̦��Ҧ������s����ҡF�D�ʷ����ǲ߫h���δ���**���T����**�A�]�N�O���ݭn�H�O�ӿ�J���ҡA��§Q�ΰV�m��ƪ��S�ʡA�N��Ƥ��s���աC

����ؾǲߥi�ѨM���P�����D�A���C�p�U�G

- Supervised learning �ʷ����ǲ�
    - Regression �j�k�G�u�ꪺ'��'�]�Ѳ��B��š^
    - Classification �����G�������]P/N, Yes/No, M/F, Sick/Not sick�^/���h�� (A/B/C/D)

- Unsupervised learning �D�ʷ����ǲ�
    - Clustering ���s
    - Association Rules ���p���W�h

�ʷ����ǲ�
====================================

�b**�ʷ���**�ǲߤ��`������Ʊ��ɺt��k�p�U�G 
  - Linear Regression �u�ʰj�k
  - Logistic Regression ù�N���j�k�B�޿�j�k
  - Support Vector Machines ����V�q��
  - Decision Trees �M����
  - K-Nearest Neighbor
  - Neural Networks ���g����
  - Deep Learning �`�׾ǲ�

�D�ʷ����ǲ�
====================================

�b**�D�ʷ���**�ǲߤ��`������Ʊ��ɺt��k�p�U�G 
  - Hierarchical clustering ���h�����s
  - K-means clustering
  - Neural Networks ���g����
  - Deep Learning �`�׾ǲ�


Regression �j�k
====================================

Regression Analysis �j�k���R�D�n�Φb�F�Ѩ�өΦh���ܼƶ�`�O�_����`�B`������V�P�j��`�A�ëإ�`�ƾǼҫ�`�H�K�[��S�w�ܼƨӹw����s�̷P���쪺�ܼơA�`�����j�k���R�t��k�]�A�G

- Linear Regression �u�ʰj�k
- Logistic Regression ù�N���j�k�B�޿�j�k

Linear Regression �u�ʰj�k
====================================

�����A���ձNLinear Regression �u�ʰj�k�ΦbNBA����ƬݬݡA��NBA`�o��`�P`�W��������`���u�ʰj�k�[��

```r
#Ū�JSportsAnalytics package
library(SportsAnalytics)
#�^��2015-2016�~�y�u�y�����
NBA1516<-fetch_NBAPlayerStatistics("15-16")
```

�j�k�u�@��
====================================

```r
library(ggplot2)
ggplot(NBA1516,aes(x=TotalMinutesPlayed,y=TotalPoints))+
    geom_point()+geom_smooth(method = "glm")
```

![plot of chunk linear2](11_DataMining-figure/linear2-1.png)

lm()
====================================

�bR���A�̰򥻪�²��u�ʰj�k���R��`lm()`�A�ϥΤ�k��`lm(formula,data=��ƦW��)`�A�f�tformula�ϥΡAformula�����g��k���G���ܶ�~���ܶ�1�Ϧ��ܶ�2��....

```r
lm(TotalPoints~TotalMinutesPlayed,data =NBA1516)
```

```

Call:
lm(formula = TotalPoints ~ TotalMinutesPlayed, data = NBA1516)

Coefficients:
       (Intercept)  TotalMinutesPlayed  
          -85.9071              0.4931  
```

TotalPoints = `0.4931` * TotalMinutesPlayed `-85.9071`

glm()
====================================
��Q�s�x�ϥΪ��O�s�q�u�ʰj�k�ҫ�generalized linear models (glm)�A��Ƭ�`glm()`�A�ϥΤ�k�P`lm()`�����A�]�A�F�u�ʰj�k�ҫ��M�޿�j�k�ҫ��C
�p�G�ݭn�ק�w�]�ҫ��A�i�]�wfamily�ѼơG
    - `family="gaussian"` �u�ʼҫ��ҫ�
    - `family="binomial"` �޿�j�k�ҫ�
    - `family="poisson"` �R�˪Q�j�k�ҫ�
    
Gaussian distribution
====================================
Gaussian distribution������ƬO`�`�A����`���K�ר��

Binomial distribution
====================================
Binomial distribution�G�������O`n�ӿW�ߪ��O/�D���礤���\������`���������v����

Poisson distribution
====================================
Poisson distribution`����`���G�G

- �Y�@�A�ȳ]�I�b�@�w�ɶ������쪺�A�ȽШD������
- ���������ԫȤH��
- �����G�ټ�
- �۵M�a�`�o�ͪ�����
- DNA�ǦC���ܲ���.....

glm()�PNBA
====================================
�H�U���ϥΦh�ܶq�u�ʰj�k�Ӥ��R`�o��`�P`�W��������`�M`����y�X���`�����Y�d��


```r
# e+01: 10^1 / e-04: 10^(-4)
glm(TotalPoints~TotalMinutesPlayed+FieldGoalsAttempted,
    data =NBA1516)
```

```

Call:  glm(formula = TotalPoints ~ TotalMinutesPlayed + FieldGoalsAttempted, 
    data = NBA1516)

Coefficients:
        (Intercept)   TotalMinutesPlayed  FieldGoalsAttempted  
         -1.799e+01           -2.347e-04            1.256e+00  

Degrees of Freedom: 475 Total (i.e. Null);  473 Residual
Null Deviance:	    99360000 
Residual Deviance: 2160000 	AIC: 5367
```

TotalPoints = `-0.0002347` * TotalMinutesPlayed + `1.255794` *FieldGoalsAttempted  `-17.99`

glm()�PNBA
====================================
�p�ݨϥΦh�ܶq�u�ʰj�k�Ӥ��R`�o��`�P`�W��������`�M`����y�X���`�M`�u�Ʀ�m`�����Y�A�i�ק�formula


```r
glm(TotalPoints~TotalMinutesPlayed+FieldGoalsAttempted+Position,
    data =NBA1516)
```

```

Call:  glm(formula = TotalPoints ~ TotalMinutesPlayed + FieldGoalsAttempted + 
    Position, data = NBA1516)

Coefficients:
        (Intercept)   TotalMinutesPlayed  FieldGoalsAttempted  
          22.852223            -0.006537             1.275721  
         PositionPF           PositionPG           PositionSF  
         -39.416327           -65.034646           -38.522299  
         PositionSG  
         -52.175144  

Degrees of Freedom: 474 Total (i.e. Null);  468 Residual
  (1 observation deleted due to missingness)
Null Deviance:	    99080000 
Residual Deviance: 1975000 	AIC: 5322
```

```r
# e+01: 10^1 / e-04: 10^(-4)
```

TotalPoints = `-0.0065` * TotalMinutesPlayed + `1.28` *FieldGoalsAttempted  `+22.85` + `22.85` * PositionPF + `-65.03` * PositionPG + `-38.52` * PositionSF + `-52.18` * PositionSG

�����ܶ� Dummy Variable
====================================
�ѤW�z���G�i�o�{�A`�u�Ʀ�m`���ܶ��Q�ର**�����ܶ� Dummy Variable**�GPositionPF�BPositionPG�BPositionSF�BPositionSG�A�p�G�O���y��á]PG�^�A�|�o��G

  - PositionPF=0
  - PositionPG=1
  - PositionSF=0
  - PositionSG=0
  
���W�h���F�H
====================================
��ꤤ�W�Q��@��Ƕ��A�]�N�O��u�Ʀ�m�O���W(C)�ɡA�|�o��G

  - PositionPF=0
  - PositionPG=0
  - PositionSF=0
  - PositionSG=0

�u�ʰj�k�`��
====================================
�`���H�W�A�h�ܶq�u�ʰj�k���R���U�C�S��G

- ���]�G�U�ܼƬۤ��W�ߡI
- �Y���ܶ�X�O���O�ܶ��A�ݭn�إ�`�����ܶ�`
- �bR�̡A`���O�ܶ�`�аO�o�নfactor�AR�|�۰ʫإ�`�����ܶ�`
- �Φb`���ܼƬ��s���ܼ�`�A`���ܼƬ��s���ܼƩε����ܼ�`�����X


Logistic Regression ù�N���j�k
====================================

Logistic Regression ù�N���j�k�`�Φb`���ܼƬ��G���ܼơ]�D0�Y1�^`�����X�A�p�G
  - �ͯf/�S�ͯf
  - ����/������
  - `family="binomial"` �޿�j�k�ҫ�

���R���������/�������H
====================================

```r
mydata <- read.csv("http://www.ats.ucla.edu/stat/data/binary.csv")
```

```r
# GRE:�Y�Ҹզ��Z, GPA:�b�ե������Z, rank:�Ǯ��n��
head(mydata)
```

|X..DOCTYPE.html.                                                                                                                           |
|:------------------------------------------------------------------------------------------------------------------------------------------|
|<html lang=en-US prefix=og: http://ogp.me/ns#>                                                                                             |
|<head >                                                                                                                                    |
|<meta charset=UTF-8 />                                                                                                                     |
|<title>Statistics - Institute for Digital Research and Education</title><meta name=viewport content=width=device-width, initial-scale=1 /> |
|<meta name=viewport content=width=device-width, initial-scale=1.0/><script>                                                                |
|jQuery(function($) {                                                                                                                       |

���R���������/�������H
====================================




















```
Error in `$<-.data.frame`(`*tmp*`, "rank", value = integer(0)) : 
  replacement has 0 rows, data has 526
```
