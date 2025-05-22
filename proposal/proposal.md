Proposition de projet
================
1.  Wilson FOTSING ;
2.  Coumba Diop  
3.  Anais Nikiema  
4.  Blaise-Pascal Guibony

``` r
library(tidyverse)
```

    ## ── Attaching core tidyverse packages ──────────────────────── tidyverse 2.0.0 ──
    ## ✔ dplyr     1.1.4     ✔ readr     2.1.5
    ## ✔ forcats   1.0.0     ✔ stringr   1.5.1
    ## ✔ ggplot2   3.5.1     ✔ tibble    3.2.1
    ## ✔ lubridate 1.9.3     ✔ tidyr     1.3.1
    ## ✔ purrr     1.0.2     
    ## ── Conflicts ────────────────────────────────────────── tidyverse_conflicts() ──
    ## ✖ dplyr::filter() masks stats::filter()
    ## ✖ dplyr::lag()    masks stats::lag()
    ## ℹ Use the conflicted package (<http://conflicted.r-lib.org/>) to force all conflicts to become errors

``` r
library(broom)
library(knitr)
```

## 1. Introduction

Avec l’affluence de plus en plus grandissante des données et l’avénement
du big data, le métier de scientifique de données ne cesse de s’imposer
dans les entreprises. Et la demande est grandissante au fil des années.
Sans compter les multiples mesures que le gouvernement met en place pour
inciter les gens à s’investir dans les recherches en intelligence
artificielle. Les recruteurs offrent des salaires concurentiels pour
s’attirer les services des meilleurs talents du domaine.

Ceci étant dit, comme dans tout autre domaine, les rémunérations dans le
domaine de la science des données varient en fonction de l’expérience,
du nombre d’années d’expériences, de la formation et de bien d’autres
facteurs.

Tout cela nous amène à nous poser les questions suivantes :

1.  Quels sont les domaines les mieux rémunérés dans la science des
    données ?

2.  Comment évolue le salaire des scientifiques des données au fil des
    années et selon le domaine ?

3.  Est-il rentable de se spécialiser dans les sciences des données ?

4….

### 2. Les données

#### A propos de l’auteur

Le jeu de donnée utilisé pour cette étude se nomme
**“DataScience_salaries_2024”.** il est disponible via le lien suivant :

*<https://www.kaggle.com/datasets/yusufdelikkaya/datascience-salaries-2024?select=DataScience_salaries_2024.csv>*

Il a été publié dans le site le 23 aout 2024 par le scientifique des
données Yusuf Delikkaya. Nous sommes le 29 aout 2024, soit 6 jours
seulement après sa publication, mais on compte déjà 5076 vues et 1301
téléchargements : ce qui montre l’intérêt que les gens portent sur le
salaire des scientifiques de données et, la pertinence de notre étude.

# Description

Le paragraphe qui suit a été inspiré de la page de l’auteur.

L’ensemble de données utilisé dans cette analyse comprend des données
anonymisées sur les emplois en science des données.

Il pourra aider à comparer les salaires, à comprendre l’impact de
facteurs tels que le niveau d’expérience et la taille de l’entreprise
sur la rémunération, et à éclairer les décisions de carrière dans le
domaine de la science des données.

# le nombre d’enregistrements

    ## [1] 14838

Le jeu de données comprend *14838* enregistrements collectés à partir de
diverses sources, notamment des enquêtes, des offres d’emploi et des
archives publiques.

# Les variables

    ## [1] 11

    ## Rows: 14,838
    ## Columns: 11
    ## $ work_year          <int> 2021, 2021, 2020, 2021, 2022, 2021, 2021, 2022, 202…
    ## $ experience_level   <chr> "MI", "MI", "MI", "MI", "SE", "MI", "SE", "EN", "EX…
    ## $ employment_type    <chr> "FT", "FT", "FT", "FT", "FT", "FT", "FT", "FT", "FT…
    ## $ job_title          <chr> "Data Scientist", "BI Data Analyst", "Data Scientis…
    ## $ salary             <int> 30400000, 11000000, 11000000, 8500000, 7500000, 700…
    ## $ salary_currency    <chr> "CLP", "HUF", "HUF", "JPY", "INR", "JPY", "INR", "H…
    ## $ salary_in_usd      <int> 40038, 36259, 35735, 77364, 95386, 63711, 94665, 17…
    ## $ employee_residence <chr> "CL", "HU", "HU", "JP", "IN", "JP", "IN", "HU", "IN…
    ## $ remote_ratio       <int> 100, 50, 50, 50, 50, 50, 50, 100, 50, 50, 50, 0, 0,…
    ## $ company_location   <chr> "CL", "US", "HU", "JP", "IN", "JP", "IN", "HU", "IN…
    ## $ company_size       <chr> "L", "L", "L", "S", "L", "S", "L", "M", "L", "L", "…

    ##  [1] "work_year"          "experience_level"   "employment_type"   
    ##  [4] "job_title"          "salary"             "salary_currency"   
    ##  [7] "salary_in_usd"      "employee_residence" "remote_ratio"      
    ## [10] "company_location"   "company_size"

Notre jeu contient *11* variables.

## 3. Plan d’analyse de données

1.  **Analyse exploratoire des données**

    - Élimination des variables inutiles s’il y a lieu (ex
      *salary_currency*) ;
    - Statistiques descriptives (Calculer les valeurs moyennes,
      médianes, minimums, maximums,etc.) ;
    - Visualisations de distribution ;  
    - Analyse univariée (Histogrammes, Boites à moustaches) ;

2.  **Analyse des salaires en fonction de divers facteurs**

    - Impact de l’expérience
    - Analyse par localisation
    - Type d’emploi et salaire
    - Analyse de la taille des entreprises
    - Ratio de télétravail

3.  **Études croisées et corrélations**

    - Analyse croisée de variables et droites de corrélation linéaires ;
    - Coefficient de correlation, interprétation ; -Analyse : Droites de
      corrélation linéaire ;

4.  **Modélisation statistique **

    - Régression linéaire ;
    - Modèles prédictifs ;

5.  **Synthèse**
