# Seção 2 – Especificação de Caso de Uso

## 2.1 Introdução

Esta seção detalha a especificação do caso de uso principal do ator **Aluno** no Sistema de Gestão Academia. O caso de uso selecionado é o **UC01 - Agendar Avaliação Física**, que permite ao aluno solicitar e agendar suas avaliações físicas periódicas através do módulo web.

A especificação contempla pré-condições, fluxo principal, fluxos alternativos, fluxos de exceção e pós-condições, evidenciando as relações entre os diferentes fluxos.

---

## 2.2 UC01 - Agendar Avaliação Física

### Informações Gerais

| Campo | Descrição |
|-------|-----------|
| **Identificador** | UC01 |
| **Nome** | Agendar Avaliação Física |
| **Ator Principal** | Aluno |
| **Atores Secundários** | Professor (notificado) |
| **Descrição** | Possibilita ao aluno agendar uma avaliação física periódica através do sistema web, escolhendo data, horário e tipo de avaliação desejada. |
| **Prioridade** | Alta |
| **Frequência de Uso** | Mensal/Trimestral |

---

### Pré-condições

| ID | Pré-condição |
|----|--------------|
| PRE01 | O aluno deve possuir matrícula ativa na academia |
| PRE02 | O aluno deve estar autenticado no sistema |
| PRE03 | Devem existir horários disponíveis para agendamento |
| PRE04 | O módulo web deve estar acessível |

---

### Pós-condições

| ID | Pós-condição |
|----|--------------|
| POS01 | A avaliação física é registrada no sistema com status "Agendada" |
| POS02 | O horário selecionado fica indisponível para outros alunos |
| POS03 | Notificação de confirmação é enviada ao aluno |
| POS04 | O profissional responsável é notificado sobre o novo agendamento |

---

### Fluxo Principal (FP)

| Passo | Ator | Sistema |
|-------|------|---------|
| 1 | O aluno acessa o sistema através do navegador ou aplicativo | - |
| 2 | - | O sistema apresenta a tela de autenticação |
| 3 | O aluno informa suas credenciais de acesso | - |
| 4 | - | O sistema valida as credenciais e apresenta o menu principal |
| 5 | O aluno seleciona "Agendar Avaliação Física" | - |
| 6 | - | O sistema apresenta os tipos de avaliação disponíveis (Completa, Parcial, Bioimpedância) |
| 7 | O aluno escolhe o tipo de avaliação desejado | - |
| 8 | - | O sistema exibe o calendário com as datas e horários disponíveis |
| 9 | O aluno seleciona a data desejada | - |
| 10 | - | O sistema exibe os horários disponíveis para a data selecionada |
| 11 | O aluno escolhe o horário | - |
| 12 | - | O sistema apresenta o resumo do agendamento para confirmação |
| 13 | O aluno confirma o agendamento | - |
| 14 | - | O sistema registra o agendamento e reserva o horário |
| 15 | - | O sistema dispara notificação de confirmação ao aluno |
| 16 | - | O sistema dispara notificação ao profissional responsável |
| 17 | - | O sistema exibe mensagem de sucesso e retorna ao menu |

---

### Fluxos Alternativos

#### FA01 - Nenhum horário disponível na data selecionada

**Condição de ativação:** No passo 10 do fluxo principal, não existem horários disponíveis para a data escolhida.

| Passo | Ator | Sistema |
|-------|------|---------|
| 10a.1 | - | O sistema identifica que não há horários disponíveis |
| 10a.2 | - | O sistema exibe alerta: "Não há horários disponíveis para esta data" |
| 10a.3 | - | O sistema sugere as próximas três datas com disponibilidade |
| 10a.4 | O aluno pode escolher uma das datas sugeridas ou voltar ao calendário | - |
| 10a.5 | - | Se escolher data sugerida, continua no passo 10 do FP; caso contrário, retorna ao passo 8 |

---

#### FA02 - Aluno já possui avaliação agendada

**Condição de ativação:** No passo 5 do fluxo principal, o sistema identifica que o aluno já possui uma avaliação agendada.

| Passo | Ator | Sistema |
|-------|------|---------|
| 5a.1 | - | O sistema detecta agendamento existente |
| 5a.2 | - | O sistema exibe informações do agendamento atual |
| 5a.3 | - | O sistema oferece opções: "Manter agendamento" ou "Reagendar" |
| 5a.4 | O aluno seleciona a opção desejada | - |
| 5a.5 | - | Se "Manter", retorna ao menu; se "Reagendar", o sistema cancela o anterior e continua no passo 6 do FP |

---

#### FA03 - Cancelar durante o processo

**Condição de ativação:** Em qualquer passo entre 5 e 12, o aluno opta por cancelar a operação.

| Passo | Ator | Sistema |
|-------|------|---------|
| Xa.1 | O aluno seleciona "Cancelar" ou "Voltar" | - |
| Xa.2 | - | O sistema solicita confirmação do cancelamento |
| Xa.3 | O aluno confirma o cancelamento | - |
| Xa.4 | - | O sistema descarta os dados e retorna ao menu principal |

---

### Fluxos de Exceção

#### FE01 - Falha na autenticação

**Condição de ativação:** No passo 4 do fluxo principal, as credenciais informadas são inválidas.

| Passo | Ator | Sistema |
|-------|------|---------|
| 4a.1 | - | O sistema detecta credenciais inválidas |
| 4a.2 | - | O sistema registra a tentativa falha |
| 4a.3 | - | O sistema exibe: "Usuário ou senha incorretos" |
| 4a.4 | - | Se quantidade de tentativas < 3: retorna ao passo 2 do FP |
| 4a.5 | - | Se quantidade de tentativas >= 3: sistema bloqueia acesso por 30 minutos |
| 4a.6 | - | O caso de uso é encerrado |

---

#### FE02 - Conflito de horário

**Condição de ativação:** No passo 14 do fluxo principal, o horário foi reservado por outro aluno durante o processo.

| Passo | Ator | Sistema |
|-------|------|---------|
| 14a.1 | - | O sistema detecta que o horário já está ocupado |
| 14a.2 | - | O sistema exibe: "Este horário acabou de ser reservado por outro aluno" |
| 14a.3 | - | O sistema atualiza a lista de horários disponíveis |
| 14a.4 | - | Retorna ao passo 10 do FP com horários atualizados |

---

#### FE03 - Falha de conexão

**Condição de ativação:** Durante qualquer passo, ocorre perda de conexão com o servidor.

| Passo | Ator | Sistema |
|-------|------|---------|
| Xa.1 | - | O sistema detecta falha na comunicação |
| Xa.2 | - | O sistema exibe: "Falha de conexão. Verifique sua internet e tente novamente." |
| Xa.3 | - | O sistema armazena os dados preenchidos localmente (se possível) |
| Xa.4 | - | O sistema oferece opção "Tentar novamente" |
| Xa.5 | O aluno pode tentar novamente ou abandonar | - |

---

### Regras de Negócio

| ID | Regra |
|----|-------|
| RN01 | O aluno pode ter no máximo uma avaliação física agendada por vez |
| RN02 | O agendamento deve ser feito com no mínimo 24 horas de antecedência |
| RN03 | O cancelamento deve ser feito com no mínimo 12 horas de antecedência |
| RN04 | Horários disponíveis são de segunda a sexta, das 6h às 21h |
| RN05 | Cada avaliação tem duração de 1 hora |
| RN06 | O bloqueio por tentativas de login é de 30 minutos |

---

### Requisitos Não Funcionais

| ID | Requisito |
|----|-----------|
| RNF01 | O calendário deve carregar em no máximo 2 segundos |
| RNF02 | O sistema deve suportar acesso simultâneo de múltiplos usuários |
| RNF03 | As notificações devem ser enviadas em até 5 minutos após o agendamento |
| RNF04 | A interface deve ser responsiva para dispositivos móveis |
| RNF05 | Os dados devem ser transmitidos com criptografia SSL/TLS |

---

### Diagrama de Relacionamento entre Fluxos

```
                    ┌──────────────────────────────────────────┐
                    │           FLUXO PRINCIPAL                │
                    │                                          │
┌───────────┐       │  1. Acessa sistema web                   │
│   INÍCIO  │──────►│  2. Apresenta login                      │
└───────────┘       │  3. Informa credenciais                  │
                    │  4. Valida acesso ───────────────────────┼──► FE01 (Falha autenticação)
                    │  5. Seleciona "Agendar Avaliação" ───────┼──► FA02 (Já possui agendamento)
                    │  6. Exibe tipos de avaliação             │
                    │  7. Escolhe tipo                         │
                    │  8. Exibe calendário                     │
                    │  9. Seleciona data                       │
                    │ 10. Exibe horários ──────────────────────┼──► FA01 (Sem horários)
                    │ 11. Escolhe horário                      │
                    │ 12. Exibe resumo ────────────────────────┼──► FA03 (Cancelar)
                    │ 13. Confirma agendamento                 │
                    │ 14. Registra e reserva ──────────────────┼──► FE02 (Conflito horário)
                    │ 15-16. Envia notificações                │
                    │ 17. Mensagem de sucesso                  │
                    │         │                                │──► FE03 (Falha conexão)
                    │         ▼                                │
                    │      ┌─────┐                             │
                    │      │ FIM │                             │
                    │      └─────┘                             │
                    └──────────────────────────────────────────┘
```

---

### Observações

1. Este caso de uso atende à história de usuário: *"Como aluno, quero agendar minhas avaliações físicas periódicas a partir do site, para poder concentrar minhas atividades na academia."*

2. O caso de uso inclui implicitamente a autenticação (UC19 - Realizar Login) nos passos 2 a 4.

3. O caso de uso estende para notificações (UC20 - Disparar Notificação) nos passos 15 e 16.

4. O agendamento realizado será utilizado pelo professor no UC08 (Registrar Avaliação Física).
