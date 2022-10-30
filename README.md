COSTRUIRE UN GRAFICO DELLA SERIE TEMPORALE DELLA CONCENTRAZIONE ATMOSFERICA DI CO2
MISURATA TRAMITE ICE CORES CON PYTHON E COLAB (https://colab.research.google.com)


FONTE DEI DATI: https://www1.ncdc.noaa.gov/pub/data/paleo/icecore/antarctica/law/law2006.txt

SCARICARE I DATI DA:
https://github.com/pierorivoira/CO2/blob/main/CO2.xlsx

# questo è un commento! (non un comando da digitare in colab)

pip install openpyxl

import os
import matplotlib.pyplot as plt
import pandas as pd

# creare la cartella <LAB/CO2>
!mkdir -p LAB/CO2

# cambiare la directory (cartella) attuale in <LAB/CO2>
os.chdir('LAB/CO2')

# controllare la dir attuale (o corrente)
os.getcwd()
/LAB/CO2

from google.colab import files
uploaded = files.upload()

# selezionare il file da caricare: <CO2.xlsx>

# visualizzare il contenuto della dir corrente
!ls
CO2.xlsx

excel_data_df = pd.read_excel('CO2.xlsx', sheet_name='CO2')
df = excel_data_df

# verificare il tipo di struttura dati di df
type(df)
pandas.core.frame.DataFrame

# costruire il grafico

df.plot(xlabel='Anno', ylabel='Concentrazione atmosferica di CO2 (ppm)')


