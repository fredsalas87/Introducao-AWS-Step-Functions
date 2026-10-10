# ⚡ Introdução ao AWS Step Functions

Este repositório contém anotações, exemplos e um projeto prático focado na aprendizagem básica do **AWS Step Functions**, abordando desde os conceitos fundamentais até à criação de uma máquina de estados na prática.

---

## 📌 Sumário

1. [Bem-vindo ao Step Functions](#-bem-vindo-ao-step-functions)
2. [Pré-requisitos](#-pré-requisitos)
3. [Situação Problema](#-situação-problema)
4. [Localizando o Serviço e Primeiros Passos](#-localizando-o-serviço-e-primeiros-passos)
5. [Workflow Studio & ASL](#-workflow-studio--asl)
6. [Criando um Hello World](#-criando-um-hello-world)
7. [Precificação e Custos](#-precificação-e-custos)
8. [Níveis de Configuração](#-níveis-de-configuração)
9. [Projeto Prático: Assistente de Delivery](#-projeto-prático-assistente-de-delivery)
10. [Links Úteis e Documentação](#-links-úteis-e-documentação)

---

## 👋 Bem-vindo ao Step Functions

O **AWS Step Functions** é um serviço de orquestração sem servidor (serverless) que permite conectar e coordenar diferentes serviços da AWS em fluxos de trabalho visuais e estruturados (máquinas de estado).

---

## 🛠️ Pré-requisitos

Para acompanhar este repositório, é necessário:
* Uma conta ativa na [AWS](https://aws.amazon.com/).
* Permissões básicas no IAM para criar fluxos de trabalho.
* Conhecimentos básicos sobre serviços serverless (ex: AWS Lambda).

---

## 🎯 Situação Problema

Em arquiteturas orientadas a eventos ou microserviços, coordenar múltiplas tarefas executadas em sequência ou em paralelo pode tornar-se complexo. 
O Step Functions resolve este problema gerindo o estado, retentativas e falhas automaticamente, evitando a necessidade de escrever código de orquestração personalizado.

---

## 🔍 Localizando o Serviço e Primeiros Passos

1. Faça login na consola da AWS.
2. Na barra de pesquisa principal, procure por **Step Functions**.
3. É possível iniciar um fluxo do zero ou utilizar os **Templates** prontos oferecidos pela AWS para aprender os padrões mais comuns.

---

## 🎨 Workflow Studio & ASL

* **Workflow Studio**: Interface gráfica do tipo "arrastar e soltar" para desenhar visualmente a lógica dos seus processos.
* **ASL (Amazon States Language)**: Estrutura baseada em JSON utilizada internamente pelo Step Functions para definir os estados, transições, decisões e ações do fluxo.

---

## 🚀 Criando um Hello World

Exemplo simples de uma máquina de estado com um único estado que retorna uma mensagem de boas-vindas:

```json
{
  "Comment": "Um exemplo simples de Hello World no Step Functions",
  "StartAt": "HelloWorld",
  "States": {
    "HelloWorld": {
      "Type": "Pass",
      "Result": "Hello World com AWS Step Functions!",
      "End": true
    }
  }
}
```

## 💰 Precificação e Custos

O **AWS Step Functions** é cobrado com base no tipo de fluxo escolhido:

* **Standard Workflows**: Cobrado pelo número de transições de estado executadas. Ideal para processos de longa duração ou auditáveis.
* **Express Workflows**: Cobrado pelo número de execuções, duração e consumo de memória. Ideal para cargas de trabalho de alto volume e rápida resposta.

---

## ⚙️ Níveis de Configuração

* **Nível 1 - Permissões de Perfil (IAM)**: Criação da *role* e políticas necessárias para que o Step Functions possa invocar e orquestrar outros serviços (como AWS Lambda, Amazon SNS ou Amazon DynamoDB).
* **Nível 2 - Disponibilidade e Governança**: Definição dos parâmetros de execução, logs de auditoria (com Amazon CloudWatch) e limites de tempo (*timeouts*).

---

## 🔗 Links Úteis e Documentação

* [Página Oficial do AWS Step Functions](https://aws.amazon.com/step-functions/)
* [Documentação Oficial da AWS Step Functions](https://docs.aws.amazon.com/step-functions/)
