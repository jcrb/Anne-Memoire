# Mémoire d'Anne Weiss: SEP et pré-briefing
jcb  
24 juin 2015  

Matériel et méthode
===================

L'ensemble des apprenants sont divisés en 2 groupes selon qu'ils ont bénéficié ou non d'un prébriefing. La répartition entre ces 2 groupes s'est faite aléatoirement. Le _sentiment d'efficacité personnel_ (SEP) de chaque participant a été évalué par un questionnaire comportant 12 items de likert gradués de 1 à 8. Ce questionnaire a été soumis à chaque participant avant la formation (pré-test) et à l'issue de celle-ci (post-test). Cinq questions à choix multiple précisent le profil du candidat. Le consentement éclairé des participant a été recueilli (?).

Les données pré-test et post-test des 12 items avec échelle de Likert et des 5 questions à choix multiple ont été saisie dans un tableur (Exel) et importées dans le logiciel R version 3.1.3 (2015-03-09) pour être analysées.

Toutes les caractéristiques du groupes sont de nature qualitative. Le test utilisé pour les comparer est le __test du Chi2__ (avec correction de continuité de Yates). Cependant les effectifs sont faibles et lorsque les conditions d’application du Chi2 ne sont pas respectées, des effectifs ont été regroupés (années d’étude) et/ou le __test exact de Fisher__ a été utilisé. Les groupes sont considérés comme différents si p-value est plus petite que 0.05.

Le score de Likert est calculé en sommant les items de Likert. Deux scores sont étudiés selon que la somme des items porte sur les 8 premiers (échelle éprouvée) ou sur les 12 items (échelle expérimentale). Les moyennes des échelles de Likert des 2 groupes sont comparées à l'aide du __test de Student__. Les comparaisons pré-test / post-test des moyennes des scores utilisent le __test de Student pour séries appariées__. Un différence inférieure à 5% (p < 0.05) a été considérée comme significative.

Lecture des fichiers
====================


Fichier des apprenants:

```
 [1] "ID_Etud"                      "Groupe_ID"                   
 [3] "SMI"                          "FDP"                         
 [5] "FMN"                          "PROF"                        
 [7] "ETUDE"                        "SEXE"                        
 [9] "ROLE"                         "Nature.de.la.formation..NAT."
[11] "PREB"                        
```

Questionnaire "avant" (lk.av):

```
 [1] "DATE"      "ID_Etud"   "Groupe_ID" "Q1.av"     "Q2.av"    
 [6] "Q3.av"     "Q4.av"     "Q5.av"     "Q6.av"     "Q7.av"    
[11] "Q8.av"     "Q9.av"     "Q10.av"    "Q11.av"    "Q12.av"   
```
Questionnaire après (lk.ap):

```
 [1] "DATE"      "ID_Etud"   "Groupe_ID" "Q1.ap"     "Q2.ap"    
 [6] "Q3.ap"     "Q4.ap"     "Q5.ap"     "Q6.ap"     "Q7.ap"    
[11] "Q8.ap"     "Q9.ap"     "Q10.ap"    "Q11.ap"    "Q12.ap"   
```
Les items de Likert correspondent aux colonnes 4 à 15

On forme un fichier global par combinaison des questionnaires _avant_ et _après_. Ajout d'une colonne __PREB__ (O/N) pour identifier le groupe ayant bénéficié d'un prébriefing.

```
 [1] "DATE"      "ID_Etud"   "Groupe_ID" "Q1.av"     "Q2.av"    
 [6] "Q3.av"     "Q4.av"     "Q5.av"     "Q6.av"     "Q7.av"    
[11] "Q8.av"     "Q9.av"     "Q10.av"    "Q11.av"    "Q12.av"   
[16] "Q1.ap"     "Q2.ap"     "Q3.ap"     "Q4.ap"     "Q5.ap"    
[21] "Q6.ap"     "Q7.ap"     "Q8.ap"     "Q9.ap"     "PREB"     
```

Analyse des groupes avec et sans prebriefing
============================================

Toutes les caractéristiques des groupes sont de nature qualitative. Le test approprié pour les comparer est le test du Chi2 (avec correction de continuité de Yates). Cependant les effectifs sont faibles et lorsque les conditions d'application du chi2 ne sont pas respectées, des effectifs ont été regroupés (années d'étude) et/ou le test exact de Fisher a été utilisé. Les goupes sont considérés comme différents si _p-value_ est plus petite que 0.05.

Sexe sdes apprenants
---------------------

```
    PREB
Sexe  N  O
   F 17 17
   M 12 10
```
La répartition des hommes et des femmes est identique dans deux groupes (p = 0.95
)

SMI (situation de mort inattendue)
----------------------------------

```
                            PREB
SMI                           N  O
  jamais                      4  5
  plusieurs fois par an      22 18
  plusieurs fois par mois     3  2
  plusieurs fois par semaine  0  2
```
Pas de différence entre les deux groupes (p = 0.56)

FDP formation décès patient
---------------------------

```
   PREB
FDP  N  O
  N 16 20
  O 13  7
```
Pas de différence entre les deux groupes (p = 0.23)

FMN formation annonce mauvaise nouvelle
---------------------------------------

```
   PREB
FMN  N  O
  N  7 16
  O 22 11
```
__Différence significative__ entre les deux groupes (p = 0.02)

Profession
----------

```
          PREB
PROF        N  O
  DESC AN   4  1
  DESC MU   0  1
  ETUDIANT 25 25
```
Pas de différence entre les deux groupes (p = 0.56)

Rôle dans la simulation
-----------------------

```
             PREB
ROLE           N  O
  EXTERNE      6  6
  IDE          3  3
  INTERNE      4  4
  OBSERVATEUR 16 14
```
Pas de différence entre les deux groupes (p = 1)

Années d'étude
--------------


```
               PREB
Années d'études  N  O
              1  0  1
              3  0  1
              4  4  0
              6 25 18
              7  0  3
              8  0  3
```

```
                N  O
moins de 6 ans  4  2
6 ans ou plus  25 24
```
Pas de différence entre les deux groupes (p = 0.67)

__Conclusion: les groupes avec et sans prébriefing ne sont pas différents sauf en ce qui concerne la formation à l'annonce d'une mauvaise nouvelle.__

Analyse du sentiment d'efficacité personnel (SEP)
=================================================

Le SEP est mesuré sur les 8 premiers items du score de Likert (validé) et sur les 12 items (expérimental).

Pré-test
-----------------------

### SEP8
![](likert_files/figure-html/sep_avant_sep8-1.png) ![](likert_files/figure-html/sep_avant_sep8-2.png) 

#### SEP (Score de Likert) avant la formation:

- Ensemble du groupe:
    - moyenne SEP8: $30.4 \pm{8.4}$
    - médiane SEP8: $30$
- Sous-groupe sans prebriefing
    - moyenne: $31.28 \pm{8.12}$
    - médiane: $32$
- Sous-groupe avec prebriefing
    - moyenne: $29.41 \pm{8.74}$
    - médiane: $29$

### SEP12
![](likert_files/figure-html/sep_avant_sep12-1.png) 

#### SEP (Score de Likert) avant la formation:

- Ensemble du groupe:
    - moyenne SEP12: $53.7 \pm{9.3}$
    - médiane SEP12: $54$
- Sous-groupe sans prebriefing
    - moyenne: $54.5 \pm{8.96}$
    - médiane: $54$
- Sous-groupe avec prebriefing
    - moyenne: $52.85 \pm{9.74}$
    - médiane: $55$

#### Comparaison du SEP avant la formation, selon que les apprenants aient bénéficiés ou non d'un prébriefing (Test T de Student):


- SEP8: pas de différence (p = 0.41)
- SEP12: pas de différence (p = 0.52)



__Conclusion__: les groupes ne sont pas différents en ce qui concerne le sentiment d'efficacité personnel avant la formation.

Post-test
-----------------------



### SEP8 (après)

![](likert_files/figure-html/sep8après-1.png) 

#### SEP (Score de Likert) après la formation:

- Ensemble du groupe:
    - moyenne SEP8: $36.7 \pm{9.41}$
    - médiane SEP8: $36$
- Sous-groupe sans prebriefing
    - moyenne: $37.76 \pm{8.5}$
    - médiane: $36$
- Sous-groupe avec prebriefing
    - moyenne: $35.52 \pm{10.32}$
    - médiane: $36$
    
### SEP12 (après)

![](likert_files/figure-html/sep12APRES-1.png) 

#### SEP (Score de Likert) après la formation:

- Ensemble du groupe:
    - moyenne SEP12: $59.6 \pm{11.11}$
    - médiane SEP12: $61$
- Sous-groupe sans prebriefing
    - moyenne: $61 \pm{9.85}$
    - médiane: $60$
- Sous-groupe avec prebriefing
    - moyenne: $58.04 \pm{12.32}$
    - médiane: $62$

#### Comparaison du SEP après la formation, selon que les apprenants aient bénéficiés ou non d'un prébriefing (Test T de Student):



- SEP8: pas de différence (p = 0.38)
- SEP12: pas de différence (p = 0.33)

__Conclusion__: après la formation, le SEP à progressé mais dans les mêmes proportions dans les deux groupes et il n'y a pas de différence de entre les SEP que le groupe ait bénéficié ou pas d'un prébriefing. 


Est-ce que la formation a une influence sur le SEP?
----------------------------------------------------
Pour répondre à la question, on compare le SEP avant et après la formation (test de Student por séries appariées):

### SEP12


- SEP12: __différence très significative__ (p = 0)

### SEP8



- SEP8: __différence très significative__ (p = 0)

__Conclusion__: dans les 2 cas le SEP progresse fortement et significativement. La formation a un effet positif sur l'évolution du SEP. 

### Analyse en sous groupes



#### SEP8
- sous-groupe avec prébriefing: SEP8 avant = 29.41, SEP8 après = 35.52, p = 0
- sous-groupe sans prébriefing: SEP8 avant = 31.28, SEP8 après = 37.76, p = 0

#### SEP12
- sous-groupe avec prébriefing: SEP12 avant = 52.85, SEP12 après = 58.04, p = 0
- sous-groupe sans prébriefing: SEP12 avant = 54.5, SEP12 après = 61, p = 0

__Conclusion__: quuelque soit l'échelle utilisée, le SEP progresse fortement et significativement quelque soit le sous-groupe considéré. La formation a un effet positif sur l'évolution du SEP. 

Evaluer le nombre de sujets nécessaires.

Résultats préliminaires
=======================

Scores de Likert avant
-----------------------

```
##      Item    1    2    3    4    5    6    7    8
## 1   Q1.av 14.3 25.0 25.0 17.9 14.3  3.6  0.0  0.0
## 2   Q2.av 21.4 35.7 21.4  8.9 12.5  0.0  0.0  0.0
## 3   Q3.av  3.6 12.5 16.1 32.1 14.3 16.1  1.8  3.6
## 4   Q4.av  1.8  7.1 16.1 14.3 14.3 26.8 12.5  7.1
## 5   Q5.av 14.3 25.0 23.2 30.4  5.4  1.8  0.0  0.0
## 6   Q6.av  5.4 16.1 21.4 16.1 19.6 19.6  1.8  0.0
## 7   Q7.av  3.6  1.8 14.3 19.6 23.2 23.2 10.7  3.6
## 8   Q8.av  5.4 14.3 23.2 23.2 16.1 12.5  3.6  1.8
## 9   Q9.av  1.8  5.5  7.3  9.1 16.4 29.1 20.0 10.9
## 10 Q10.av  0.0  0.0  0.0  5.4  0.0 19.6 35.7 39.3
## 11 Q11.av  3.6  7.1 12.5  3.6 23.2 21.4 21.4  7.1
## 12 Q12.av  1.8 14.3  8.9  5.4  1.8 21.4 21.4 25.0
```

![](likert_files/figure-html/score_avant-1.png) 

```
##      Q1.av       Q2.av         Q3.av         Q4.av         Q5.av    
##  Min.   :1   Min.   :1.0   Min.   :1.0   Min.   :1.0   Min.   :1.0  
##  1st Qu.:2   1st Qu.:2.0   1st Qu.:3.0   1st Qu.:3.8   1st Qu.:2.0  
##  Median :3   Median :2.0   Median :4.0   Median :5.0   Median :3.0  
##  Mean   :3   Mean   :2.6   Mean   :4.1   Mean   :5.0   Mean   :2.9  
##  3rd Qu.:4   3rd Qu.:3.0   3rd Qu.:5.0   3rd Qu.:6.0   3rd Qu.:4.0  
##  Max.   :6   Max.   :5.0   Max.   :8.0   Max.   :8.0   Max.   :6.0  
##                                                                     
##      Q6.av         Q7.av         Q8.av         Q9.av         Q10.av   
##  Min.   :1.0   Min.   :1.0   Min.   :1.0   Min.   :1.0   Min.   :4.0  
##  1st Qu.:3.0   1st Qu.:4.0   1st Qu.:3.0   1st Qu.:5.0   1st Qu.:6.8  
##  Median :4.0   Median :5.0   Median :4.0   Median :6.0   Median :7.0  
##  Mean   :3.9   Mean   :4.9   Mean   :3.9   Mean   :5.5   Mean   :7.0  
##  3rd Qu.:5.0   3rd Qu.:6.0   3rd Qu.:5.0   3rd Qu.:7.0   3rd Qu.:8.0  
##  Max.   :7.0   Max.   :8.0   Max.   :8.0   Max.   :8.0   Max.   :8.0  
##                                            NA's   :1                  
##      Q11.av        Q12.av   
##  Min.   :1.0   Min.   :1.0  
##  1st Qu.:4.0   1st Qu.:3.8  
##  Median :5.5   Median :6.0  
##  Mean   :5.2   Mean   :5.7  
##  3rd Qu.:7.0   3rd Qu.:7.2  
##  Max.   :8.0   Max.   :8.0  
## 
```

Score de Likert après
---------------------

```
##      Item   1    2    3    4    5    6    7    8
## 1   Q1.ap 8.9 12.5 19.6 16.1 32.1  8.9  1.8  0.0
## 2   Q2.ap 5.4 17.9 23.2 19.6 23.2  5.4  5.4  0.0
## 3   Q3.ap 1.8  7.1  8.9 14.3 19.6 26.8 12.5  8.9
## 4   Q4.ap 1.8  1.8  3.6 17.9 14.3 26.8 23.2 10.7
## 5   Q5.ap 3.6  7.1 23.2 21.4 37.5  7.1  0.0  0.0
## 6   Q6.ap 3.6  5.4 16.1 21.4 25.0 26.8  1.8  0.0
## 7   Q7.ap 0.0  5.4  5.4 28.6 19.6 16.1 19.6  5.4
## 8   Q8.ap 3.6  5.4 14.3 19.6 32.1 16.1  7.1  1.8
## 9   Q9.ap 1.8  3.6  7.1  5.4 19.6 28.6 23.2 10.7
## 10 Q10.ap 0.0  1.8  1.8  0.0  7.1 14.3 37.5 37.5
## 11 Q11.ap 5.4 10.7 10.7  8.9 16.1 30.4 14.3  3.6
## 12 Q12.ap 1.8 10.7  8.9  5.4 17.9 23.2 16.1 16.1
```

![](likert_files/figure-html/score_apres-1.png) 

```
##      Q1.ap         Q2.ap         Q3.ap         Q4.ap         Q5.ap  
##  Min.   :1.0   Min.   :1.0   Min.   :1.0   Min.   :1.0   Min.   :1  
##  1st Qu.:3.0   1st Qu.:3.0   1st Qu.:4.0   1st Qu.:4.8   1st Qu.:3  
##  Median :4.0   Median :4.0   Median :5.0   Median :6.0   Median :4  
##  Mean   :3.8   Mean   :3.8   Mean   :5.2   Mean   :5.7   Mean   :4  
##  3rd Qu.:5.0   3rd Qu.:5.0   3rd Qu.:6.0   3rd Qu.:7.0   3rd Qu.:5  
##  Max.   :7.0   Max.   :7.0   Max.   :8.0   Max.   :8.0   Max.   :6  
##      Q6.ap         Q7.ap         Q8.ap         Q9.ap         Q10.ap   
##  Min.   :1.0   Min.   :2.0   Min.   :1.0   Min.   :1.0   Min.   :2.0  
##  1st Qu.:3.8   1st Qu.:4.0   1st Qu.:4.0   1st Qu.:5.0   1st Qu.:6.8  
##  Median :5.0   Median :5.0   Median :5.0   Median :6.0   Median :7.0  
##  Mean   :4.5   Mean   :5.2   Mean   :4.6   Mean   :5.7   Mean   :6.9  
##  3rd Qu.:6.0   3rd Qu.:6.2   3rd Qu.:5.2   3rd Qu.:7.0   3rd Qu.:8.0  
##  Max.   :7.0   Max.   :8.0   Max.   :8.0   Max.   :8.0   Max.   :8.0  
##      Q11.ap        Q12.ap   
##  Min.   :1.0   Min.   :1.0  
##  1st Qu.:3.0   1st Qu.:4.0  
##  Median :5.0   Median :6.0  
##  Mean   :4.9   Mean   :5.4  
##  3rd Qu.:6.0   3rd Qu.:7.0  
##  Max.   :8.0   Max.   :8.0
```


Note: pour étudier une colonne seule, il faut utiliser la syntaxe suivante:

```r
q1a <- lk.av[, 4, drop = FALSE]
# plot likert
plot(likert(q1a,nlevels = 8))
```

![](likert_files/figure-html/unnamed-chunk-1-1.png) 

```r
# summary spécifique
summary(likert(q1a,nlevels = 8))
```

```
##    Item low neutral high mean  sd
## 1 Q1.av  82       0   18    3 1.4
```

```r
# %
likert(q1a, nlevels = 8)
```

```
##    Item  1  2  3  4  5   6 7 8
## 1 Q1.av 14 25 25 18 14 3.6 0 0
```

```r
# nombre
table(q1a)
```

```
## q1a
##  1  2  3  4  5  6 
##  8 14 14 10  8  2
```

Q1 avant et après

```r
q1a <- lk.av[, 4, drop = FALSE]
q1p <- lk.ap[, 4, drop = FALSE]
q1 <- cbind(q1p, q1a)
names(q1) <- c("Q1.Ap","Q1.Av")
plot(likert(q1, nlevels = 8))
```

![](likert_files/figure-html/Q1-1.png) 

```r
likert.bar.plot(likert(q1, nlevels = 8), main = "Q1")
```

![](likert_files/figure-html/Q1-2.png) 

```r
likert.heat.plot(likert(q1, nlevels = 8), main = "Q1")
```

![](likert_files/figure-html/Q1-3.png) 

```r
likert.density.plot(likert(q1, nlevels = 8), main = "Q1", warning = FALSE)
```

![](likert_files/figure-html/Q1-4.png) 

```r
summary(likert(q1, nlevels = 8))
```

```
##    Item low neutral high mean  sd
## 1 Q1.Ap  57       0   43  3.8 1.5
## 2 Q1.Av  82       0   18  3.0 1.4
```

```r
# test du chi2 pour comparer avant-après
c <- likert(q1, nlevels = 8)
# c est un objet de type likert dont il faut extraire les données (voir str(c))
d <- c$results[,2:9]
# on regroupe les colonnes 6 et 7 pour avoir des effectifs convenables
d[,6] <-d[,6]+d[,7]
# test en éliminant le colonne 8 qui est nulle
chisq.test(d[, 1:6])
```

```
## 
## 	Pearson's Chi-squared test
## 
## data:  d[, 1:6]
## X-squared = 17, df = 5, p-value = 0.005371
```

Cronbach alpha
==============

On utilise la formule _alpha_ du package _epîcalc_. Calcul du coefficient de Cronbach pour les questions avant / après et pour la totalité des 12 items et les 8 premiers:


```
Loading required package: foreign
Loading required package: survival
Loading required package: MASS
Loading required package: nnet

Attaching package: 'epicalc'

The following object is masked from 'package:likert':

    recode
```

```
Number of items in the scale = 12 
Sample size = 56 
Average inter-item correlation = 0.2722 
 
Cronbach's alpha: cov/cor computed with 'pairwise.complete.obs'
      unstandardized value = 0.8008 
        standardized value = 0.8178 
 
Item(s) reversed: Q11.av, Q12.av 
 
New alpha if item omitted: 
       Reversed Alpha  Std.Alpha r(item, rest)
Q1.av      .    0.7651 0.7827    0.7032       
Q2.av      .    0.7709 0.7869    0.6604       
Q3.av      .    0.7709 0.7903    0.6119       
Q4.av      .    0.7973 0.8138    0.3425       
Q5.av      .    0.7678 0.7817    0.7109       
Q6.av      .    0.7894 0.8066    0.4108       
Q7.av      .    0.7733 0.7943    0.5836       
Q8.av      .    0.7796 0.7985    0.5173       
Q9.av      .    0.7831 0.8037    0.4848       
Q10.av     .    0.809  0.8321    0.1105       
Q11.av     x    0.8235 0.8359    0.0943       
Q12.av     x    0.7999 0.8145    0.3691       
```

```
Number of items in the scale = 8 
Sample size = 56 
Average inter-item correlation = 0.4226 
 
Cronbach's alpha: cov/cor computed with 'pairwise.complete.obs'
      unstandardized value = 0.8446 
        standardized value = 0.8541 
 
Item(s) reversed:  
 
New alpha if item omitted: 
      Reversed Alpha  Std.Alpha r(item, rest)
Q1.av     .    0.8216 0.8305    0.6217       
Q2.av     .    0.8148 0.8229    0.6971       
Q3.av     .    0.821  0.8318    0.619        
Q4.av     .    0.8503 0.8573    0.4194       
Q5.av     .    0.8168 0.8243    0.6869       
Q6.av     .    0.8394 0.8517    0.4763       
Q7.av     .    0.8256 0.8385    0.5841       
Q8.av     .    0.8199 0.8331    0.6274       
```

```
Number of items in the scale = 8 
Sample size = 56 
Average inter-item correlation = 0.5474 
 
Cronbach's alpha: cov/cor computed with 'pairwise.complete.obs'
      unstandardized value = 0.9043 
        standardized value = 0.9063 
 
Item(s) reversed:  
 
New alpha if item omitted: 
      Reversed Alpha  Std.Alpha r(item, rest)
Q1.ap     .    0.8863 0.8889    0.7589       
Q2.ap     .    0.8854 0.8888    0.7693       
Q3.ap     .    0.8886 0.8913    0.738        
Q4.ap     .    0.9043 0.9065    0.5624       
Q5.ap     .    0.8904 0.8906    0.7373       
Q6.ap     .    0.8961 0.8982    0.6493       
Q7.ap     .    0.8925 0.8953    0.6911       
Q8.ap     .    0.8924 0.8943    0.6923       
```

```
Number of items in the scale = 12 
Sample size = 56 
Average inter-item correlation = 0.2931 
 
Cronbach's alpha: cov/cor computed with 'pairwise.complete.obs'
      unstandardized value = 0.8155 
        standardized value = 0.8327 
 
Item(s) reversed: Q12.ap 
 
New alpha if item omitted: 
       Reversed Alpha  Std.Alpha r(item, rest)
Q1.ap      .    0.7765 0.7979    0.7554       
Q2.ap      .    0.7766 0.7994    0.7554       
Q3.ap      .    0.7798 0.8038    0.6912       
Q4.ap      .    0.7968 0.8174    0.5235       
Q5.ap      .    0.7868 0.8019    0.7008       
Q6.ap      .    0.7883 0.8064    0.6404       
Q7.ap      .    0.7802 0.8022    0.7102       
Q8.ap      .    0.7831 0.8031    0.6861       
Q9.ap      .    0.8174 0.8362    0.2894       
Q10.ap     .    0.8276 0.8485    0.0884       
Q11.ap     .    0.8336 0.8447    0.1542       
Q12.ap     x    0.8541 0.8601    -0.0462      
```
La consistance interne parait bonne.

Score sur les 8 premières questions
===================================


```r
lkt$score.av <- apply(lkt[, c(4:11)], 1, sum, na.rm = TRUE)
lkt$score.ap <- apply(lkt[, c(16:23)], 1, sum, na.rm = TRUE)

summary(lkt$score.av)
```

```
##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
##      13      23      30      30      38      50
```

```r
summary(lkt$score.ap)
```

```
##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
##      11      31      36      37      44      55
```

```r
# création d'une colonne delta.score qui fait la différence avant/après. Onconstate que le score peut augmenter, diminuer ou ne pas bouger.
lkt$delta.score <- lkt$score.ap - lkt$score.av

# Comparaison des scores av et pré-briefing ou non
boxplot(score.av ~ PREB, data = lkt)
```

![](likert_files/figure-html/score-1.png) 

```r
t.test(score.av ~ PREB, data = lkt)
```

```
## 
## 	Welch Two Sample t-test
## 
## data:  score.av by PREB
## t = 0.83, df = 53, p-value = 0.4119
## alternative hypothesis: true difference in means is not equal to 0
## 95 percent confidence interval:
##  -2.7  6.4
## sample estimates:
## mean in group N mean in group O 
##              31              29
```

```r
# Comparaison des scores ap et pré-briefing ou non
boxplot(score.ap ~ PREB, data = lkt)
```

![](likert_files/figure-html/score-2.png) 

```r
t.test(score.ap ~ PREB, data = lkt)
```

```
## 
## 	Welch Two Sample t-test
## 
## data:  score.ap by PREB
## t = 0.88, df = 51, p-value = 0.3816
## alternative hypothesis: true difference in means is not equal to 0
## 95 percent confidence interval:
##  -2.9  7.3
## sample estimates:
## mean in group N mean in group O 
##              38              36
```

```r
use(lkt)

# comparaison des scores des différents groupes
boxplot(score.av ~ Groupe_ID, data = lkt)
```

![](likert_files/figure-html/score-3.png) 

```r
boxplot(score.ap ~ Groupe_ID, data = lkt)
```

![](likert_files/figure-html/score-4.png) 

```r
# l'ANOVA confirme que les groupes n'ont pas les mêmes scores
a <- aov(score.av ~ Groupe_ID, data = lkt)
summary(a)
```

```
##             Df Sum Sq Mean Sq F value  Pr(>F)    
## Groupe_ID    1    762     762    13.2 0.00063 ***
## Residuals   54   3119      58                    
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
```

```r
a2 <- aov(score.ap ~ Groupe_ID, data = lkt)
summary(a2)
```

```
##             Df Sum Sq Mean Sq F value Pr(>F)   
## Groupe_ID    1    662     662    8.51 0.0051 **
## Residuals   54   4204      78                  
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
```

```r
# évolution des scores moyens par groupes
tapply(score.av, Groupe_ID, mean)
```

```
##  1  2  3  4  5  6  7  8 
## 36 42 30 31 31 28 27 26
```

```r
tapply(score.ap, Groupe_ID, mean)
```

```
##  1  2  3  4  5  6  7  8 
## 44 48 37 36 36 39 30 34
```

```r
# évolution des scores moyens par groupes et prebriefing
tapply(score.av, list(Groupe_ID, lkt$PREB), mean)
```

```
##    N  O
## 1 36 NA
## 2 NA 42
## 3 NA 30
## 4 31 NA
## 5 31 NA
## 6 28 NA
## 7 NA 27
## 8 NA 26
```

```r
tapply(score.ap, list(Groupe_ID, lkt$PREB), mean)
```

```
##    N  O
## 1 44 NA
## 2 NA 48
## 3 NA 37
## 4 36 NA
## 5 36 NA
## 6 39 NA
## 7 NA 30
## 8 NA 34
```

Information de session
======================

Informations pour le chapitre matériel et méthode.


```
R version 3.1.3 (2015-03-09)
Platform: x86_64-apple-darwin13.4.0 (64-bit)
Running under: OS X 10.10.3 (Yosemite)

locale:
[1] fr_FR.UTF-8/fr_FR.UTF-8/fr_FR.UTF-8/C/fr_FR.UTF-8/fr_FR.UTF-8

attached base packages:
[1] stats     graphics  grDevices utils     datasets  methods   base     

other attached packages:
[1] epicalc_2.15.1.0 nnet_7.3-10      MASS_7.3-42      survival_2.38-3 
[5] foreign_0.8-65   knitr_1.10.5     likert_1.2       xtable_1.7-4    
[9] ggplot2_1.0.1   

loaded via a namespace (and not attached):
 [1] colorspace_1.2-6 digest_0.6.8     evaluate_0.7     formatR_1.2     
 [5] grid_3.1.3       gridExtra_0.9.1  gtable_0.1.2     htmltools_0.2.6 
 [9] labeling_0.3     magrittr_1.5     mnormt_1.5-3     munsell_0.4.2   
[13] parallel_3.1.3   plyr_1.8.3       proto_0.3-10     psych_1.5.4     
[17] Rcpp_0.11.6      reshape_0.8.5    reshape2_1.4.1   rmarkdown_0.7   
[21] scales_0.2.5     splines_3.1.3    stringi_0.5-5    stringr_1.0.0   
[25] tools_3.1.3      yaml_2.1.13     
```

```

To cite R in publications use:

  R Core Team (2015). R: A language and environment for
  statistical computing. R Foundation for Statistical Computing,
  Vienna, Austria. URL http://www.R-project.org/.

A BibTeX entry for LaTeX users is

  @Manual{,
    title = {R: A Language and Environment for Statistical Computing},
    author = {{R Core Team}},
    organization = {R Foundation for Statistical Computing},
    address = {Vienna, Austria},
    year = {2015},
    url = {http://www.R-project.org/},
  }

We have invested a lot of time and effort in creating R, please
cite it when using it for data analysis. See also
'citation("pkgname")' for citing R packages.
```
