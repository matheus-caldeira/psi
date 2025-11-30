# Sistema Academia - Documentação UML

## Atividade Prática (ATP) - Design Orientado a Objetos

---

# Sumário

## [Seção 1 – Diagrama de Casos de Uso](01-diagrama-casos-uso.md)

1.1 Introdução

1.2 Atores do Sistema
- 1.2.1 Atores Primários
- 1.2.2 Atores Secundários

1.3 Lista de Casos de Uso
- Módulo Local
- Módulo Web
- Gestão de Treinos
- Gestão Administrativa
- Acompanhamento Médico
- Casos de Uso Auxiliares

1.4 Diagrama de Casos de Uso

1.5 Relacionamentos
- 1.5.1 Relacionamentos de Inclusão
- 1.5.2 Relacionamentos de Extensão

1.6 Requisitos de Acessibilidade

---

## [Seção 2 – Especificação de Casos de Uso](02-especificacao-casos-uso.md)

2.1 Introdução

2.2 Casos de Uso do Aluno
- UC01 - Consultar Treino Diário
- UC02 - Agendar Avaliação Física
- UC03 - Agendar Aula em Modalidade
- UC04 - Consultar Evolução Física
- UC05 - Consultar Agenda
- UC06 - Comunicar com Professor

2.3 Casos de Uso do Professor
- UC07 - Registrar Treino Programado
- UC08 - Registrar Avaliação Física
- UC09 - Registrar Evolução do Aluno
- UC10 - Gerar Relatório de Evolução

2.4 Casos de Uso do Administrador
- UC11 - Exportar Atividades Extras
- UC12 - Exportar Frequência
- UC13 - Exportar Estatísticas por Professor
- UC14 - Consultar Alunos por Modalidade
- UC15 - Gerenciar Modalidades

2.5 Casos de Uso do Médico
- UC16 - Consultar Histórico de Avaliações
- UC17 - Atualizar Avaliação Física
- UC18 - Consultar Agenda Médica

2.6 Casos de Uso Auxiliares
- UC19 - Autenticar Usuário
- UC20 - Enviar Notificação

---

## [Seção 3 – Diagramas de Atividades](03-diagrama-atividades.md)

3.1 Introdução

3.2 UC01 - Consultar Treino Diário

3.3 UC02 - Agendar Avaliação Física

3.4 UC07 - Registrar Treino Programado

3.5 UC08 - Registrar Avaliação Física

3.6 UC11 - Exportar Atividades Extras

3.7 UC19 - Autenticar Usuário

3.8 Elementos Utilizados nos Diagramas

---

## [Seção 4 – Diagrama de Classes](04-diagrama-classes.md)

4.1 Introdução

4.2 Visão Geral da Arquitetura

4.3 Diagrama de Classes

4.4 Descrição das Classes
- 4.4.1 Classes de Pessoa (Herança)
- 4.4.2 Classes de Treino
- 4.4.3 Classes de Avaliação
- 4.4.4 Classes de Modalidade
- 4.4.5 Classes de Agendamento
- 4.4.6 Classes de Comunicação
- 4.4.7 Classes de Integração

4.5 Enumerações

4.6 Relacionamentos
- 4.6.1 Herança
- 4.6.2 Composição
- 4.6.3 Agregação
- 4.6.4 Associações

---

## Anexos

### Arquivos PlantUML

| Diagrama | Arquivo |
|----------|---------|
| Casos de Uso | [diagrams/casos-uso.puml](../diagrams/casos-uso.puml) |
| Classes | [diagrams/classes.puml](../diagrams/classes.puml) |
| Atividade - UC01 | [diagrams/atividades/uc01-consultar-treino.puml](../diagrams/atividades/uc01-consultar-treino.puml) |
| Atividade - UC02 | [diagrams/atividades/uc02-agendar-avaliacao.puml](../diagrams/atividades/uc02-agendar-avaliacao.puml) |
| Atividade - UC07 | [diagrams/atividades/uc07-registrar-treino.puml](../diagrams/atividades/uc07-registrar-treino.puml) |
| Atividade - UC08 | [diagrams/atividades/uc08-registrar-avaliacao.puml](../diagrams/atividades/uc08-registrar-avaliacao.puml) |
| Atividade - UC11 | [diagrams/atividades/uc11-exportar-atividades.puml](../diagrams/atividades/uc11-exportar-atividades.puml) |
| Atividade - UC19 | [diagrams/atividades/uc19-autenticar-usuario.puml](../diagrams/atividades/uc19-autenticar-usuario.puml) |

### Como Gerar os Diagramas

```bash
# Instalar PlantUML (macOS)
brew install plantuml

# Gerar todos os diagramas em PNG
plantuml diagrams/*.puml
plantuml diagrams/atividades/*.puml

# Gerar em SVG (melhor qualidade)
plantuml -tsvg diagrams/*.puml
plantuml -tsvg diagrams/atividades/*.puml
```

---

## Informações do Projeto

**Sistema:** Sistema Academia - Monitoramento e Controle de Atividades

**Descrição:** Sistema para gerenciamento de atividades de alunos em uma academia de grande porte, incluindo treinos personalizados, avaliações físicas, evolução, agendamentos e integração com sistema financeiro.

**Atores Principais:**
- Aluno
- Professor
- Administrador
- Médico
- Sistema Financeiro (externo)

**Módulos:**
1. Módulo Local (terminais na academia)
2. Módulo Web (acesso via navegador/mobile)

**Requisitos Especiais:**
- Acessibilidade para portadores de necessidades especiais
- Compatibilidade com navegadores e dispositivos móveis
- Integração com sistema financeiro existente
