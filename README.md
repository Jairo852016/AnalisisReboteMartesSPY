# Rebote Martes

Analisis de la estrategia Martes de Rebotes del ETF SPY este analisis se realizo tomando los datos desde el año 2014 al año 2020

Estrategia tomada del Club de Inversionistas y de un gran mentor Hyenuk Chu https://www.hyenukchu.com/ https://chu.mx/

El detalle de cada analisis y tratamiento de detos se encuentra en los notebooks que se encuentran en este proyecto. 

1.0 LimpiezaDatos.ipynb: En este archivo se encontrara un detalle de todos procesos realizados para definir la base de datos que se analiza
2.0 AnalisisMartes.ipynb: En este archivo se detalla un conjunto de analisis de los datos enfocandos al movimiento del precio de 
                        los dias Martes, relacion con variacion diaria, ATR, RSI, EMA8, EMA21, MA50, MA200
3.0 AnalisisVLM.ipynb:  En este archivo se detalla el conjunto de analisis para la combinacion de los dias Viernes y Lunes antes del Martes
                        analizado, se estudia las combinaciones que tiene los dias anteriores y los porcentajes para que un dia Martes sea positivo.

    El analisis dio como resultado que el 56,39% de los dias Martes son positivos (181 dias) y el 43.61% son negativos (140 dias), de los cuales se resume de la siguiente manera:
        Precio/EMA8:
                    - en los dias positivos el 82.32%  el precio estuvo sobre la EMA8 y 17.68% el precio estuvo bajo la EMA8

        EMA8/EMA21
                    - en los dias positivos el 72.93%  la EMA8 estuvo sobre la EMA21 y 27.07%  la EMA8 estuvo bajo la EMA21
                    
        EMA21/MA50
                    - en los dias positivos el 72.93%  la EMA21 estuvo sobre la MA50 y 27.07% la EMA21 estuvo bajo la MA50
                    
        MA50/MA200
                    - en los dias positivos el 80.11%  la MA50 estuvo sobre la MA200 y 19.89% la EMA50 estuvo bajo la MA200
                    
        %VariacionDiaria
                    - en los dias positivos el 59.12% el %Variacion esta en el rango de 0 a 0.5% y el 28.18% en el rango de 0.5% a 1%
                    
        ATR
                    - en los dias positivos el 83.98% el ATR estuvo en el rango de 1 a 4.5 y 12.15% en el rango de 4.5 a 7
                    
        RSI
                    - en los dias positivos el 39.78% el RSI estuvo en el rango de 60 a 72 y 38.12% en el rango de 47 a 60
                    

Generamos una tabla pivote para analizar la combinacion del dia Viernes y Lunes anteriores al Martes 
    Cuando los dias Martes son positivo : 
    Vienes Positivo y Lunes positivo   35.78%
    Viernes Negativo y Lunes positivo  20.59%
    Viernes Positivo y Lunes negativo  22.06%
    Viernes Negativo y Lunes negativo  21.57%


CONCLUCION

El analisis realizado nos dio como resultado que el 56.39% de los dias Martes son positivos, las caracteristicas de estos dias fueron:
            - El 82% el precio estuvo sobre EMA8
            - El 73% la EMA8 estuvo sobre EMA21
            - El 73% la EMA21 estuvo sobre MA50
            - El 80% la MA50 estuvo sobre MA200
            - El 59% la %Variacion estuvo entre 0 a 0.5%
            - El 84% el ATR entre 1 a 4.5
            - El 79% el RSI estuvo 47 a 72
        La Combinacion del Viernes y Lunes anteriores al Martes :
             Vienes Positivo y Lunes positivo   35.78%
             Viernes Negativo y Lunes positivo  20.59%
             Viernes Positivo y Lunes negativo  22.06%
             Viernes Negativo y Lunes negativo  21.57% 

RECOMENDACIONES

- Hacer traiding es muy riesgoso, por favor cuida tu capital y maneja tu riesgo, este analisis solo es sobre los datos pasados, no son
  predicciones del movimiento del precio. 

- Es importante en futuros analisis revisar comportamientos del precio en temporalidades de 30 minutos para poder identificar horarios de
  rebotes 

- Generar reportes visuales en Tableu o PowerBI

- Realizar analisis de los contratos de opciones CALL en los dias Martes.

      
  
## Installation guide

Please read [install.md](install.md) for details on how to set up this project.

## Project Organization

    ├── LICENSE
    ├── tasks.py           <- Invoke with commands like `notebook`.
    ├── README.md          <- The top-level README for developers using this project.
    ├── install.md         <- Detailed instructions to set up this project.
    ├── data
    │   ├── external       <- Data from third party sources.
    │   ├── interim        <- Intermediate data that has been transformed.
    │   ├── processed      <- The final, canonical data sets for modeling.
    │   └── raw            <- The original, immutable data dump.
    │
    ├── models             <- Trained and serialized models, model predictions, or model summaries.
    │
    ├── notebooks          <- Jupyter notebooks. Naming convention is a number (for ordering),
    │                         the creator's initials, and a short `-` delimited description, e.g.
    │                         `1.0-jqp-initial-data-exploration`.
    │
    ├── references         <- Data dictionaries, manuals, and all other explanatory materials.
    │
    ├── reports            <- Generated analysis as HTML, PDF, LaTeX, etc.
    │   └── figures         <- Generated graphics and figures to be used in reporting.
    │
    ├── environment.yml    <- The requirements file for reproducing the analysis environment.
    │
    ├── .here              <- File that will stop the search if none of the other criteria
    │                         apply when searching head of project.
    │
    ├── setup.py           <- Makes project pip installable (pip install -e .)
    │                         so final_project can be imported.
    │
    └── final_project               <- Source code for use in this project.
        ├── __init__.py    <- Makes final_project a Python module.
        │
        ├── data           <- Scripts to download or generate data.
        │   └── make_dataset.py
        │
        ├── features       <- Scripts to turn raw data into features for modeling.
        │   └── build_features.py
        │
        ├── models         <- Scripts to train models and then use trained models to make
        │   │                 predictions.
        │   ├── predict_model.py
        │   └── train_model.py
        │
        ├── utils          <- Scripts to help with common tasks.
            └── paths.py   <- Helper functions to relative file referencing across project.
        │
        └── visualization  <- Scripts to create exploratory and results oriented visualizations.
            └── visualize.py

---