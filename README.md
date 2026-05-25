# Correlacionando Obesidade com Renda

Análise exploratória e estatística da relação entre obesidade mundial e PIB per capita, cobrindo 193 países ao longo de quatro décadas.

---

## Sobre o projeto

Este projeto investiga se, e em que medida, a renda per capita de um país explica seus índices de obesidade.
A análise combina dois datasets públicos do Kaggle, aplica tratamento e interpolação de dados,
e conclui com correlação de Pearson e regressão linear simples para quantificar a relação entre as variáveis.

A hipótese inicial era de que países mais ricos teriam maiores índices de obesidade. Os resultados confirmaram essa relação,
mas revelaram que ela é mais fraca do que o esperado, e que fatores culturais e geográficos têm peso explicativo superior ao econômico em vários casos.

---

## Fontes de dados

| Dataset | Período | Fonte |
|---|---|---|
| Obesity among adults by country | 1975–2016 | Kaggle |
| GDP Per Person | 1901–2011 | Kaggle |

Ambos os datasets são públicos e estão disponíveis no Kaggle

---

## Bibliotecas utilizadas

```python
pandas
numpy
matplotlib
seaborn
plotly
scipy
```

---

## Etapas da análise

**1. Manipulação do dataset de obesidade**
- Limpeza e conversão da coluna `Obesity (%)` de string para float
- Conversão da coluna `Year` para inteiro

**2. Análise descritiva**
- Média de obesidade por sexo no mundo em 2015
- 5 países com maior e menor crescimento absoluto nos índices de obesidade (1975–2016)
- Países com maiores e menores índices de obesidade em 2015
- Diferença média percentual entre homens e mulheres no Brasil
- Evolução temporal da obesidade por sexo no mundo (gráfico de linhas)
- Mapa coroplético da obesidade mundial em 2015

**3. Manipulação do dataset de GDP**
- Limpeza e conversão de tipos
- Interpolação linear para preencher anos ausentes entre países
- Criação de grade completa país × ano (1901–2011)
- Análise do crescimento do PIB por região no século XX

**4. Merge e correlação**
- Inner join entre os dois datasets por país e ano
- Correlação de Pearson entre GDP per capita e obesidade
- Regressão linear simples com visualização e anotação de outliers

---

## Principais resultados

**Diferença de obesidade por sexo (mundo, 2015)**
| Grupo | Obesidade média |
|---|---|
| Feminino | 22,9% |
| Ambos os sexos | 19,5% |
| Masculino | 15,9% |

Mulheres apresentam índices consistentemente superiores ao longo de todo o período analisado,
com diferença de 6,18 pontos percentuais em relação aos homens, padrão explicado por fatores hormonais,
gasto energético diferencial e comportamentais.

**Países com maior crescimento de obesidade (1975–2016)**

| País | Variação (p.p.) |
|---|---|
| Tuvalu | +33,7 |
| Niue | +31,1 |
| Kiribati | +30,1 |
| Tonga | +28,3 |
| Cook Islands | +27,9 |

Todos microestados insulares do Pacífico, com alta dependência de importação de alimentos ultraprocessados.

**Países com menor crescimento de obesidade (1975–2016)**

| País | Variação (p.p.) |
|---|---|
| Vietnã | +2,0 |
| Singapura | +3,1 |
| Japão | +3,3 |
| Bangladesh | +3,4 |
| Timor-Leste | +3,6 |

Países asiáticos continentais com dieta tradicional preservada.

**Correlação GDP × Obesidade (2005)**

| Métrica | Valor |
|---|---|
| Pearson r | 0,32 |
| p-value | ≈ 0 |
| R² | 0,102 |

A correlação é estatisticamente real (p ≈ 0), mas de baixo poder explicativo isolado, GDP per capita explica apenas 10,2% da variação global nos índices de obesidade.

---

## Conclusão

GDP per capita é um preditor real, porém fraco e incompleto da obesidade. A regressão linear e a análise de outliers revelaram dois padrões que fogem ao modelo:

- **Japão e Singapura** (alto GDP, baixa obesidade): cultura alimentar tradicional funciona como fator protetor mesmo sob alta renda e globalização
- **Nauru, Tuvalu e ilhas do Pacífico** (baixo GDP, alta obesidade): isolamento geográfico e dependência de ultraprocessados importados são preditores mais fortes do que a renda per capita

Fatores culturais, geográficos e alimentares têm peso explicativo superior ao econômico na maioria dos casos analisados.
Um modelo preditivo robusto exigiria variáveis adicionais como padrão alimentar regional, índice de urbanização e acesso a alimentos naturais,
o que abre caminho para análises futuras com datasets complementares.

---

## Como executar

```bash
# Clone o repositório
git clone https://github.com/seu-usuario/analise-de-obesidade-e-pib-per-capita.git

# Instale as dependências
pip install pandas numpy matplotlib seaborn plotly scipy

# Abra o notebook
jupyter notebook project_relating_obesity_gdp.ipynb
```

---

## Autor
Samuel Archila
Linkedin: www.linkedin.com/in/samuelarchila

