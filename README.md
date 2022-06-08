# HOUSE SALES 

<div align="center">
<img src = "https://user-images.githubusercontent.com/94937578/172006534-8ca0f590-ec0c-4f54-a5ca-b43e620b2971.png" width="1000px" />
</div>

## 1. Resumo

- <b>Código no Jupyter Notebook</b>
- <b>Visualização dos dados no Power BI</b>

## 2. Contexto

Supondo hipoteticamente que a House Rocket, uma plataforma digital que tem como modelo de negócio a compra e a venda de imóveis usando tecnologia, desejasse encontrar boas oportunidades de negócio a partir dos imóveis disponíveis no momento para a compra. Sua principal estratégia é comprar boas casas em ótimas localizações com preços baixos e depois revendê-las posteriormente à preços mais altos. No entanto, as casas possuem muitos atributos que as tornam mais ou menos atrativas aos compradores e vendedores e a localização e o período do ano também podem influenciar os preços. O time do negócio não consegue tomar boas decisões de compra sem analisar os dados, mas o portfólio é muito grande, o que levaria muito tempo para fazer o trabalho manualmente.
   
## 3. Problema de negócio

O desafio é organizar e analisar os dados e fornecer uma seleção de imóveis com as melhores condições, demonstrando visualmente as oportunidades para que o time de negócio da House Rocket possa acessar e simular a compra de imóveis com determinadas características e a partir disso tomar suas decisões.

## 4. Planejamento da solução:

- <b>Passo 1:</b> Coletar os dados (Kaggle). 
- <b>Passo 2:</b> Descrever os dados.
- <b>Passo 3:</b> Limpar os dados e criar novos atributos (Feature Engineering).
- <b>Passo 4:</b> Realizar a análise exploratória dos dados e obter a partir disso alguns insights.
- <b>Passo 5:</b> Apresentar os dados referentes aos imóveis selecionados em um dashboard no Power BI.

## 5. Dados:

- Foi utilizado para a análise um conjunto de dados disponibilizado na plataforma Kaggle (https://www.kaggle.com/harlfoxem/housesalesprediction)
- O conjunto de dados contém informações sobre os imóveis vendidos entre maio de 2014 e 2015 em King County (Condado de King), EUA.
- Os atributos dos imóveis apresentados no conjunto de dados são descritos na tabela abaixo.

**Atributo** | **Descrição**
--- | --- 
 `id` | Número de identificação único para cada imóvel
 `date` | Data de venda
 `price` | Preço que a casa está sendo vendida
 `bedrooms` | Número de quartos
 `bathrooms` | Número de banheiros (0.5 = banheiro em um quarto, mas sem chuveiro)
 `sqft_living` | Medida (em pés quadrado) do espaço interior dos apartamentos
 `sqft_lot` | Medida (em pés quadrado) do espaço terrestre
 `floors` | Número de andares do imóvel
 `waterfront` | Variável que indica a presença ou não de vista para o mar (0 = não e 1 = sim)
 `view` | Índice de 0 a 4 que indica a qualidade da vista da propriedade (onde: 0 = baixa e 4 = alta)
 `condition` | Índice de 1 a 5 que indica a condição da casa (onde: 1 = baixo e 5 = alta)
 `grade` | Índice de 1 a 13 que indica a construção e o design do edifício (onde: 13 = baixo, 7 = médio e 13 = alta)
 `sqft_above` | Metragem quadrada do espaço habitacional interior abaixo do nível do solo
 `sqft_basement` | Metragem quadrada do espaço habitacional interior acima do nível do solo
 `yr_built` | Ano de construção de cada imóvel
 `yr_renovated` | Ano de reforma de cada imóvel
 `zipcode` | Código posta da casa
 `lat` | Latitude
 `long` | Longitude
 `sqft_livining15` | Medida (em pés quadrado) do espaço interno de habitação para os 15 vizinhos mais próximo
 `sqft_lot15` | Medida (em pés quadrado) dos lotes de terra dos 15 vizinhos mais próximo
 
 ## 6. Pressupostos:

<b>Algumas suposições foram definidas previamente pelo time de negócio:</b>

- Não há interesse na compra de imóveis com condições ruins e péssimas.
- Não há interesse na compra de imóveis construídos até 1950, pois são muito antigos.
- Pretende-se comprar apenas os imóveis com preço abaixo da média da região.
- Para a venda dos imóveis com condição regular será adicionado 15% ao preço de compra.
- Para a venda dos imóveis com condição boa será adicionado 15% ao preço de compra.
- Para a venda dos imóveis com condição excelente será adicionado 25% ao preço de compra.

 ## 7. Outras suposições:
- Deverá ser indicado se os imóveis são reformados ou não.
- Deverá ser indicado a estação do ano na qual os imóveis foram postos a venda,
- Os imóveis deverão ser classificados de acordo com o ano de construção em: 
  - Antigo (ano de construção <= 2000)
  - Novo (ano de construção > 2000)
- Os imóveis deverão ser classificados de acordo com o tipo de dormitório: 
  - Studio (<= 1 quarto)
  - Apartamento (de 2 a 4 quartos)
  - Casa (>= 4 quartos)

## 8. Principais resultados:

<b>Insights a partir da análise dos dados:</b>

- O número total de imóveis no conjunto de dados é 21435.
- O preço médio de todos os imóveis do conjunto de dados é $541645.37.
- A casa mais antiga do conjunto de dados foi construida no ano de 1900.
- A casa mais nova do conjunto de dados foi construida no ano de 2015.
- O preço dos imóveis está diretamente correlacionado com o tamanho do imóvel, o número de quartos e o número de banheiros.
- Sugere-se que o preço está pouco correlacionado com o tamanho do terreno no qual o imóvel está localizado e ano no qual foi construído.
- O preço médio dos imóveis cresce com a classificação do design da construção, assim como com a classificação da vista.
- Não há muita divergência no preço médio dos imóveis por mês de venda é muito semelhante, assim como também para os imóveis vendidos em cada estação do ano.
- Em geral, os imóveis com cerca de 8 quartos são aqueles que apresentam maior custo médio (embora haja imóveis com mais quartos).
- Em geral, os imóveis com cerca de 7 banheiros são aqueles que apresentam maior custo médio (embora haja imóveis com mais banheiros).
- Há 13911 imóveis com a condição 'regular', 5645 imóveis com a condição igual a 'boa' e 1879 imóveis com a condição 'excelente'. Apesar da maioria dos imóveis apresentar condição "regular", os imóveis com condição "excelente" possuem maior preço médio.
- No conjunto de dados há 12446 imóveis de 1 andar, 8370 imóveis de 2 andares e 619 imóveis de 3 andares. Logo, há mais imóveis com 2 andares e são eles que possuem o maior preço médio dentre as três categorias.
- O número de imóveis novos é 4529, enquanto o número de imóveis antigos é 16906. O preço médio dos imóveis novos é significativamente superior aos dos imóveis antigos.
- Há 910 imóveis que foram reformados e 20525 imóveis que não foram reformados. O preço médio dos imóveis reformados é maior dos que o preço médio dos imóveis antigos.
- Há apenas 163 imóveis com vista para o mar, no entanto o preço médio desses imóveis é maior do que aqueles que não tem vista para o mar.
- Embora estejam disponíveis para a compra 21613 imóveis, apenas 9688 imóveis atingem as exigências do time de negócios.
- Caso a empresa decida adquirir tais imóveis selecionados seu custo total será $3992138389.0, sua receita total com a aquisição será de $4471090112.1 e seu lucro total a partir das vendas dos imóveis será de $4471090112.1.

## 9. Produto final:

- Após a organização dos dados e seleção dos imóveis que atingem as exigências solicitadas, será disponibilizado um dashboard no Power BI com as análises realizadas que poderá ser apresentado diretamente ao time de negócios ou disponibilizado para o acesso individual, no qual será possível simular a compra imóveis (dentre aqueles selecionados) com determinadas características.
