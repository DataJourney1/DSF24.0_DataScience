# DSF24.0_DataScience
Tugas Data Science Digital Skill Fair 24.0 

#Konvenrsi suhu dari celcius(float) ke Fahrenheit (Float)
def celcius_ke_fahrenheit(celcius):
  """
  Fungsi untuk mengkonversi suhu dari Celcius ke Fahrenheit.

  Args:
    celcius: Suhu dalam Celcius (float).

  Returns:
    Suhu dalam Fahrenheit (float).
  """
  fahrenheit = (celcius * 9/5) + 32
  return fahrenheit

# Contoh penggunaan
suhu_celcius = 25.0
suhu_fahrenheit = celcius_ke_fahrenheit(suhu_celcius)

print(f"{suhu_celcius} derajat Celcius sama dengan {suhu_fahrenheit} derajat Fahrenheit.")

#memasukan sebuah bilangan bulat.
# Meminta pengguna memasukkan bilangan bulat
bilangan = int(input("Masukkan bilangan bulat: "))

# Memeriksa apakah bilangan tersebut genap
if bilangan % 2 == 0:
  # Mencetak bahwa bilangan tersebut genap
  print(f"{bilangan} adalah bilangan genap.")
else:
  # Mencetak bahwa bilangan tersebut ganjil
  print(f"{bilangan} adalah bilangan ganjil.")

#LATIHAN IMPORT DAN VISUALISASI DATA
sumber data : https://colab.research.google.com/corgiredirector?site=https%3A%2F%2Fwww.kaggle.com%2Fdatasets%2Fdinanjuliansyah%2Fkecelakaan-jogja%3Fresource%3Ddownload

#menjalankan library pandas
from __future__ import print_function

import pandas as pd
pd.__version__

import pandas as pd
#reading data from a csv file
kecelakaan = pd.read_csv ("/kecelakaan_jogja.csv")
kecelakaan

kecelakaan.info()

kecelakaan.describe()

#grouping and aggregating data
kecelakaan.groupby("Tahun").mean()

kecelakaan.groupby('Tahun').agg(['mean', 'median', 'std'])

Balajar Seaborn
https://colab.research.google.com/corgiredirector?site=https%3A%2F%2Fseaborn.pydata.org%2Ftutorial%2Fintroduction.html

import seaborn as sns
sns.scatterplot(data=kecelakaan, x="Jumlah Pelanggaran Lalu lintas", y="Jumlah Kecelakaan", hue="Tahun")

sns.displot(data=kecelakaan, x="Jumlah Kecelakaan", col="Tahun", kde=True)

sns.catplot(data=kecelakaan, kind="bar", x="Tahun", y="Jumlah Kecelakaan")
