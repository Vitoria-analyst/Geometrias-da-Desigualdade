# 🗺️ Geometrias da Desigualdade: Análise Espacial de Mobilidade Urbana

> **Uma análise comparativa de acesso e exclusão socioterritorial em cidades brasileiras utilizando QGIS.**

![PostGIS](https://img.shields.io/badge/PostGIS-Spatial%20SQL-blue)
![QGIS](https://img.shields.io/badge/QGIS-Visualisation-green)
![Status](https://img.shields.io/badge/Status-Completed-success)

## 📋 Sobre o Projeto

Mobilidade não é apenas sobre movimento, é sobre acesso.

Este projeto explora o conceito de **Justiça Espacial** através da análise de dados geográficos. O objetivo foi quantificar o "Gap de Acessibilidade": a diferença de oportunidades alcançáveis em 30 minutos por transporte privado (carro) *versus* transporte público ou ativo.

Utilizando dados do **Censo IBGE 2022** e infraestrutura do **OpenStreetMap (OSM)**, analisamos três arquétipos urbanos brasileiros para responder: *A infraestrutura dita o tempo de deslocamento ou o modal é o fator determinante de exclusão?* 

### 🏙️ Estudos de Caso e Resultados

| Cidade | Arquétipo Urbano | Descoberta Principal | Gap de Acesso (Carro vs. Outros) |
| :--- | :--- | :--- | :--- |
| **São Paulo (SP)** | A Metrópole Travada | *Spatial Mismatch*: Empregos no centro, moradia na periferia. | [cite_start]**467 km²** de vantagem para o carro [cite: 441] |
| **Rio Branco (AC)** | Cidade Média Dependente | Eficiência Seletiva: A cidade flui bem, mas apenas para quem tem carro. | [cite_start]**33 km²** de vantagem para o carro [cite: 460] |
| **Porto Velho (RO)** | O Potencial Ativo | Múltiplos polos conectados. A bicicleta é altamente eficiente, limitada apenas pelo clima. | [cite_start]**105 km²** de vantagem para a **bicicleta** [cite: 474] |

---

## 🛠️ A "Cozinha" Geoespacial (Tech Stack)

A análise foi realizada combinando três técnicas de geoprocessamento:

1.  **Análise de Rede (Isochrones):** Utilização da **TravelTime API** para calcular polígonos de alcance de 30 minutos a partir dos centros urbanos (zonas de trabalho).
2.  **Processamento Vetorial (PostGIS/SQL):**
    * Uso de índices espaciais para performance.
    * Filtragem de infraestrutura viária e barreiras naturais.
    * Cálculo de áreas de intersecção e diferença (Gaps).
3.  **Análise de Sobreposição (Heatmaps):** Identificação de padrões de densidade populacional vs. infraestrutura no **QGIS 3.x**.

### Ferramentas:
* **Banco de Dados:** PostgreSQL com extensão **PostGIS**.
* **GIS Desktop:** QGIS 3.
* **Dados:** IBGE (Demografia), OSM (Vias), SRTM Downloader (Relevo).

---

## 📊 Visualizações

*(Sugestão: Insira aqui as imagens dos mapas comparativos gerados no projeto, especialmente as manchas vermelhas vs. amarelas mostradas no relatório)*

> **Exemplo - São Paulo:** A mancha vermelha representa a área acessível apenas de carro em 30 min. A amarela, acessível por transporte público. A diferença (467km²) ilustra a exclusão social imposta pela malha urbana. 

---

## 🚀 Próximos Passos e Limitações

* [cite_start]**Limitação:** O mapeamento colaborativo (OSM) pode apresentar vazios de dados em áreas periféricas[cite: 499].
* [cite_start]**Futuro:** Integração de dados GTFS (GPS real dos autocarros) para maior precisão e adição de variáveis sociais (renda/raça) para qualificar a população afetada[cite: 501, 502].

---

## 👩‍💻 Autoras

* **Vitória Rodrigues**

---
*Desenvolvido no âmbito do Mestrado em Ciência de Dados para Ciências Sociais - Universidade de Aveiro*
