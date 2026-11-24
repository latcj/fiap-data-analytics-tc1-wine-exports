# Tech Challenge 1 - Exportações de vinhos brasileiros

Quais países mais compraram vinhos do Brasil entre 2009 e 2023? O projeto usa os dados da Embrapa para comparar destinos pelo valor exportado em dólares e distinguir mercados com vendas recorrentes daqueles que se destacaram em poucos anos.

[Consultar o notebook com gráficos e tabelas](notebooks/tech_challenge_1.ipynb) · [Baixar o relatório HTML](reports/exportacoes-de-vinhos.html?raw=1)

## Objetivo

Identificar os principais mercados de destino e investigar como as exportações evoluíram ao longo de 15 anos. A análise calcula o crescimento acumulado e a taxa de crescimento anual composta (CAGR) dos 20 maiores destinos em receita. Para mercados selecionados, ajusta uma regressão linear por país e projeta valores anuais de 2024 a 2028.

## Resultados

| Destino | Evidência no período |
| --- | --- |
| Paraguai | Liderou o valor acumulado com US$ 42,86 milhões. As exportações passaram de US$ 392 mil em 2009 a US$ 5,52 milhões em 2023. |
| Rússia | Ficou em segundo lugar com US$ 23,15 milhões. O gráfico anual mostra como as vendas se concentraram em poucos anos. |
| Estados Unidos | O terceiro maior destino acumulou US$ 9,31 milhões. |
| Uruguai e Haiti | Entre os 20 maiores destinos, registraram as maiores taxas de crescimento anual composto, de 47,40% e 42,94%, respectivamente. O primeiro ano com exportação positiva foi 2010 no Uruguai e 2009 no Haiti. |

O CAGR usa os primeiros e últimos anos com receita positiva em cada país. As projeções também usam os anos com valores positivos e limitam as estimativas inferiores a zero a US$ 0. Os valores a partir de 2024 representam extrapolações do histórico encerrado em 2023.

## Dados

Os três arquivos abrangem 1970 a 2023. Em `ExpVinho.csv`, cada linha representa um destino e cada ano aparece em duas colunas consecutivas, uma para a quantidade em quilogramas e outra para o valor em dólares. A Embrapa chama essa tabela de *Vinhos de mesa* e informa que a série inclui todos os tipos de vinho dos códigos 2204.21 e 2204.29 desde 1996. O notebook reorganiza esses pares antes de calcular os indicadores. As tabelas de produção e comercialização do Rio Grande do Sul serviram à exploração inicial. Os resultados por destino usam a tabela de exportações. [Fonte dos dados — Embrapa Uva e Vinho, VitiBrasil](https://vitibrasil.cnpuv.embrapa.br/index.php?opcao=opt_06)

## Tecnologias utilizadas

Python 3.12, JupyterLab, pandas e NumPy para a preparação dos dados, Matplotlib e Seaborn para os gráficos e scikit-learn para as regressões.

## Estrutura do projeto

```text
data/
  Comercio.csv
  ExpVinho.csv
  Producao.csv
notebooks/
  tech_challenge_1.ipynb
reports/
  exportacoes-de-vinhos.html
requirements.txt
```

## Execução local

1. Na raiz do repositório, crie um ambiente com Python 3.12 usando `python -m venv .venv`.
2. Ative o ambiente com `.\.venv\Scripts\Activate.ps1` no PowerShell ou `source .venv/bin/activate` no Linux e no macOS.
3. Instale as dependências e abra o notebook.

```shell
python -m pip install -r requirements.txt
python -m jupyterlab notebooks/tech_challenge_1.ipynb
```

No JupyterLab, selecione **Run → Run All Cells** para recriar os gráficos e as tabelas. Para ler o relatório sem instalar Python, baixe o HTML e abra-o no navegador.

## Autor

Luiz Carvalho · Pós-graduação em Data Analytics — FIAP. [Perfil no GitHub](https://github.com/latcj)
