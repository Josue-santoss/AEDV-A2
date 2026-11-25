# Dinâmica da Criminalidade no Rio de Janeiro: Uma Análise Integrada Sobre Segurança Pública

Projeto final da disciplina **Análise Exploratória de Dados e Visualização** — FGV EMAp  
Professor: João Rulff

**Autores:** Josué Santos de Oliveira da Silva · Leonardo Cardia Bicca · Luigi Parmeggiani Porto

---

## Sobre o projeto

Análise exploratória da evolução temporal e da distribuição espacial da violência letal no estado do Rio de Janeiro, a partir da integração de **16 bases abertas** do Instituto de Segurança Pública do Estado do Rio de Janeiro (**ISP-RJ**) e de **três malhas geográficas oficiais** (CISP, AISP e RISP). As séries cobrem de 1991 a 2026, conforme a base.

O estudo é **estritamente descritivo e exploratório**: os padrões e associações apresentados não identificam causas isoladas. Os registros do ISP-RJ derivam de Registros de Ocorrência e refletem, conjuntamente, a dinâmica criminal, as práticas de notificação e a atuação policial.

### Conceitos-chave

- **CISP:** Circunscrição Integrada de Segurança Pública (área de uma delegacia e da companhia correspondente da PM).
- **AISP:** Área Integrada de Segurança Pública (nível de batalhão da PMERJ); agrupa CISPs.
- **RISP:** Região Integrada de Segurança Pública (comandos intermediários das polícias).
- **Letalidade violenta:** indicador oficial que soma homicídio doloso, latrocínio, lesão corporal seguida de morte e morte por intervenção de agente do Estado (MDIP).

---

## Perguntas de domínio

| # | Pergunta | Janela principal |
|---|---|---|
| P1 | Quais AISPs concentram as maiores taxas proporcionais de letalidade violenta e de feminicídio? | 2003–2022 (letalidade); 2017–2022/25 (feminicídio) |
| P2 | Como se compara a evolução da taxa de letalidade entre a Capital, a Região Metropolitana e o Interior? | 1991–2022 (comum às quatro regiões: 2000–2022) |
| P3 | Como se comporta a sazonalidade mensal da letalidade violenta nas regiões de policiamento? | 2003–2024 |
| P4 | Qual é a evolução do volume e da taxa de armas de fogo e fuzis apreendidos? | 2007–2024 |
| P5 | Há agrupamentos territoriais onde altas taxas de MDIP coexistem com grandes volumes de fuzis apreendidos? | 2017–2022 |
| P6 | Como a participação da MDIP se relaciona com a letalidade total nos municípios mais populosos? | 2014–2024 |
| P7 | Há correlação temporal entre policiais mortos em serviço e a letalidade violenta nos meses seguintes? | jan/2003–ago/2026 (284 meses) |

> A numeração acima é a **final** (notebooks e artigo). Ela difere da ordem da proposta inicial (Marco 1): a P1 da proposta (armas) virou a P4, a P2 (concentração por AISP) virou a P1 e a P4 (evolução por região) virou a P2.

---

## Principais resultados

- **Letalidade estadual (2003–2022):** o total de vítimas caiu de 8.054 para 4.485 (−44,3%); a taxa estadual caiu de 54,3 para 25,5 por 100 mil habitantes (−53,0%).
- **Regiões (P2):** de 2003 a 2022, a taxa caiu 66,7% na Capital, 52,7% em Grande Niterói e 49,0% na Baixada Fluminense, contra 24,6% no Interior. Em 2022, a Capital (19,4) ficou abaixo do Interior (26,0). O coeficiente de variação regional foi de 19,7% (2000) a 22,5% (2022), com pico de 36,5% em 2014.
- **Sazonalidade (P3):** ajustado pela duração dos meses, o índice estadual (base 100) atinge pico em março (111,97) e fevereiro (111,7) e vale em julho (89,81). O Interior tem a maior amplitude (25,06 pontos).
- **Armas (P4):** entre 2007 e 2024, o total de armas apreendidas caiu 44,4% (11.062 → 6.150), enquanto as apreensões de fuzis cresceram 242,1% (214 → 732).
- **Clusters (P5):** entre as 39 AISPs com cobertura completa, fuzis apreendidos e taxa média de MDIP têm Pearson r = 0,757 e Spearman ρ = 0,834 (taxa de fuzis: ρ = 0,782); 15 AISPs ficam iguais ou acima das duas medianas.
- **Municípios (P6):** a participação da MDIP chegou a 55,7% em Niterói (2023) e 48,7% em São Gonçalo (2021); em Campos dos Goytacazes o máximo foi 3,6%.
- **Policiais mortos (P7):** em nível, a correlação com a letalidade no mês seguinte é 0,415 (tendência histórica compartilhada); em primeiras diferenças, cai para 0,005.

---
 
## Estrutura do repositório
 
```
.
├── .vscode/
│   └── settings.json
├── Documentação/
│   ├── documentacao.pdf
│   └── documentacao.tex
├── Projeto/
│   ├── Datas/
│   ├── Declaração de Contribuição - Projeto AEDV A2
│   ├── comando_do_trabalho.pdf
│   └── projeto_seguranca_publica.pdf
├── NotebookAEDV.ipynb
├── NotebookArtigo.html
├── NotebookArtigo.ipynb
└── README.md
```
 
| Arquivo / pasta | Conteúdo |
|---|---|
| `Projeto/NotebookAEDV.ipynb` | Notebook exploratório completo: 15 etapas de preparação e auditoria de dados, seguidas das sete perguntas, com tabelas intermediárias e mapas interativos com mapa base. |
| `NotebookArtigo.ipynb` | Versão em formato de artigo, para publicação via Quarto, com mapas vetoriais autocontidos. |
| `NotebookArtigo.html` | Artigo renderizado (HTML autocontido gerado pelo Quarto). |
| `Documentação/documentacao.tex` e `.pdf` | Documentação técnica e metodológica do código (arquitetura, pipeline, decisões metodológicas e referência das 13 funções). |
| `Projeto/Datas/` | CSVs do ISP-RJ e shapefiles compactados (`CISP.zip`, `AISP.zip`, `RISP.zip`). |
| `Projeto/Declaração de Contribuição - Projeto AEDV A2` | Declaração de contribuição do grupo. |
| `Projeto/comando_do_trabalho.pdf` | Enunciado oficial e rubrica de avaliação. |
| `Projeto/projeto_seguranca_publica.pdf` | Proposta inicial (Marco 1). |
| `.vscode/settings.json` | Configurações do editor para o projeto. |
 
--

## Dados

- **Fonte:** [ISP-RJ — ISPDados](https://www.ispdados.rj.gov.br), com dados abertos de frequência mensal e anual originados nos Registros de Ocorrência das delegacias do estado.
- **Bases:** 16 CSVs (população por CISP e município, evolução mensal por CISP/município/UF/UPP, armas apreendidas, policiais mortos em serviço, feminicídio, taxa de letalidade, taxas mensais e anuais, e a relação CISP–AISP–RISP).
- **Malhas geográficas:** CISP (137 polígonos), AISP (41) e RISP (7), reprojetadas para `EPSG:4326`.
- **Referência territorial:** [Relação RISP × AISP × CISP](https://www.ispdados.rj.gov.br/Arquivos/Relacao_RISPxAISPxCISP.pdf).

### Como os notebooks leem os dados

Os notebooks leem primeiro os CSVs e shapefiles da pasta local `Projeto/Datas/`. Se a pasta não existir, baixam o ZIP do repositório pelo GitHub, em memória. Para execuções offline, mantenha a pasta `Projeto/Datas/` no diretório de execução.

---

## Como executar

### Requisitos

- Python 3.10 ou superior
- Bibliotecas: `requests`, `numpy`, `pandas`, `geopandas`, `matplotlib`, `seaborn`, `plotly`, `ipykernel`, `nbformat`
- Para gerar o artigo em HTML: [Quarto CLI](https://quarto.org)
- Para compilar a documentação técnica: uma distribuição LaTeX com `pdflatex` ou `xelatex`

### Passo a passo

```bash
# 1. Clonar o repositório
git clone https://github.com/Josue-santoss/AEDV-A2.git
cd AEDV-A2

# 2. Criar o ambiente e instalar as dependências
python -m venv .venv
source .venv/bin/activate        # Windows: .venv\Scripts\activate
pip install requests numpy pandas geopandas matplotlib seaborn plotly ipykernel nbformat

# 3. Abrir o notebook exploratório
jupyter notebook NotebookAEDV.ipynb
```

### Gerar o artigo em HTML

```bash
quarto render NotebookArtigo.ipynb
```

O cabeçalho do notebook configura `embed-resources: true` e `execute: echo: false`, de modo que o HTML resultante é autocontido e não exibe o código.

### Compilar a documentação técnica

```bash
pdflatex documentacao.tex
pdflatex documentacao.tex   # segunda passada para o sumário e as referências
```

---

## Decisões metodológicas em destaque

- **Integridade relacional:** junções críticas usam `validate="one_to_one"` ou `"many_to_one"`, e `exigir_colunas` interrompe a execução se o esquema dos CSVs mudar.
- **Imputação seletiva:** apenas colunas `quantidade_*` ausentes viram zero; chaves, populações e taxas ausentes permanecem `NaN`.
- **Taxas por AISP:** exigem 12 meses de atividade territorial e população completa em todas as CISPs do mês; anos parciais ficam sem taxa.
- **Mudanças territoriais:** a AISP 1 (Cidade Nova/Santa Teresa em 2003–2011; São Gonçalo/Neves depois) e a AISP 13 (extinta) têm tratamento explícito.
- **Feminicídio (P1):** sem população por sexo, adota-se a aproximação de 50% de mulheres (fator 200.000). Os rankings usam taxas ponderadas por pessoas-ano e mostram a contagem absoluta `n`.
- **Sazonalidade (P3):** as somas mensais são convertidas em intensidade diária média, para remover o viés de calendário (fevereiro), e normalizadas em Índice Base 100.
- **Armas (P4):** a população estadual de 2022 é propagada (`ffill`) para 2023–2024; os índices usam Base 100 (2007 = 100) em vez de eixos duplos.
- **Clusters (P5):** quadrantes definidos pelas medianas de fuzis e de MDIP, com teste de robustez pela taxa proporcional de fuzis.
- **Municípios (P6):** a população dos municípios mais populosos é estimada pela identidade ROs ÷ taxa de ROs, o que permite ir além de 2022.
- **Policiais mortos (P7):** correlação cruzada em nível e em primeiras diferenças, com banda de referência ±1,96/√n (≈ ±0,117) sob ruído branco e sem pré-branqueamento formal.

### Acessibilidade e design

- Paleta **Okabe-Ito** (segura para daltonismo), com cores fixas por região em todo o projeto.
- Escala dos mapas animados limitada ao **percentil 98**, para preservar o contraste territorial.
- Formatação numérica brasileira e rodapé padronizado com a fonte (ISP-RJ) em todas as figuras.

---

## Limitações

- As taxas por AISP dependem da população por CISP, disponível até **2022**. As taxas estaduais de armas de 2023–2024 carregam a população de 2022.
- O denominador feminino é uma aproximação (50%), e AISPs pequenas têm contagens baixas de feminicídio, o que torna as taxas sensíveis.
- Os dados são registros administrativos, sujeitos a mudanças legais (como a Lei nº 13.104/2015), à subnotificação e ao foco operacional das polícias.
- Os resultados são associações descritivas. Nenhuma análise estabelece causalidade.

---

## Referências

- Instituto de Segurança Pública do Estado do Rio de Janeiro (ISP-RJ). *ISPDados*. <https://www.ispdados.rj.gov.br>
- ISP-RJ. *Relação RISP × AISP × CISP*. <https://www.ispdados.rj.gov.br/Arquivos/Relacao_RISPxAISPxCISP.pdf>
- Brasil. Lei nº 13.104, de 9 de março de 2015 (Lei do Feminicídio).

---
