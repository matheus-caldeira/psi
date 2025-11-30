# Seção 1 – Diagrama de Casos de Uso

## 1.1 Introdução

O diagrama de casos de uso apresenta uma visão geral das funcionalidades do Sistema Academia, identificando os atores que interagem com o sistema e os principais casos de uso disponíveis. O sistema foi projetado para atender às necessidades de monitoramento e controle das atividades dos alunos de uma academia de grande porte.

## 1.2 Atores do Sistema

### 1.2.1 Atores Primários

| Ator | Descrição |
|------|-----------|
| **Aluno** | Usuário principal do sistema. Consulta treinos, agenda avaliações físicas e aulas, visualiza sua evolução e se comunica com o professor. Acessa o sistema tanto pelo módulo local (computadores na academia) quanto pelo módulo web (navegador/celular). |
| **Professor** | Responsável por registrar e acompanhar os treinos dos alunos. Alimenta dados de avaliações físicas e evolução, além de gerar relatórios de acompanhamento. |
| **Administrador** | Gerencia as operações administrativas da academia. Exporta dados para o sistema financeiro e controla modalidades e turmas oferecidas. |
| **Médico** | Profissional responsável pelo acompanhamento físico dos alunos. Consulta e atualiza avaliações físicas, além de gerenciar sua agenda de atendimentos. |

### 1.2.2 Atores Secundários

| Ator | Descrição |
|------|-----------|
| **Sistema Financeiro** | Sistema externo que recebe dados exportados para controle de cobranças e cálculo de comissões dos professores. |

## 1.3 Lista de Casos de Uso

### Módulo Local

| ID | Nome do Caso de Uso | Ator Principal |
|----|---------------------|----------------|
| UC01 | Consultar Treino Diário | Aluno |

### Módulo Web

| ID | Nome do Caso de Uso | Ator Principal |
|----|---------------------|----------------|
| UC02 | Agendar Avaliação Física | Aluno |
| UC03 | Agendar Aula em Modalidade | Aluno |
| UC04 | Consultar Evolução Física | Aluno |
| UC05 | Consultar Agenda | Aluno |
| UC06 | Comunicar com Professor | Aluno, Professor |

### Gestão de Treinos

| ID | Nome do Caso de Uso | Ator Principal |
|----|---------------------|----------------|
| UC07 | Registrar Treino Programado | Professor |
| UC08 | Registrar Avaliação Física | Professor |
| UC09 | Registrar Evolução do Aluno | Professor |
| UC10 | Gerar Relatório de Evolução | Professor |

### Gestão Administrativa

| ID | Nome do Caso de Uso | Ator Principal |
|----|---------------------|----------------|
| UC11 | Exportar Atividades Extras | Administrador |
| UC12 | Exportar Frequência | Administrador |
| UC13 | Exportar Estatísticas por Professor | Administrador |
| UC14 | Consultar Alunos por Modalidade | Administrador |
| UC15 | Gerenciar Modalidades | Administrador |

### Acompanhamento Médico

| ID | Nome do Caso de Uso | Ator Principal |
|----|---------------------|----------------|
| UC16 | Consultar Histórico de Avaliações | Médico |
| UC17 | Atualizar Avaliação Física | Médico |
| UC18 | Consultar Agenda Médica | Médico |

### Casos de Uso Auxiliares

| ID | Nome do Caso de Uso | Descrição |
|----|---------------------|-----------|
| UC19 | Autenticar Usuário | Caso de uso incluído por outros para validar credenciais |
| UC20 | Enviar Notificação | Caso de uso estendido para envio de alertas e confirmações |

## 1.4 Diagrama de Casos de Uso

![Diagrama de Casos de Uso](../diagrams/casos-uso.png)

```plantuml
@startuml casos-uso
title Diagrama de Casos de Uso - Sistema Academia

left to right direction
skinparam packageStyle rectangle
skinparam actorStyle awesome

' === ATORES ===
actor "Aluno" as aluno
actor "Professor" as professor
actor "Administrador" as admin
actor "Médico" as medico
actor "Sistema Financeiro" as sistemaFinanceiro <<system>>

' === SISTEMA ===
rectangle "Sistema Academia" {

    ' --- Casos de Uso do Aluno ---
    package "Módulo Local" {
        usecase "UC01 - Consultar Treino Diário" as UC01
    }

    package "Módulo Web" {
        usecase "UC02 - Agendar Avaliação Física" as UC02
        usecase "UC03 - Agendar Aula em Modalidade" as UC03
        usecase "UC04 - Consultar Evolução Física" as UC04
        usecase "UC05 - Consultar Agenda" as UC05
        usecase "UC06 - Comunicar com Professor" as UC06
    }

    ' --- Casos de Uso do Professor ---
    package "Gestão de Treinos" {
        usecase "UC07 - Registrar Treino Programado" as UC07
        usecase "UC08 - Registrar Avaliação Física" as UC08
        usecase "UC09 - Registrar Evolução do Aluno" as UC09
        usecase "UC10 - Gerar Relatório de Evolução" as UC10
    }

    ' --- Casos de Uso do Administrador ---
    package "Gestão Administrativa" {
        usecase "UC11 - Exportar Atividades Extras" as UC11
        usecase "UC12 - Exportar Frequência" as UC12
        usecase "UC13 - Exportar Estatísticas por Professor" as UC13
        usecase "UC14 - Consultar Alunos por Modalidade" as UC14
        usecase "UC15 - Gerenciar Modalidades" as UC15
    }

    ' --- Casos de Uso do Médico ---
    package "Acompanhamento Médico" {
        usecase "UC16 - Consultar Histórico de Avaliações" as UC16
        usecase "UC17 - Atualizar Avaliação Física" as UC17
        usecase "UC18 - Consultar Agenda Médica" as UC18
    }

    ' --- Casos de Uso Auxiliares ---
    usecase "UC19 - Autenticar Usuário" as UC19
    usecase "UC20 - Enviar Notificação" as UC20
}

' === RELACIONAMENTOS DO ALUNO ===
aluno --> UC01
aluno --> UC02
aluno --> UC03
aluno --> UC04
aluno --> UC05
aluno --> UC06

' === RELACIONAMENTOS DO PROFESSOR ===
professor --> UC07
professor --> UC08
professor --> UC09
professor --> UC10
professor --> UC06

' === RELACIONAMENTOS DO ADMINISTRADOR ===
admin --> UC11
admin --> UC12
admin --> UC13
admin --> UC14
admin --> UC15

' === RELACIONAMENTOS DO MÉDICO ===
medico --> UC16
medico --> UC17
medico --> UC18

' === RELACIONAMENTOS COM SISTEMA FINANCEIRO ===
UC11 --> sistemaFinanceiro
UC12 --> sistemaFinanceiro
UC13 --> sistemaFinanceiro

' === RELACIONAMENTOS DE INCLUDE ===
UC01 ..> UC19 : <<include>>
UC02 ..> UC19 : <<include>>
UC04 ..> UC19 : <<include>>
UC07 ..> UC19 : <<include>>
UC10 ..> UC19 : <<include>>
UC16 ..> UC19 : <<include>>

' === RELACIONAMENTOS DE EXTEND ===
UC02 ..> UC20 : <<extend>>
UC03 ..> UC20 : <<extend>>
UC08 ..> UC20 : <<extend>>

@enduml
```

## 1.5 Relacionamentos

### 1.5.1 Relacionamentos de Inclusão (<<include>>)

Os seguintes casos de uso incluem obrigatoriamente a autenticação do usuário:

- UC01 (Consultar Treino Diário) → UC19 (Autenticar Usuário)
- UC02 (Agendar Avaliação Física) → UC19 (Autenticar Usuário)
- UC04 (Consultar Evolução Física) → UC19 (Autenticar Usuário)
- UC07 (Registrar Treino Programado) → UC19 (Autenticar Usuário)
- UC10 (Gerar Relatório de Evolução) → UC19 (Autenticar Usuário)
- UC16 (Consultar Histórico de Avaliações) → UC19 (Autenticar Usuário)

### 1.5.2 Relacionamentos de Extensão (<<extend>>)

Os seguintes casos de uso podem opcionalmente enviar notificações:

- UC02 (Agendar Avaliação Física) ← UC20 (Enviar Notificação)
- UC03 (Agendar Aula em Modalidade) ← UC20 (Enviar Notificação)
- UC08 (Registrar Avaliação Física) ← UC20 (Enviar Notificação)

## 1.6 Requisitos de Acessibilidade

Conforme especificado pelo cliente, o sistema deve:

- Ser acessível via navegadores web comuns
- Funcionar em dispositivos móveis (celulares)
- Atender aos requisitos de acessibilidade para alunos portadores de necessidades especiais
