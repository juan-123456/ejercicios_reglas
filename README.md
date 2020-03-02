# ejercicios_reglas

import pandas as pd
df_relinc=pd.read_csv("https://raw.githubusercontent.com/juan-123456/nose/master/README.csv")
df_relinc.head(): 

df_relinc=df_relinc.melt(id_vars=["personas"],var_name=["dinero"],value_name="debe")
df_relinc.head()

df_relinc=(df_relinc.pivot_table(index = "personas", columns = "dinero", values = "debe")
   .reset_index() 
   .rename_axis(None, axis = 1))
df_relinc.head()
