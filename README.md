# Mulheres na Tecnologia da Informação: perfil profissional, cargos e remuneração no mercado brasileiro

Repositório do Trabalho de Conclusão de Curso (TCC) de Análise e Desenvolvimento de Sistemas, IFNMG – Campus Almenara.
Autora: Jaiane Gonçalves de Sousa · Orientadora: Suzana Viana Mota

## Sobre o projeto
O meu TCC analisa a participação das mulheres na Tecnologia da Informação, comparando representatividade, cargos e remuneração com base nas pesquisas State of Data Brazil (SoD) e Código Fonte TV (CFTV).
## Fontes de dados
| Fonte | Público | Tipo de dado | Edições |
|---|---|---|---|
| Código Fonte TV (CFTV) | TI em geral | Painéis com gráficos (sem microdados) | 2021–2025 |
| State of Data Brazil (SoD) | Área de Dados | Microdados em CSV | 2021–2025 |

- CFTV: https://pesquisa.codigofonte.com.br (acessado em 17/10/2026).
- SoD: https://www.kaggle.com/datasets/datahackers/state-of-data-2022
https://www.kaggle.com/datasets/datahackers/state-of-data-brazil-2023
https://www.kaggle.com/datasets/datahackers/state-of-data-brazil-20242025
https://www.kaggle.com/datasets/datahackers/state-of-data-brazil-2025-2026
## Conteúdo do repositório
- `ANALISE_DADOS.ipynb`: notebook (Google Colab) com a análise. Parte 1: SoD;
  Parte 2: CFTV (geral e por área); Parte 3: comparação; e correção pelo IPCA.
- `Rastreabilidade_CFTV.xlsx`: registro de cada valor extraído dos painéis do
  CFTV (51 painéis), com URL, data de acesso e forma de extração.

## Como executar
1. Abra o notebook no Google Colab.
2. Coloque os CSVs do SoD (`Dados_2021.csv` a `Dados_2025.csv`) numa pasta do seu Google Drive e ajuste o caminho na variável `PASTA` do notebook.
3. Execute: Ambiente de execução → Executar tudo.

Bibliotecas: Python, Pandas, NumPy, Matplotlib, SciPy [confira se usou outras].

## Métodos
[Uma linha cada: lacuna salarial; correção pelo IPCA (data-base dez/2025);
bootstrap (semente 42; 5.000 sorteios no SoD e 3.000 no CFTV); testes de Welch e
Mann-Whitney e d de Cohen (SoD); qui-quadrado como indicativo.]

## Limitações
- Dados de adesão voluntária: os resultados descrevem os respondentes de cada
  edição e não representam toda a população de profissionais de TI.
- No CFTV, as contagens por faixa salarial são estimadas a partir dos gráficos.
- Os salários são estimados pelo ponto médio das faixas.
- A comparação entre as pesquisas é descritiva e sujeita a limitações de
  comparabilidade.
