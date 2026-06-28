# 📊 Tabelas de conversão da densidade e conversão de volume (Derivados de Petróleo) a 20°C, Teor Alcoólico e Massa Específica (Etanol) a 20°C

---

## 🗺️ Roadmap do Projeto (Etapas)

Status de mapeamento, processamento e estruturação de dados:

| Status | Etapa | Descrição |
|:---:|---|---|
| ✅ | **1. Derivados de Petróleo (Densidade)** | Conversão da densidade observada para densidade a 20ºC (Faixas do Diesel, etc.) |
| ⏳ | **2. Etanol (Massa Específica e Teor)** | Conversão de Massa Específica e Teor Alcoólico a 20°C |
| ⏳ | **3. Derivados de Petróleo (Volume)** | Fatores de conversão de volume a partir da temperatura observada

---

## 📁 Arquivos Gerados

| Arquivo | Descrição |
|---------|-----------|
| `Conversão da densidade observada para densidade a 20ºC/res-894-2022-01_db_format.xlsx` | Formato banco de dados (flat table com primary key) |
| `Conversão da densidade observada para densidade a 20ºC/res-894-2022-01_db_format.json` | Formato JSON para consulta via API REST (GitHub raw) |
| `Conversão da densidade observada para densidade a 20ºC/res-894-2022-01_pivot_format.xlsx` | Formato pivot (matriz de consulta) com guias agrupadas |

---

## 📈 Estatísticas do Dataset Atual

| Métrica | Valor |
|---------|-------|
| Total de registros | **6,060** |
| Densidades observadas únicas | **60** |
| Temperaturas observadas únicas | **101** |
| Faixa de densidade | **0.820** a **0.879** g/cm³ |
| Faixa de temperatura | **0.0** a **50.0** °C |

---

## 📑 Guias do Arquivo Pivot

O arquivo pivot é dividido em guias agrupadas de 10 em 10 unidades de densidade (×1000):

| Guia | Faixa de Densidade (g/cm³) | Colunas |
|------|---------------------------|---------|
| `820 a 829` | 0.820 – 0.829 | 10 |
| `830 a 839` | 0.830 – 0.839 | 10 |
| `840 a 849` | 0.840 – 0.849 | 10 |
| `850 a 859` | 0.850 – 0.859 | 10 |
| `860 a 869` | 0.860 – 0.869 | 10 |
| `870 a 879` | 0.870 – 0.879 | 10 |

---

## 🔑 Estrutura da Primary Key

<densidade_observada>#<temperatura_observada>
Exemplo: 0.825#25.0

A primary key concatena a densidade (3 casas decimais) e a temperatura (1 casa decimal),
permitindo identificação única de cada ponto de consulta.

---

## 🌐 Consulta via API REST

Consulte os dados via raw URL:

https://raw.githubusercontent.com/alefealvessilva/anp-tabelas-conversao/main/Convers%C3%A3o%20da%20densidade%20observada%20para%20densidade%20a%2020%C2%BAC/res-894-2022-01_db_format.json

Exemplo de resposta:
```json
{
  "0.825#25.0": {
    "densidade_observada": 0.825,
    "temperatura_observada": 25.0,
    "densidade_20_graus": 0.8284
  }
}
```

📋 Referência Legal
Resolução ANP nº 894, de 26 de janeiro de 2022

Tabela I — Listagem de Derivados de Petróleo

Redução de densidade observada à densidade a 20 °C

🕛 Atualizado em 28/06/2026
