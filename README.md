# Mulheres na Tecnologia da Informação: perfil profissional, cargos e remuneração no mercado brasileiro

Repositório do Trabalho de Conclusão de Curso (TCC) do curso de Análise e Desenvolvimento de Sistemas do IFNMG – Campus Almenara.

**Autora:** Jaiane Gonçalves de Sousa
**Orientadora:** Suzana Viana Mota

## Sobre o projeto

Este trabalho descreve e compara a participação feminina, os cargos e a remuneração de homens e mulheres no mercado brasileiro de Tecnologia da Informação, a partir de duas pesquisas de mercado de 2021 a 2025: o **Código Fonte TV (CFTV)**, que cobre a TI em geral, e o **State of Data Brazil (SoD)**, que cobre a área de Dados. A análise de cargos é feita apenas no SoD, pois o CFTV não cruza cargo com gênero.

Os resultados descrevem os respondentes de cada edição e não representam toda a população de profissionais de TI.

## Fontes de dados

| Fonte | Público | Tipo de dado | Edições |
|---|---|---|---|
| Código Fonte TV (CFTV) | TI em geral | Painéis com gráficos (sem microdados) | 2021–2025 |
| State of Data Brazil (SoD) | Área de Dados | Microdados em CSV | 2021–2025 |

**CFTV:** https://pesquisa.codigofonte.com.br (painéis acessados em 17/10/2026).

**SoD (conjuntos de dados no Kaggle):**
- https://www.kaggle.com/datasets/datahackers/state-of-data-2022
- https://www.kaggle.com/datasets/datahackers/state-of-data-brazil-2023
- https://www.kaggle.com/datasets/datahackers/state-of-data-brazil-20242025
- https://www.kaggle.com/datasets/datahackers/state-of-data-brazil-2025-2026

## Conteúdo do repositório

| Arquivo | Descrição |
|---|---|
| `ANALISE_DADOS.ipynb` | Notebook (Google Colab) com toda a análise. Parte 1: SoD (2021–2025). Parte 2: CFTV (geral e por área de atuação). Parte 3: comparação entre as pesquisas. Ao final, correção dos salários pelo IPCA. |
| `Rastreabilidade_CFTV.xlsx` | Registro de cada valor extraído dos 51 painéis do CFTV: ano, área, URL, número de participantes, percentuais por gênero, altura das barras por faixa salarial, data de acesso e forma de extração. |

## Como executar

1. Abra o notebook no Google Colab.
2. Salve os arquivos do SoD (`Dados_2021.csv` a `Dados_2025.csv`) em uma pasta do seu Google Drive e ajuste o caminho na variável `PASTA` do notebook.
3. Execute: *Ambiente de execução → Executar tudo*.

Os dados do CFTV já estão inseridos no notebook e documentados na planilha de rastreabilidade.

**Bibliotecas:** Python, Pandas, NumPy, Matplotlib e SciPy.

## Métodos

- **Salário estimado:** como os salários são informados em faixas, utiliza-se o ponto médio de cada faixa (R$ 25.000 para as faixas acima de R$ 20.000 no CFTV).
- **Lacuna salarial:** (média dos homens − média das mulheres) ÷ média dos homens, em percentual.
- **Correção pelo IPCA:** valores corrigidos para dezembro de 2025, usando a série 433 do Banco Central (IBGE) e o mês central do período de coleta de cada edição como referência. A lacuna percentual dentro de um mesmo ano não se altera.
- **CFTV:** o número de pessoas por faixa é estimado a partir da altura das barras dos gráficos, do percentual de cada gênero e do total de participantes.
- **Intervalos de confiança:** bootstrap com semente fixa (42), com 5.000 sorteios no SoD e 3.000 no CFTV. Na análise por área do CFTV, só são calculados para áreas com pelo menos 100 mulheres.
- **Testes estatísticos (SoD):** Welch (comparação de médias), Mann-Whitney (comparação de posições) e d de Cohen (tamanho do efeito).
- **Comparação entre as pesquisas:** descritiva. O teste qui-quadrado é usado apenas como indicativo para a participação feminina.

## Limitações

- Dados de adesão voluntária (autosseleção): não representam toda a população de profissionais de TI.
- No CFTV, os dados vêm de gráficos e as contagens por faixa salarial são estimadas.
- Os salários são aproximados pelo ponto médio das faixas.
- As pesquisas têm públicos, amostras e faixas salariais diferentes, o que limita a comparabilidade.
- O CFTV não permite cruzar cargo ou senioridade com gênero, então as diferenças salariais observadas não controlam essas variáveis.
