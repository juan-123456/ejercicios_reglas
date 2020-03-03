# ejercicios_reglas

+ First we add our libraries to then load the data from the link and it will show us the data table

import pandas as pd
df_relinc=pd.read_csv("https://raw.githubusercontent.com/juan-123456/nose/master/README.csv")
df_relinc.head():  

+ what we do is add the columns so that the row is understood which is, as are 3 rows we add 3 names with their variables

df_relinc=df_relinc.melt(id_vars=["personas"],var_name=["dinero"],value_name="debe")
df_relinc.head()

+ lo que hacemos es que muestra ya de forma ordenada como se ve con sus columnas ya ordenadas.

df_relinc=(df_relinc.pivot_table(index = "personas", columns = "dinero", values = "debe")
   .reset_index() 
   .rename_axis(None, axis = 1))
df_relinc.head()
