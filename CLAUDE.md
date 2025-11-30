# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Projeto: Sistema Academia - Documentação UML

Este projeto consiste na criação de artefatos UML para documentar um sistema de monitoramento e controle de atividades de alunos de uma academia de grande porte (2.000 alunos matriculados).

## Estrutura do Projeto

```
puc/
├── tarefa.md          # Descrição do cenário e requisitos do sistema
├── entrega.md         # Critérios de entrega da atividade
├── docs/              # Documentação final em Markdown
│   ├── 00-sumario.md
│   ├── 01-diagrama-casos-uso.md
│   ├── 02-especificacao-casos-uso.md
│   ├── 03-diagrama-atividades.md
│   └── 04-diagrama-classes.md
└── diagrams/          # Arquivos PlantUML
    ├── casos-uso.puml
    ├── atividades/    # Um arquivo por caso de uso principal
    └── classes.puml
```

## Comandos

### Gerar diagramas PlantUML

```bash
# Instalar PlantUML (macOS)
brew install plantuml

# Gerar PNG de um diagrama específico
plantuml diagrams/casos-uso.puml

# Gerar todos os diagramas
plantuml diagrams/**/*.puml

# Gerar em SVG (melhor qualidade)
plantuml -tsvg diagrams/**/*.puml
```

## Contexto do Sistema Academia

### Atores Identificados
- **Aluno**: Consulta treinos, agenda avaliações, visualiza evolução
- **Professor**: Registra treinos, alimenta avaliações, gera relatórios
- **Administrador**: Exporta dados para sistema financeiro, controla modalidades
- **Médico**: Consulta/atualiza avaliações físicas, gerencia agenda
- **Sistema Financeiro**: Integração externa para cobrança e comissões

### Módulos do Sistema
1. **Módulo Local**: Computadores na academia para treino diário
2. **Módulo Web**: Acesso via navegador/celular para consultas e agendamento

### Funcionalidades Principais (User Stories)
- Consulta de treinos diários
- Agendamento de avaliações físicas e aulas
- Consulta de evolução física
- Comunicação aluno-professor
- Registro de treinos programados
- Relatórios de evolução
- Exportação para sistema financeiro
- Controle de modalidades e turmas

## Padrões de Documentação

### Markdown
- Usar cabeçalhos hierárquicos (H1 para título, H2 para seções)
- Tabelas para especificação de casos de uso
- Listas para fluxos alternativos e exceções

### PlantUML
- Usar `@startuml` e `@enduml` como delimitadores
- Nomear os diagramas com `title`
- Usar português para todos os elementos
- Seguir estereótipos UML padrão

### Especificação de Casos de Uso
Cada caso de uso deve conter:
- Nome e identificador (UC-XX)
- Descrição breve
- Atores envolvidos
- Pré-condições e pós-condições
- Fluxo principal
- Fluxos alternativos
- Fluxos de exceção
