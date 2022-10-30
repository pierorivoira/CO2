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
# output
/LAB/CO2

# per importare da un drive locale 
from google.colab import files

# selezionare il file da caricare: <CO2.xlsx>
uploaded = files.upload()

# visualizzare il contenuto della dir corrente
!ls
# output
CO2.xlsx

# leggere il foglio di calcolo di excel (che contiene i dati) in un data frame
excel_data_df = pd.read_excel('CO2.xlsx', sheet_name='CO2')

# rinominare il data frame
df = excel_data_df

# verificare il tipo di struttura dati di df
type(df)
# output
pandas.core.frame.DataFrame

# costruire il grafico

df.plot(xlabel='Anno', ylabel='Concentrazione atmosferica di CO2 (ppm)')


