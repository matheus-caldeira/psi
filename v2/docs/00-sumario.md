# Sistema de Gestão Academia - Documentação UML

## Atividade Prática (ATP) - Design Orientado a Objetos

---

# Sumário

## [Seção 1 – Diagrama de Casos de Uso](01-diagrama-casos-uso.md)

1.1 Introdução

1.2 Atores do Sistema

1.3 Lista de Casos de Uso

1.4 Diagrama de Casos de Uso

1.5 Relacionamentos

1.6 Requisitos de Acessibilidade

---

## [Seção 2 – Especificação de Caso de Uso](02-especificacao-casos-uso.md)

2.1 Introdução

2.2 UC01 - Agendar Avaliação Física
- Informações Gerais
- Pré-condições
- Pós-condições
- Fluxo Principal
- Fluxos Alternativos (FA01, FA02, FA03)
- Fluxos de Exceção (FE01, FE02, FE03)
- Regras de Negócio
- Requisitos Não Funcionais
- Diagrama de Relacionamento entre Fluxos

---

## [Seção 3 – Diagrama de Atividades](03-diagrama-atividades.md)

3.1 Introdução

3.2 UC01 - Agendar Avaliação Física
- Descrição
- Diagrama

3.3 Descrição do Fluxo

3.4 Elementos Utilizados no Diagrama

3.5 Correspondência com a Especificação

3.6 Observações sobre o Diagrama

---

## [Seção 4 – Diagrama de Classes](04-diagrama-classes.md)

4.1 Introdução

4.2 Visão Geral da Arquitetura

4.3 Diagrama de Classes

4.4 Descrição das Classes
- Hierarquia de Indivíduos
- Classes de Programa de Treino
- Classes de Avaliação
- Classes de Atividades
- Classes de Agendamento
- Classes de Comunicação
- Classes de Integração

4.5 Enumerações

4.6 Relacionamentos

---

## Anexos

### Arquivos PlantUML

| Diagrama | Arquivo |
|----------|---------|
| Casos de Uso | [diagrams/casos-uso.puml](../diagrams/casos-uso.puml) |
| Classes | [diagrams/classes.puml](../diagrams/classes.puml) |
| Atividade - UC01 | [diagrams/atividades/uc01-agendar-avaliacao.puml](../diagrams/atividades/uc01-agendar-avaliacao.puml) |

### Como Gerar os Diagramas

```bash
# Instalar PlantUML (macOS)
brew install plantuml

# Gerar diagrama de casos de uso
plantuml diagrams/casos-uso.puml

# Gerar diagrama de classes
plantuml diagrams/classes.puml

# Gerar diagrama de atividades
plantuml diagrams/atividades/uc01-agendar-avaliacao.puml
```

---

## Informações do Projeto

**Sistema:** Sistema de Gestão Academia

**Descrição:** Solução para monitoramento e controle das atividades de alunos em academia de grande porte, contemplando programas de treino personalizados, exames físicos, acompanhamento de progresso, agendamentos e integração com sistema financeiro.

**Atores Principais:**
- Matriculado (Aluno)
- Instrutor (Professor)
- Gestor (Administrador)
- Profissional de Saúde (Médico)
- Sistema Financeiro (externo)

**Módulos:**
1. Terminal Academia (acesso local)
2. Acesso Web (navegador/dispositivos móveis)

**Caso de Uso Especificado:** UC01 - Agendar Avaliação Física (Ator: Matriculado)
