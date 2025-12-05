# ⚖️ LegalFlow AI: Decisão & Extração Judicial Estruturada

## 🚀 Visão Geral do Projeto

O **LegalFlow AI** é um pipeline de Inteligência Artificial generativa projetado para automatizar a análise e a triagem de documentos judiciais complexos. O objetivo é transformar textos jurídicos não estruturados (petições, sentenças) em dados limpos e padronizados no formato **JSON**, permitindo a **tomada de decisão automatizada** e a **precificação de crédito** ágil.

Este projeto demonstra a capacidade de construir **fluxos de automação robustos (DECISION-RAG)**, essenciais para a área de **Análise de Machine Learning e IA** na LegalTech (JusCash).

---

## 🎯 Desafio de Engenharia e Valor Agregado

| Desafio da LegalTech | Solução do LegalFlow AI |
| :--- | :--- |
| **Lentidão na Análise Manual** | Automação da **Classificação** e **Extração Estruturada** em segundos. |
| **Inconsistência de Dados** | Uso de **Pydantic** para forçar a saída **JSON** validada e livre de alucinações de formato. |
| **Necessidade de Motor de Decisão** | Implementação de um **Motor de Regras (Python)** que consome a saída JSON para pré-avaliar o **risco** e **precificação** inicial. |
| **Escalabilidade** | Arquitetura **Serverless (AWS Lambda)** provisionada via **Terraform** para lidar com alto volume de documentos. |

---

## 🏛️ Arquitetura do Pipeline DECISION-RAG

O projeto utiliza uma arquitetura modular focada em produção, orquestrada pelo Python e LangChain.

### Fluxo de Dados 

1.  **Ingestão:** Documento entra via **S3/API** e é processado.
2.  **Raciocínio:** O **LangChain** atua como o orquestrador na **AWS Lambda**.
3.  **Saída:** O JSON validado e a decisão de risco são publicados.

### Componentes Chave na Camada de Raciocínio

| Passo | Tecnologia Chave | Descrição da Habilidade |
| :--- | :--- | :--- |
| **Classificação** | **LLM (OpenAI/Claude)** | Determina a **Tipologia** do caso (*Trabalhista, Cível*). |
| **Extração Estruturada** | **LangChain & Pydantic** | Garante que campos como `valor_causa` e `partes` sejam extraídos em um **JSON** *schema-validated*. |
| **Motor de Regras** | **Python (Classes/Funções)** | Aplica a lógica de negócio (ex: *Se Ação Trabalhista E Valor > X, atribua Risco 'Alto'*). |
| **RAG Suporte** | **Vector Store Lookup (ChromaDB)** | Busca por contexto e jurisprudências similares (RAG) para inferência ou suporte. |

---

## 💻 Tech Stack e Habilidades Demonstradas

Este projeto é um *showcase* completo das suas competências para Engenharia de IA em um ambiente corporativo.

| Categoria | Tecnologia Específica | Competência Comprovada |
| :--- | :--- | :--- |
| **GenAI & NLP** | **OpenAI/Claude (via API)**, **LangChain**, **Pydantic** | **Interpretação de Texto** e **Automação de Decisão** com controle de saída. |
| **Engenharia de Dados** | **Python**, Pandas, **Vector Store (ChromaDB/Pinecone)** | **Desenvolvimento de pipelines de dados em Python** e tratamento de texto. |
| **MLOps & Cloud** | **AWS Lambda, API Gateway** | **Escalabilidade** e **Deployment** de modelos como serviços *Serverless*. |
| **DevOps & IaC** | **Terraform** | **Infraestrutura como Código (IaC)** para gerenciar o *deployment* da Lambda e dos recursos. |

---

## 📝 Instalação e Uso

### Pré-requisitos
* Python 3.10+
* Conta AWS configurada (para o deployment Terraform).
* Chave de API OpenAI ou credenciais para outro LLM.

### 1. Configuração do Projeto

```bash
# Clone o repositório
git clone [https://github.com/CarlosLivius/legalflow-ai.git](https://github.com/CarlosLivius/legalflow-ai.git)
cd legalflow-ai

# Instale as dependências
pip install -r requirements.txt
