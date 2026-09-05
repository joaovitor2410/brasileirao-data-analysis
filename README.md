# ⚽ Análise do Campeonato Brasileiro (2003–2024)

Projeto de portfólio em Análise de Dados: tratamento, exploração e visualização do histórico de classificações do Campeonato Brasileiro Série A, de 2003 a 2024.

## 🎯 Objetivo

Ir além do "gráfico bonito" e mostrar um fluxo completo de análise: encontrar uma inconsistência real nos dados, investigar a causa raiz (em vez de só corrigir ou descartar), e transformar isso em um insight de storytelling.

## 🔍 Principal achado

Ao validar a regra `pontos = vitórias×3 + empates`, 11 linhas do dataset quebravam essa equação. Em vez de tratar como erro, investigei historicamente cada caso e descobri que **são todos reais**: punições e compensações de pontos aplicadas pelo STJD (Superior Tribunal de Justiça Desportiva) por escalação irregular de jogadores — incluindo o caso do São Caetano em 2004, que perdeu 24 pontos após a morte em campo do zagueiro Serginho, e o "Caso Héverton" de 2013, que rebaixou a Portuguesa.

| Temporada | Time | Diferença | Motivo |
|---|---|---|---|
| 2003 | Paysandu | −8 | Escalação irregular de 2 jogadores em 4 jogos |
| 2003 | Ponte Preta | −1 | Perdeu 4 (escalação irregular), recebeu 3 (punição do Paysandu) |
| 2004 | São Caetano | −24 | Morte do zagueiro Serginho (escalação irregular) |
| 2010 | Barueri/Prudente | −3 | Escalação irregular do zagueiro Paulão |
| 2013 | Flamengo | −4 | Escalação irregular do lateral André Santos |
| 2013 | Portuguesa | −4 | Caso Héverton — time rebaixado por causa da punição |

*(tabela completa com as compensações de pontos no notebook)*

**Outra checagem de qualidade de dados**: o Mirassol aparece no cadastro de clubes (`teams.csv`), mas nunca nas classificações (`brasileirao.csv`) — não é inconsistência, o clube só foi promovido à Série A em 2025, fora do recorte temporal (2003–2024) deste projeto.

## 📊 Outros insights

- **Ranking histórico de títulos**: Corinthians e Palmeiras lideram com 4 títulos cada no período, seguidos por Cruzeiro, Flamengo e São Paulo com 3.
- **Ataque pesa mais que defesa**: correlação de 0.75 entre gols marcados e pontos, contra -0.42 entre gols sofridos e pontos.
- **Evolução histórica por time** e **heatmap de posição final** (time x temporada) para visualizar trajetórias de ascensão e queda.
- **Desempenho médio de pontos por região do país.**

## 🛠️ Tecnologias

- Python (Pandas, NumPy)
- Visualização: Plotly, Matplotlib, Seaborn
- Google Colab

## 📁 Estrutura

```
├── brasileirao_analise.ipynb   # notebook principal
├── brasileirao.csv             # classificação por temporada (2003–2024)
├── teams.csv                   # dados cadastrais dos clubes
└── README.md
```

## 📌 Fonte dos dados

Dataset original: [Brasileirão Série A 2006-2022](https://www.kaggle.com/datasets/lucasyukioimafuko/brasileirao-serie-a-2006-2022), por Lucas Yukio Imafuko, no Kaggle.
Versão espelhada para reprodutibilidade deste projeto: `<link do seu dataset no Kaggle aqui>`

## ▶️ Como rodar

1. Abra o notebook no [Google Colab](https://colab.research.google.com/)
2. Faça upload de `brasileirao.csv` e `teams.csv` (ou ajuste o caminho para seu dataset no Kaggle)
3. Execute as células em ordem

## 👤 Autor

**João Victor Azevedo Porto**
Estudante de Ciência da Computação | Foco em Análise de Dados e BI
[LinkedIn](https://linkedin.com/in/joaovitorazevedoporto)
