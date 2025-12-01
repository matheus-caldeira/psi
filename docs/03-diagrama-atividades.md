# Seção 3 – Diagrama de Atividades

## 3.1 Introdução

O diagrama de atividades representa o fluxo de trabalho e as ações executadas no caso de uso **UC01 - Consultar Treino Diário** do ator **Aluno**. Este diagrama ilustra a sequência de atividades, decisões e tratamentos de exceção que ocorrem durante a execução do processo.

O diagrama foi elaborado com base na especificação do caso de uso apresentada na Seção 2, mantendo correspondência com o fluxo principal, fluxos alternativos e fluxos de exceção.

---

## 3.2 UC01 - Consultar Treino Diário

### Descrição

Este diagrama representa o fluxo completo de atividades quando o aluno consulta seu treino diário através do terminal na academia. O diagrama contempla:

- **Fluxo Principal:** Autenticação, seleção do treino, exibição dos exercícios e registro de frequência
- **Fluxo Alternativo:** Tratamento para treino não cadastrado
- **Fluxo de Exceção:** Tratamento para falha de autenticação com bloqueio após 3 tentativas

### Diagrama

![Diagrama de Atividades - UC01 Consultar Treino Diário](../diagrams/atividades/uc01-consultar-treino.png)

---

## 3.3 Descrição do Fluxo

### Início do Processo

1. O aluno inicia o processo acessando o terminal físico localizado na academia
2. O sistema apresenta a tela de login solicitando autenticação

### Processo de Autenticação

3. O aluno fornece suas credenciais (matrícula e senha)
4. O sistema valida as credenciais informadas
5. **Decisão:** Se as credenciais forem válidas, prossegue para o menu principal
6. **Exceção:** Se as credenciais forem inválidas:
   - O sistema incrementa o contador de tentativas
   - Se tentativas < 3: permite nova tentativa (loop)
   - Se tentativas >= 3: bloqueia o acesso temporariamente

### Consulta do Treino

7. O sistema exibe o menu principal com as opções disponíveis
8. O aluno seleciona a opção "Consultar Treino Diário"
9. O sistema busca o treino programado para a data atual

### Exibição do Treino

10. **Decisão:** Se o treino for encontrado:
    - O sistema exibe a lista completa de exercícios
    - O aluno visualiza o treino
    - O sistema registra a frequência do aluno
11. **Alternativo:** Se não houver treino cadastrado:
    - O sistema exibe mensagem informando ausência de treino
    - O sistema sugere contato com o professor

### Fim do Processo

12. O processo é encerrado após a consulta ou em caso de bloqueio

---

## 3.4 Elementos Utilizados no Diagrama

| Elemento | Símbolo | Descrição |
|----------|---------|-----------|
| **Início** | Círculo preenchido | Ponto de início do fluxo de atividades |
| **Fim** | Círculo com borda dupla | Ponto de término do fluxo |
| **Atividade** | Retângulo arredondado | Ação executada por ator ou sistema |
| **Decisão** | Losango | Ponto de ramificação condicional com condições "sim" e "não" |
| **Loop (Repeat)** | Estrutura de repetição | Permite retornar a um ponto anterior do fluxo |
| **Nota** | Retângulo com dobra | Informação adicional sobre uma atividade |

---

## 3.5 Correspondência com a Especificação do Caso de Uso

| Elemento do Diagrama | Elemento da Especificação |
|---------------------|---------------------------|
| Aluno acessa terminal | FP - Passo 1 |
| Sistema solicita autenticação | FP - Passo 2 |
| Aluno fornece credenciais | FP - Passo 3 |
| Sistema valida credenciais | FP - Passo 4 |
| Credenciais inválidas (loop) | FE01 - Falha de autenticação |
| Bloqueio após 3 tentativas | FE01 - Passos 4a.5 e 4a.6 |
| Sistema exibe menu | FP - Passo 5 |
| Aluno seleciona "Consultar Treino" | FP - Passo 6 |
| Sistema busca treino | FP - Passo 7 |
| Treino não encontrado | FA01 - Treino não cadastrado |
| Sistema exibe exercícios | FP - Passo 8 |
| Aluno visualiza treino | FP - Passo 9 |
| Sistema registra frequência | FP - Passo 10 |

---

## 3.6 Observações sobre o Diagrama

1. **Nó de Decisão - Credenciais:** As saídas "sim" e "não" são mutuamente exclusivas, garantindo que o fluxo de controle não seja ambíguo.

2. **Nó de Decisão - Treino:** As saídas "sim" (treino encontrado) e "não" (treino não cadastrado) cobrem todas as possibilidades.

3. **Estrutura de Repetição:** O loop de tentativas de autenticação está bem equilibrado, com condição clara de saída (tentativas >= 3 ou autenticação bem-sucedida).

4. **Fluxo de Controle:** Em cada ponto de decisão, está claro para onde o fluxo prossegue, evitando ambiguidades.

5. **Terminação:** O diagrama possui múltiplos pontos de término (stop) para representar as diferentes formas de encerramento do caso de uso: sucesso, bloqueio por tentativas ou desistência do usuário.
