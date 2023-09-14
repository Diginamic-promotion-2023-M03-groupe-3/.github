# .github

## Présentation

Ici existe l’organisation initiée par le groupe 3 de la promotion
**[Diginamic](https://www.diginamic.fr/) 2023 M03**.
Elle a pour but de travailler sur le projet « Fil rouge : Qualité de l’air »
alias **AQI Project**.

Ce projet est né de la collaboration entre
[FYHenry](https://github.com/FYHenry),
[HassAllali](https://github.com/HassAllali),
[NicolasSoulay](https://github.com/NicolasSoulay) et
[melinasim](https://github.com/melinasim).

## Procédure

Pour essayer le projet dans une distribution comme Debian:

```sh
#!/usr/bin/env bash
# Préparation des exécutables
git clone https://github.com/Diginamic-promotion-2023-M03-groupe-3/aqi-project-frontend.git
git clone https://github.com/Diginamic-promotion-2023-M03-groupe-3/aqi-project-backend.git
cd aqi-project-backend/
mvn package
mariadb --user=dev --password=dev \
  --host=127.0.0.1 --database=aqi_project \
  < ./dump-aqi_project-202309111753.sql > /dev/null
cd ../aqi-project-frontend/
npm install
cd ../
```

Reste à exécuter dans des shells séparés ces deux commandes:

```sh
cd aqi-project-backend/; java -jar aqi-project-backend-1.0.0-SNAPSHOT.jar
```

```sh
cd aqi-project-frontend/; ng serve --open
```
