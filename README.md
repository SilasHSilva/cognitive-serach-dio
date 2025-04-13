# Fourth Coffee - AI Search com Azure Cognitive Search ☕

Este projeto é baseado em um laboratório prático da DIO, com o objetivo de aplicar **Azure Cognitive Search** para analisar avaliações de clientes da empresa fictícia **Fourth Coffee**.

## 🚀 Objetivo

Criar um pipeline de indexação e enriquecimento de dados com inteligência artificial usando o Azure Cognitive Search. O foco é extrair **frases-chave**, **sentimentos** e outras informações relevantes a partir de um arquivo de avaliações em JSON.

---

## 🔧 Tecnologias Utilizadas

- [Azure Cognitive Search](https://azure.microsoft.com/en-us/products/ai-search/)
- Azure Blob Storage
- Azure AI Services
- Habilidades Cognitivas (Skillset)
- JSON como fonte de dados
- Portal do Azure

---

## 📦 Recursos Criados no Azure

Durante o projeto, foram criados os seguintes recursos no portal do Azure:

- **Azure Cognitive Search** (região: **East US**) – para indexação e consulta de dados.
- **Azure AI Services** – para fornecer as habilidades cognitivas (sentimento, idioma, etc.).
- **Azure Storage Account** – para armazenar o arquivo `usreviews.json`.

---

## 📂 Estrutura do Projeto

- `usreviews.json` - Arquivo com as avaliações de clientes em formato JSON.
- **Azure Blob Storage** - Armazenamento do arquivo fonte.
- **Indexer** - Responsável por ingerir os dados da fonte e aplicar as habilidades.
- **Skillset** - Conjunto de habilidades cognitivas aplicadas:
  - Extração de idioma
  - Análise de sentimento
  - Extração de frases-chave
- **Index** - Armazena os dados estruturados e enriquecidos para consulta.

---

## 🔄 Etapas do Projeto

1. **Criação dos Recursos no Azure**
   - Provisionamento dos serviços:
     - Azure Cognitive Search
     - Azure AI Services
     - Azure Storage Account

2. **Upload do JSON para o Azure Blob Storage**
   - Container criado com acesso público.
   - Arquivo `usreviews.json` armazenado com sucesso.

3. **Configuração da Indexação e Enriquecimento**
   - Data source criado a partir do blob.
   - Skillset com habilidades cognitivas padrão configuradas:
     - Detecção de idioma
     - Análise de sentimento
     - Extração de frases-chave
   - Indexer criado e executado com sucesso.
   - Index construído com os dados enriquecidos.

4. **Consulta aos Dados**
   - Consulta realizada via Search Explorer.
   - Resultados exibem frases-chave e sentimentos extraídos.

---

## 🔍 Exemplo de Resultado Enriquecido

```json
{
  "@search.score": 1.0,
  "reviewerName": "John D.",
  "reviewText": "The coffee was amazing and the service was excellent!",
  "rating": 5,
  "keyPhrases": ["coffee", "service"],
  "sentiment": "positive"
}
