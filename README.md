<h1 align="center">Análise de Dados com Phyton - Equipe de Vendas</h1>

<h2 align="left"> 🎯Desafio </h2> 

Análise Iniciante em Phyton.  

Objetivo: O que fazer para aumentar as vendas? 

Informações: Base de Dados de Vendas - [Vendas.xlsx](https://github.com/Isabella-Bueno/AnalisedeDados_Phyton_AumentodeVendas/files/11782654/Vendas.xlsx)

Empresa: Lojas de Bermudas

<h2 align="left"> 🗂️ Organizando o Desafio </h2> 

► Passo 1 - Trazer sua base de dados para o Python e ver o que tem nela

► Passo 2 - Limpeza e Tratamento

► Passo 3 - Ter um panorama geral

► Passo 4 - Análise dos Dados obtidos 

<h2 align="left"> 1 - Trazer sua base de dados para o Python e ver o que tem nela </h2> 


<h3 align="left">Eu utilizei para esse projeto o Jupyter, e utilizei o seguinte código

  import pandas as pd
  tabela =pd.read_excel("Vendas.xlsx")
  display(tabela)

  ![image](https://github.com/Isabella-Bueno/AnalisedeDados_Phyton_AumentodeVendas/assets/112008347/5deba06f-28c2-497f-8fcc-0435a2b95b94)

  <h2 align="left"> Passo 2 - Limpresa e Tratamento </h2> 
    
  Precisamos sempre verificar se os dados estão todos preenchidos e no formato correto, para isso utilizo o seguinte código
  
  tabela = tabela.dropna()
  display(tabela.info ())
  
  ![image](https://github.com/Isabella-Bueno/AnalisedeDados_Phyton_AumentodeVendas/assets/112008347/d77b9d8f-9e9e-471b-a48d-87e00c59ed67)

  
<h2 align="left"> Passo 3 - Visão Geral | Análise dos dados </h2> 

   A primeira pergunta que me fiz é qual loja está se destacando? 
   Com a função abaixo podemos ver que é a loja Iguatemi Campinas 


  #faturamento por loja
  faturamento_por_loja = tabela [["ID Loja","Valor Final"]].groupby("ID Loja").sum()
  display (faturamento_por_loja)
  ![image](https://github.com/Isabella-Bueno/AnalisedeDados_Phyton_AumentodeVendas/assets/112008347/24353319-72d7-4589-90b7-0762aaf42205)
  
  import plotly.express as px
  grafico = px.bar(tabela, x= "ID Loja", y= "Valor Final")
  grafico.show()
  ![image](https://github.com/Isabella-Bueno/AnalisedeDados_Phyton_AumentodeVendas/assets/112008347/5d68edb9-1236-4329-a4ba-a5c771eeaf3d)

Mas o que essa loja está fazendo diferente das outras lojas?
  
Com a tabela abaixo podemos ver por produto e o produto destaque é a Bermuda Lisa que não se encontra nas demais loja. 
  
  #faturamento por loja
  faturamento_por_produto = tabela [["ID Loja","Produto","Valor Final"]].groupby(["ID Loja","Produto"]).sum()
  display (faturamento_por_produto)
  ![image](https://github.com/Isabella-Bueno/AnalisedeDados_Phyton_AumentodeVendas/assets/112008347/3bd3f379-1207-4173-b5cf-0eec2caf00ce)

  
  <h2 align="left">  Conclusão | Análise dos dados </h2> 
    Sabendo que a Loja destaque é Iguatemi Campinas por conta do produto Bermuda Lisa e as demais lojas não possuem este mesmo produto, podemos sugerir colocar esse mesmo produto nas demais lojas e acompanhar os principais KPIs de Vendas.
  
  
  
