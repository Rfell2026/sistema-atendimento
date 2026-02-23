# 📋 Sistema de Atendimento

## 📌 Descrição do Projeto

Aplicativo para empresa de registro de atendimento, com controle de filas, cadastro de atendentes e registro das pessoas atendidas.

O sistema permite organizar a ordem de atendimento e manter o histórico completo de cada atendimento realizado.

---

## 🎯 Objetivo Geral

Gerenciar clientes, atendentes e filas de atendimento, garantindo organização, rastreabilidade e histórico das operações.

---

## 📁 Estrutura Inicial do Projeto

- README.md → Documentação do projeto
- docs/ → Arquivos de modelagem
- sql/ → Scripts de criação do banco de dados

---

## 🔢 Versão Inicial

Versão 1.0 – Primeira modelagem do banco de dados contendo:

- Cliente
- Atendente
- Fila
- Atendimento

---

## 🗄️ Modelo de Dados (MERMAID)

```mermaid
erDiagram

CLIENTE {
    int id_cliente PK
    string nome
    string cpf
    string telefone
}

ATENDENTE {
    int id_atendente PK
    string nome
    string cpf
    string email
}

FILA {
    int id_fila PK
    string nome
    string descricao
}

ATENDIMENTO {
    int id_atendimento PK
    datetime data_inicio
    datetime data_fim
    string status
}

CLIENTE ||--o{ ATENDIMENTO : realiza
ATENDENTE ||--o{ ATENDIMENTO : executa
FILA ||--o{ ATENDIMENTO : organiza
