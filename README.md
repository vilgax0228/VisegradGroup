## Introdução: Visegrad Group
The dataset concerns listed companies of the Visegrad Group (Czech Republic, Hungary, Poland, Slovakia). The research period covers data for quarterly analysis(Q1 2017–Q1 2021), and yearly analysis 2017–2020. We computed 82 indicators.

Data concerns 6 sectors (S): 1. Transportation and warehousing; 2. Wholesale trade; 3. Manufacturing; 4. Retail trade; 5. Energy; 6. Construction.

## Formulate your Question
Queremos classificar os setores em diferentes grupos e poder prever as colunas faltantes.

Como temos 82 indicadores no total, nosso objetivo aqui vai ser selecionar os indicadores mais importantes para que seja feita a classificação.

## Read in your Data
O arquivo está em formato ARFF.
```R
viseg_group = read.arff("2017 Q1.arff")
```

## Check the Packaging
install.packages(foreign)
library(dplyr), library(ggplot2), (...)

## Run str()
str(viseg_group)

## Look at the top and the bottom of your data
head(viseg_group)
tail(viseg_group)

## Look at your n's


## ETL process
```R
viseg_group_new = viseg_group[!apply(viseg_group == "m", 1, any), ]  # Remover linhas com valores "m"
dim(viseg_group_new)  # Checar número de linhas e colunas
```

```R
pais = table(df$Country)


# Contagem das observações por país
country_count <- table(df$Country)

setor = table(df$X73)
setor
sector_df <- as.data.frame(setor)
sector_df[sector_df == "m"] = NA

sector_df

table(df$S)  # mudar 1,2,...,6 para os nomes dos setores correspondentes

table(df_clean$X1)  # importante esse cara aqui



# Transformar em data.frame para o ggplot
country_df <- as.data.frame(pais)

# Criar o gráfico
ggplot(country_df, aes(x = Var1, y = Freq, fill = Var1)) +
  geom_bar(stat = "identity") +
  labs(x = "País", y = "Frequência", title = "Número de Observações por País") +
  theme_minimal()

df$Setor <- factor(df$S, 
                   levels = c(1, 2, 3, 4, 5, 6),
                   labels = c("Transportation and warehousing", "Wholesale trade", "Manufacturing", "Retail trade", "Energy", "Construction"))
df$Setor

```

![Rplot08](https://github.com/user-attachments/assets/358feea5-0cb9-4cf8-9e70-d4ed141c01a7)

```R
barplot(table(df$Setor), 
        main = "Distribuição dos Setores",
        xlab = "Setores",
        ylab = "Frequência",
        col = rainbow(6))
```

![Rplot09](https://github.com/user-attachments/assets/6f24039a-539b-41ff-9153-f7d08f198329)

















