# Seção 2 – Especificação de Casos de Uso

## 2.1 Introdução

Esta seção apresenta a especificação detalhada dos casos de uso identificados para o Sistema Academia. Cada caso de uso é descrito com seus fluxos principal, alternativos e de exceção, além das pré-condições e pós-condições necessárias.

---

## 2.2 Casos de Uso do Aluno

### UC01 - Consultar Treino Diário

| Campo | Descrição |
|-------|-----------|
| **Identificador** | UC01 |
| **Nome** | Consultar Treino Diário |
| **Ator Principal** | Aluno |
| **Descrição** | Permite ao aluno consultar seu treino programado para o dia atual através dos computadores localizados na academia. |
| **Pré-condições** | - Aluno deve estar autenticado no sistema<br>- Aluno deve ter treino cadastrado para a data atual |
| **Pós-condições** | - Treino diário é exibido para o aluno<br>- Registro de consulta é armazenado para controle de frequência |

**Fluxo Principal:**

1. O aluno acessa o terminal na academia
2. O sistema solicita autenticação (include UC19)
3. O aluno fornece suas credenciais
4. O sistema valida as credenciais e exibe o menu principal
5. O aluno seleciona a opção "Consultar Treino Diário"
6. O sistema recupera o treino programado para a data atual
7. O sistema exibe a lista de exercícios com séries, repetições e cargas
8. O aluno visualiza e confirma a consulta
9. O sistema registra a frequência do aluno

**Fluxos Alternativos:**

- **FA01 - Treino não cadastrado:**
  1. No passo 6, se não houver treino para a data atual
  2. O sistema exibe mensagem informando ausência de treino
  3. O sistema sugere contato com o professor
  4. Retorna ao menu principal

- **FA02 - Visualizar treino de outra data:**
  1. No passo 5, o aluno seleciona "Consultar Treino por Data"
  2. O aluno informa a data desejada
  3. O sistema recupera e exibe o treino da data informada

**Fluxos de Exceção:**

- **FE01 - Falha de autenticação:**
  1. No passo 4, se as credenciais forem inválidas
  2. O sistema exibe mensagem de erro
  3. Retorna ao passo 2

- **FE02 - Sistema indisponível:**
  1. Em qualquer passo, se o sistema estiver indisponível
  2. O sistema exibe mensagem de erro técnico
  3. O caso de uso é encerrado

---

### UC02 - Agendar Avaliação Física

| Campo | Descrição |
|-------|-----------|
| **Identificador** | UC02 |
| **Nome** | Agendar Avaliação Física |
| **Ator Principal** | Aluno |
| **Descrição** | Permite ao aluno agendar uma avaliação física periódica através do módulo web. |
| **Pré-condições** | - Aluno deve estar autenticado no sistema<br>- Deve haver horários disponíveis para agendamento |
| **Pós-condições** | - Avaliação física é agendada<br>- Notificação é enviada ao aluno e ao profissional responsável |

**Fluxo Principal:**

1. O aluno acessa o sistema via web ou aplicativo móvel
2. O sistema solicita autenticação (include UC19)
3. O aluno seleciona a opção "Agendar Avaliação Física"
4. O sistema exibe os tipos de avaliação disponíveis
5. O aluno seleciona o tipo de avaliação desejado
6. O sistema exibe o calendário com horários disponíveis
7. O aluno seleciona a data e horário
8. O sistema exibe resumo do agendamento
9. O aluno confirma o agendamento
10. O sistema registra o agendamento
11. O sistema envia notificação de confirmação (extend UC20)

**Fluxos Alternativos:**

- **FA01 - Sem horários disponíveis:**
  1. No passo 6, se não houver horários disponíveis
  2. O sistema sugere datas alternativas no próximo período
  3. O aluno pode selecionar uma nova data ou cancelar

- **FA02 - Reagendar avaliação existente:**
  1. No passo 3, o sistema identifica avaliação já agendada
  2. O sistema oferece opção de reagendamento
  3. O aluno confirma o reagendamento
  4. Continua no passo 6

**Fluxos de Exceção:**

- **FE01 - Conflito de horário:**
  1. No passo 9, se o horário foi ocupado por outro aluno
  2. O sistema informa o conflito
  3. Retorna ao passo 6 com horários atualizados

---

### UC03 - Agendar Aula em Modalidade

| Campo | Descrição |
|-------|-----------|
| **Identificador** | UC03 |
| **Nome** | Agendar Aula em Modalidade |
| **Ator Principal** | Aluno |
| **Descrição** | Permite ao aluno agendar aulas nas diversas modalidades oferecidas pela academia. |
| **Pré-condições** | - Aluno deve estar autenticado<br>- Aluno deve estar matriculado na modalidade<br>- Deve haver vagas disponíveis na turma |
| **Pós-condições** | - Aula é agendada<br>- Vaga na turma é reservada<br>- Notificação é enviada |

**Fluxo Principal:**

1. O aluno acessa o sistema via web
2. O sistema solicita autenticação (include UC19)
3. O aluno seleciona "Agendar Aula"
4. O sistema exibe as modalidades em que o aluno está matriculado
5. O aluno seleciona a modalidade desejada
6. O sistema exibe as turmas e horários disponíveis
7. O aluno seleciona a turma e horário
8. O sistema verifica disponibilidade de vagas
9. O sistema confirma o agendamento
10. O sistema envia notificação (extend UC20)

**Fluxos Alternativos:**

- **FA01 - Turma lotada:**
  1. No passo 8, se não houver vagas
  2. O sistema oferece opção de lista de espera
  3. O aluno pode entrar na lista ou escolher outra turma

**Fluxos de Exceção:**

- **FE01 - Modalidade não contratada:**
  1. No passo 5, se o aluno tentar acessar modalidade não contratada
  2. O sistema informa a restrição
  3. O sistema sugere contato com a administração

---

### UC04 - Consultar Evolução Física

| Campo | Descrição |
|-------|-----------|
| **Identificador** | UC04 |
| **Nome** | Consultar Evolução Física |
| **Ator Principal** | Aluno |
| **Descrição** | Permite ao aluno visualizar sua evolução física ao longo do tempo, incluindo medidas, peso e indicadores de desempenho. |
| **Pré-condições** | - Aluno deve estar autenticado<br>- Aluno deve ter pelo menos uma avaliação física registrada |
| **Pós-condições** | - Dados de evolução são exibidos |

**Fluxo Principal:**

1. O aluno acessa o sistema via web
2. O sistema solicita autenticação (include UC19)
3. O aluno seleciona "Minha Evolução"
4. O sistema recupera histórico de avaliações físicas
5. O sistema exibe gráficos e indicadores de evolução
6. O aluno pode filtrar por período ou tipo de medida
7. O aluno visualiza os dados

**Fluxos Alternativos:**

- **FA01 - Sem avaliações registradas:**
  1. No passo 4, se não houver avaliações
  2. O sistema informa ausência de dados
  3. O sistema sugere agendamento de avaliação

- **FA02 - Exportar dados:**
  1. No passo 7, o aluno seleciona "Exportar"
  2. O sistema gera arquivo PDF com os dados
  3. O aluno faz download do arquivo

---

### UC05 - Consultar Agenda

| Campo | Descrição |
|-------|-----------|
| **Identificador** | UC05 |
| **Nome** | Consultar Agenda |
| **Ator Principal** | Aluno |
| **Descrição** | Permite ao aluno visualizar sua agenda de atividades, incluindo treinos, aulas e avaliações agendadas. |
| **Pré-condições** | - Aluno deve estar autenticado |
| **Pós-condições** | - Agenda é exibida |

**Fluxo Principal:**

1. O aluno acessa o sistema via web
2. O aluno seleciona "Minha Agenda"
3. O sistema recupera todos os compromissos do aluno
4. O sistema exibe calendário com atividades
5. O aluno pode navegar entre datas
6. O aluno pode clicar em um evento para ver detalhes

**Fluxos Alternativos:**

- **FA01 - Cancelar compromisso:**
  1. No passo 6, o aluno seleciona "Cancelar"
  2. O sistema solicita confirmação
  3. O sistema cancela o agendamento
  4. O sistema envia notificação de cancelamento

---

### UC06 - Comunicar com Professor

| Campo | Descrição |
|-------|-----------|
| **Identificador** | UC06 |
| **Nome** | Comunicar com Professor |
| **Atores** | Aluno, Professor |
| **Descrição** | Permite a comunicação direta entre aluno e professor para acompanhamento personalizado das atividades. |
| **Pré-condições** | - Usuário deve estar autenticado<br>- Aluno deve ter professor vinculado |
| **Pós-condições** | - Mensagem é enviada e registrada |

**Fluxo Principal:**

1. O usuário (aluno ou professor) acessa o sistema
2. O usuário seleciona "Mensagens"
3. O sistema exibe lista de conversas
4. O usuário seleciona ou inicia uma conversa
5. O usuário digita a mensagem
6. O usuário envia a mensagem
7. O sistema registra e entrega a mensagem
8. O destinatário recebe notificação

**Fluxos Alternativos:**

- **FA01 - Anexar arquivo:**
  1. No passo 5, o usuário seleciona "Anexar"
  2. O usuário seleciona arquivo (foto, documento)
  3. O sistema valida e anexa o arquivo
  4. Continua no passo 6

---

## 2.3 Casos de Uso do Professor

### UC07 - Registrar Treino Programado

| Campo | Descrição |
|-------|-----------|
| **Identificador** | UC07 |
| **Nome** | Registrar Treino Programado |
| **Ator Principal** | Professor |
| **Descrição** | Permite ao professor criar e registrar o programa de treino personalizado para cada aluno. |
| **Pré-condições** | - Professor deve estar autenticado<br>- Aluno deve estar cadastrado e vinculado ao professor |
| **Pós-condições** | - Treino é registrado e disponibilizado para o aluno |

**Fluxo Principal:**

1. O professor acessa o sistema
2. O sistema solicita autenticação (include UC19)
3. O professor seleciona "Gerenciar Treinos"
4. O professor seleciona o aluno
5. O sistema exibe histórico de treinos do aluno
6. O professor seleciona "Novo Treino"
7. O professor define período de vigência do treino
8. O professor adiciona exercícios com séries, repetições e cargas
9. O professor pode adicionar observações e instruções
10. O professor confirma o registro
11. O sistema salva e disponibiliza o treino

**Fluxos Alternativos:**

- **FA01 - Copiar treino existente:**
  1. No passo 6, o professor seleciona "Copiar Treino"
  2. O professor seleciona treino base (do mesmo aluno ou de outro)
  3. O sistema copia os exercícios
  4. O professor ajusta conforme necessário
  5. Continua no passo 10

- **FA02 - Usar modelo de treino:**
  1. No passo 6, o professor seleciona "Usar Modelo"
  2. O sistema exibe modelos de treino pré-definidos
  3. O professor seleciona e personaliza o modelo

**Fluxos de Exceção:**

- **FE01 - Aluno sem avaliação recente:**
  1. No passo 4, se o aluno não tiver avaliação física recente
  2. O sistema exibe alerta
  3. O professor pode prosseguir ou agendar avaliação

---

### UC08 - Registrar Avaliação Física

| Campo | Descrição |
|-------|-----------|
| **Identificador** | UC08 |
| **Nome** | Registrar Avaliação Física |
| **Ator Principal** | Professor |
| **Descrição** | Permite ao professor registrar os dados da avaliação física realizada com o aluno. |
| **Pré-condições** | - Professor deve estar autenticado<br>- Avaliação deve estar agendada ou ser criada manualmente |
| **Pós-condições** | - Avaliação é registrada<br>- Dados ficam disponíveis para consulta do aluno e médico |

**Fluxo Principal:**

1. O professor acessa o sistema
2. O professor seleciona "Avaliações"
3. O sistema exibe avaliações agendadas para o dia
4. O professor seleciona a avaliação a ser registrada
5. O sistema exibe formulário de avaliação
6. O professor preenche medidas corporais (peso, altura, percentual de gordura, etc.)
7. O professor registra resultados de testes físicos
8. O professor adiciona observações
9. O professor confirma o registro
10. O sistema salva a avaliação
11. O sistema notifica o aluno (extend UC20)

**Fluxos Alternativos:**

- **FA01 - Avaliação não agendada:**
  1. No passo 3, o professor seleciona "Nova Avaliação"
  2. O professor busca e seleciona o aluno
  3. Continua no passo 5

---

### UC09 - Registrar Evolução do Aluno

| Campo | Descrição |
|-------|-----------|
| **Identificador** | UC09 |
| **Nome** | Registrar Evolução do Aluno |
| **Ator Principal** | Professor |
| **Descrição** | Permite ao professor registrar observações e marcos de evolução do aluno durante o acompanhamento. |
| **Pré-condições** | - Professor deve estar autenticado<br>- Aluno deve estar vinculado ao professor |
| **Pós-condições** | - Registro de evolução é salvo |

**Fluxo Principal:**

1. O professor acessa o sistema
2. O professor seleciona "Acompanhamento"
3. O professor seleciona o aluno
4. O sistema exibe histórico de evolução
5. O professor seleciona "Novo Registro"
6. O professor informa tipo de evolução (força, resistência, flexibilidade, etc.)
7. O professor registra observações e métricas
8. O professor pode anexar fotos comparativas
9. O professor confirma o registro
10. O sistema salva os dados

---

### UC10 - Gerar Relatório de Evolução

| Campo | Descrição |
|-------|-----------|
| **Identificador** | UC10 |
| **Nome** | Gerar Relatório de Evolução |
| **Ator Principal** | Professor |
| **Descrição** | Permite ao professor gerar relatórios sobre a evolução dos alunos, individualmente ou em grupo. |
| **Pré-condições** | - Professor deve estar autenticado<br>- Deve haver dados de evolução registrados |
| **Pós-condições** | - Relatório é gerado e disponibilizado |

**Fluxo Principal:**

1. O professor acessa o sistema
2. O sistema solicita autenticação (include UC19)
3. O professor seleciona "Relatórios"
4. O sistema exibe tipos de relatório disponíveis
5. O professor seleciona tipo de relatório (individual ou grupo)
6. O professor define filtros (período, modalidade, alunos)
7. O sistema processa os dados
8. O sistema exibe prévia do relatório
9. O professor pode exportar em PDF ou Excel
10. O sistema gera o arquivo para download

**Fluxos Alternativos:**

- **FA01 - Relatório comparativo:**
  1. No passo 5, o professor seleciona "Relatório Comparativo"
  2. O professor seleciona dois ou mais alunos
  3. O sistema gera comparativo de evolução

---

## 2.4 Casos de Uso do Administrador

### UC11 - Exportar Atividades Extras

| Campo | Descrição |
|-------|-----------|
| **Identificador** | UC11 |
| **Nome** | Exportar Atividades Extras |
| **Ator Principal** | Administrador |
| **Ator Secundário** | Sistema Financeiro |
| **Descrição** | Exporta dados de atividades extras realizadas pelos alunos para integração com o sistema financeiro. |
| **Pré-condições** | - Administrador deve estar autenticado<br>- Deve haver atividades extras registradas |
| **Pós-condições** | - Arquivo de exportação é gerado<br>- Dados são enviados ao Sistema Financeiro |

**Fluxo Principal:**

1. O administrador acessa o sistema
2. O administrador seleciona "Integrações"
3. O administrador seleciona "Exportar Atividades Extras"
4. O sistema exibe filtros de período e tipo de atividade
5. O administrador define os parâmetros de exportação
6. O sistema gera prévia dos dados
7. O administrador confirma a exportação
8. O sistema gera arquivo no formato do Sistema Financeiro
9. O sistema envia arquivo para o Sistema Financeiro
10. O sistema registra log da exportação

**Fluxos de Exceção:**

- **FE01 - Falha na integração:**
  1. No passo 9, se houver falha de comunicação
  2. O sistema registra erro
  3. O sistema permite download manual do arquivo
  4. O administrador pode tentar reenvio posteriormente

---

### UC12 - Exportar Frequência

| Campo | Descrição |
|-------|-----------|
| **Identificador** | UC12 |
| **Nome** | Exportar Frequência |
| **Ator Principal** | Administrador |
| **Ator Secundário** | Sistema Financeiro |
| **Descrição** | Exporta dados de frequência dos alunos para controle financeiro. |
| **Pré-condições** | - Administrador deve estar autenticado |
| **Pós-condições** | - Dados de frequência são exportados |

**Fluxo Principal:**

1. O administrador acessa o sistema
2. O administrador seleciona "Integrações"
3. O administrador seleciona "Exportar Frequência"
4. O administrador define período de exportação
5. O sistema recupera registros de frequência
6. O sistema gera arquivo de exportação
7. O sistema envia ao Sistema Financeiro

---

### UC13 - Exportar Estatísticas por Professor

| Campo | Descrição |
|-------|-----------|
| **Identificador** | UC13 |
| **Nome** | Exportar Estatísticas por Professor |
| **Ator Principal** | Administrador |
| **Ator Secundário** | Sistema Financeiro |
| **Descrição** | Exporta avaliações e estatísticas de evolução dos alunos agrupadas por professor para cálculo de comissões. |
| **Pré-condições** | - Administrador deve estar autenticado<br>- Deve haver avaliações registradas no período |
| **Pós-condições** | - Estatísticas são exportadas para cálculo de comissão |

**Fluxo Principal:**

1. O administrador acessa o sistema
2. O administrador seleciona "Integrações"
3. O administrador seleciona "Estatísticas por Professor"
4. O administrador define período de apuração
5. O sistema calcula estatísticas de evolução por professor
6. O sistema gera relatório com indicadores
7. O sistema exporta para o Sistema Financeiro

---

### UC14 - Consultar Alunos por Modalidade

| Campo | Descrição |
|-------|-----------|
| **Identificador** | UC14 |
| **Nome** | Consultar Alunos por Modalidade |
| **Ator Principal** | Administrador |
| **Descrição** | Permite visualizar o número de alunos matriculados em cada modalidade oferecida pela academia. |
| **Pré-condições** | - Administrador deve estar autenticado |
| **Pós-condições** | - Relatório de alunos por modalidade é exibido |

**Fluxo Principal:**

1. O administrador acessa o sistema
2. O administrador seleciona "Modalidades"
3. O administrador seleciona "Alunos por Modalidade"
4. O sistema recupera dados de matrícula
5. O sistema exibe lista de modalidades com quantidade de alunos
6. O administrador pode expandir para ver lista de alunos
7. O administrador pode exportar relatório

---

### UC15 - Gerenciar Modalidades

| Campo | Descrição |
|-------|-----------|
| **Identificador** | UC15 |
| **Nome** | Gerenciar Modalidades |
| **Ator Principal** | Administrador |
| **Descrição** | Permite cadastrar, editar e gerenciar as modalidades e turmas oferecidas pela academia. |
| **Pré-condições** | - Administrador deve estar autenticado |
| **Pós-condições** | - Modalidades/turmas são atualizadas |

**Fluxo Principal:**

1. O administrador acessa o sistema
2. O administrador seleciona "Modalidades"
3. O sistema exibe lista de modalidades cadastradas
4. O administrador pode adicionar, editar ou desativar modalidades
5. Para cada modalidade, pode gerenciar turmas
6. O sistema salva as alterações

**Fluxos Alternativos:**

- **FA01 - Criar nova modalidade:**
  1. O administrador seleciona "Nova Modalidade"
  2. Informa nome, descrição, capacidade máxima
  3. Define horários disponíveis
  4. Salva a modalidade

- **FA02 - Gerenciar turmas:**
  1. O administrador seleciona uma modalidade
  2. Visualiza turmas existentes
  3. Pode criar, editar ou encerrar turmas
  4. Define professor responsável por cada turma

---

## 2.5 Casos de Uso do Médico

### UC16 - Consultar Histórico de Avaliações

| Campo | Descrição |
|-------|-----------|
| **Identificador** | UC16 |
| **Nome** | Consultar Histórico de Avaliações |
| **Ator Principal** | Médico |
| **Descrição** | Permite ao médico consultar o histórico completo de avaliações físicas de um aluno. |
| **Pré-condições** | - Médico deve estar autenticado<br>- Aluno deve ter avaliações registradas |
| **Pós-condições** | - Histórico de avaliações é exibido |

**Fluxo Principal:**

1. O médico acessa o sistema via web
2. O sistema solicita autenticação (include UC19)
3. O médico seleciona "Avaliações"
4. O médico busca o aluno por nome ou matrícula
5. O sistema exibe lista de avaliações do aluno
6. O médico pode visualizar detalhes de cada avaliação
7. O médico pode comparar avaliações de diferentes datas

---

### UC17 - Atualizar Avaliação Física

| Campo | Descrição |
|-------|-----------|
| **Identificador** | UC17 |
| **Nome** | Atualizar Avaliação Física |
| **Ator Principal** | Médico |
| **Descrição** | Permite ao médico adicionar informações médicas às avaliações físicas periódicas. |
| **Pré-condições** | - Médico deve estar autenticado<br>- Deve haver avaliação física para atualização |
| **Pós-condições** | - Avaliação é atualizada com dados médicos |

**Fluxo Principal:**

1. O médico acessa o sistema
2. O médico seleciona avaliação a ser atualizada
3. O sistema exibe formulário com dados existentes
4. O médico adiciona parecer médico
5. O médico pode adicionar restrições ou recomendações
6. O médico confirma a atualização
7. O sistema salva as alterações

---

### UC18 - Consultar Agenda Médica

| Campo | Descrição |
|-------|-----------|
| **Identificador** | UC18 |
| **Nome** | Consultar Agenda Médica |
| **Ator Principal** | Médico |
| **Descrição** | Permite ao médico visualizar sua agenda de atendimentos na academia via web. |
| **Pré-condições** | - Médico deve estar autenticado |
| **Pós-condições** | - Agenda é exibida |

**Fluxo Principal:**

1. O médico acessa o sistema via web
2. O médico seleciona "Minha Agenda"
3. O sistema exibe calendário com atendimentos agendados
4. O médico pode navegar entre datas
5. O médico pode ver detalhes de cada agendamento

---

## 2.6 Casos de Uso Auxiliares

### UC19 - Autenticar Usuário

| Campo | Descrição |
|-------|-----------|
| **Identificador** | UC19 |
| **Nome** | Autenticar Usuário |
| **Atores** | Aluno, Professor, Administrador, Médico |
| **Descrição** | Valida as credenciais do usuário para acesso ao sistema. |
| **Pré-condições** | - Usuário deve ter cadastro ativo no sistema |
| **Pós-condições** | - Sessão é iniciada<br>- Permissões são carregadas conforme perfil |

**Fluxo Principal:**

1. O sistema exibe tela de login
2. O usuário informa e-mail/matrícula e senha
3. O sistema valida as credenciais
4. O sistema verifica status do cadastro
5. O sistema carrega permissões do perfil
6. O sistema redireciona para área apropriada

**Fluxos Alternativos:**

- **FA01 - Recuperar senha:**
  1. O usuário seleciona "Esqueci minha senha"
  2. O sistema solicita e-mail
  3. O sistema envia link de recuperação
  4. O usuário cria nova senha

- **FA02 - Primeiro acesso:**
  1. O sistema identifica primeiro acesso
  2. O sistema solicita criação de senha
  3. O sistema solicita aceitação dos termos de uso

**Fluxos de Exceção:**

- **FE01 - Credenciais inválidas:**
  1. O sistema informa erro de autenticação
  2. Após 3 tentativas, conta é bloqueada temporariamente

- **FE02 - Usuário inativo:**
  1. O sistema informa que cadastro está inativo
  2. O sistema orienta contato com administração

---

### UC20 - Enviar Notificação

| Campo | Descrição |
|-------|-----------|
| **Identificador** | UC20 |
| **Nome** | Enviar Notificação |
| **Descrição** | Caso de uso de extensão que envia notificações aos usuários sobre eventos do sistema. |
| **Pré-condições** | - Usuário deve ter canal de notificação configurado |
| **Pós-condições** | - Notificação é enviada e registrada |

**Fluxo Principal:**

1. O caso de uso chamador solicita envio de notificação
2. O sistema identifica destinatário(s)
3. O sistema verifica preferências de notificação
4. O sistema formata mensagem conforme canal (e-mail, push, SMS)
5. O sistema envia notificação
6. O sistema registra log de envio

**Fluxos Alternativos:**

- **FA01 - Múltiplos destinatários:**
  1. O sistema processa cada destinatário
  2. Aplica preferências individuais

**Fluxos de Exceção:**

- **FE01 - Falha no envio:**
  1. O sistema registra falha
  2. O sistema agenda nova tentativa
