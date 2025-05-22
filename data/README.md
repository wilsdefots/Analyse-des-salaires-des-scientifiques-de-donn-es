# Les données
salaires <- read.csv("DataScience_salaries_2024.csv")

## nom du fichier de données : Salaires

Dictionnaire des données

1. **work_year** (entier): l'année de travail (ex : 2021)
2. **experience_level**  (categorielle): le niveau d'expérience de l'employé, avec des codes tels que :
   - **EN** : Entry-level (débutant),
   - **MI** : Mid-level (intermédiaire),
   - **SE** : Senior,
   - **EX** : Expert
3. **employment_type** (categorielles): le type d'emploi (FT pour temps plein, FL pour freelance)
4. **job_title** (categorielle): le titre du poste occupé (ex : "Data Scientist")
5. **salary** (continue) : le salaire annuel dans la devise locale (ex : 3 040 000 CLP).
6. **salary_currency**(facteur) : la devise du salaire (CLP, HUF, INR)
7. **salary_in_usd** (continue) : le salaire converti en dollars américains pour uniformiser les montants
8. **employee_residence** (categorielle): le pays de résidence de l'employé (CL pour Chili, HU pour Hongrie).
9. **remote_ratio**(continue) : le pourcentage de télétravail (ex 100 pour travail à distance complet)
10. **company_location** (categorielle): le pays où se situe l'employeur (CL pour Chili, US pour États-Unis)
11. **company_size**(categorielle) : la taille de l'entreprise indiquée par des lettres :
    - **S** : Petite,
    - **M** : Moyenne,
    - **L** : Grande entreprise
    
    glimpse(salaires)
