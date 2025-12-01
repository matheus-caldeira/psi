# Requisitos

## ATP – Etapa 1

Ao longo desta etapa, você deverá elaborar um diagrama de caso de uso a partir do cenário apresentado na
semana 1.
O que eu preciso desenvolver? Você deve criar um diagrama de casos de uso utilizando uma ferramenta
apropriada; podem ser ferramentas on-line gratuitas, como Lucidchat, Draw.IO ou qualquer outra que conheça
e com que tenha afinidade.
O que eu preciso entregar? Você deverá entregar o diagrama de casos de uso produzido. Gere uma imagem
dele e insira na seção 1 – Diagrama de casos de uso, do seu arquivo do Word. Garanta uma imagem nítida e
legível.
Para ajudá-lo na construção, você deve identificar os atores envolvidos e descrever os cenários (casos de uso)
que estão relacionados a eles. Em um caso de uso, você pode ter vários requisitos (funcionalidades) envolvidos.
Depois de identificar os atores e casos de uso, verifique quais são as relações existentes entre atores e casos de
uso.
A seguir, há um checklist para você verificar se o diagrama criado está descrito de maneira consistente e
completa.
O nome do caso de uso é significativo e inequívoco?
• O caso de uso tem um nome exclusivo?
• O nome do caso de uso é uma frase composta de verbo e substantivo (por exemplo, Retirar dinheiro)?
• O nome resume com precisão o principal objetivo do caso de uso?
A descrição resumida relata claramente o objetivo principal do caso de uso?
• Está claro, a partir da descrição, qual é o principal objetivo do caso de uso?
Os atores e as informações trocadas estão claramente definidos?
• O caso de uso está associado a um ou mais atores?
• Está claro quem executa as ações no caso de uso?
É fácil entender o que o sistema faz ao revisar o modelo?
• O diagrama de casos de uso fornece uma visão clara e concisa do objetivo e das funcionalidades do
sistema?
• Não há longas cadeias de relacionamentos do tipo include, como quando um caso de uso incluído tem
outros casos de uso? Isso pode dificultar a compreensão.
• Os casos de uso incluídos (utilizando include) são independentes dos casos de uso que os incluem?
Existem todos os relacionamentos entre casos de uso?
• Cada caso de uso incluído ou ampliado facilita a compreensão do modelo?
• Cada caso de uso concreto (que não contém include ou extend) é independente de outros casos de uso?
Todos os elementos do modelo têm nomes apropriados?
• Você verificou se não há dois casos de uso com o mesmo nome?
• Cada ator tem um nome que descreve efetivamente o papel dessa pessoa dentro do sistema?
Você considerou funções administrativas e de manutenção?
• É comum se concentrar nos usuários diários do sistema e esquecer as funções administrativas e de
manutenção, como configurar contas de usuário, gerenciar direitos de acesso, executar backups etc.
Certifique-se de capturar algum desses atores no cenário apresentado.
Após fazer todas essas verificações em seu diagrama de casos de uso, gere uma imagem dele e
insira no arquivo do Word do seu projeto.

## ATP – Etapa 2

Você deverá construir a especificação dos casos de uso referentes ao diagrama construído na semana 2. Para
ajudá-lo, um template foi disponibilizado nos materiais extras.
O que eu preciso desenvolver? Você deve especificar um caso de uso do ator Aluno. Caso tenha identificado
mais de um para esse ator, irá utilizar o caso de uso principal. Você deve especificar as precondições, fluxo
principal, fluxos alternativos, fluxos de exceção, regras de negócio e pós-condições (quando o caso de uso
finalizar).
O que eu preciso entregar? Você deverá entregar a especificação produzida na seção 2 – Especificação de caso
de uso, do seu arquivo do Word. Deixe claro qual é o caso de uso que está sendo especificado.
Para ajudá-lo na especificação, produzimos um checklist de verificação.
As precondições foram especificadas?
• Cada precondição representa um estado tangível do sistema (por exemplo, o caso de uso Retirar
dinheiro de um caixa automático tem uma precondição de que o usuário tenha uma conta)?
Os fluxos básico e alternativo são completos, corretos e consistentes?
• Está claro como o caso de uso é iniciado?
• O evento de início está claramente descrito?
• O fluxo tem um final definido?
• Cada etapa do cenário descreve algo que realmente pode acontecer e que o sistema pode detectar?
• Cada passo faz progresso em direção à meta?
• Existem etapas ausentes? Está claro como ir de um passo para o outro? A sequência de comunicação
entre os atores e os casos de uso está de acordo com as expectativas dos usuários?
• Cada passo descreve como ajuda os atores a alcançar seus objetivos?
• Cada passo é independente da tecnologia?
• As etapas estão numeradas corretamente?
• Para cada fluxo alternativo, as condições para o início dele estão claramente definidas?
• Para cada fluxo alternativo, está claro como o caso de uso termina ou em que local do fluxo básico o caso
de uso é retomado?
As pós-condições foram especificadas?
• Há garantias mínimas de que, quando o caso de uso é concluído, a pós-condição é realizada,
independentemente do sucesso? (uma garantia mínima representa uma condição que será verdadeira
quando o caso de uso terminar, independentemente de como terminar).

## ATP – Etapa 3

O que eu preciso desenvolver? Você deve elaborar um diagrama de atividades, com base em um cenário de
caso de uso do ator Aluno (o mesmo que utilizou para fazer a especificação de caso de uso). Se você identificou
mais de um caso de uso para ele, escolha apenas um para esta atividade.
O que eu preciso entregar? Você deverá entregar o diagrama de atividades produzido. Gere uma imagem dele
e insira na seção 3 – Diagrama de atividades, do seu arquivo do Word. Garanta uma imagem nítida e legível.
Para criá-lo, vale ressaltar que o uso de terminologia adequada e a nomeação apropriada de ações e atividades
são essenciais para a clareza e compreensibilidade dos diagramas de atividades.
Para auxiliá-lo no processo de construção do diagrama de atividades, preparamos alguns aspectos que você
deve levar em consideração na criação.
• Ao construir diagramas de atividades, lembre-se sempre de que apenas processos de negócios são
relevantes.
• As condições de diferentes saídas de um nó de decisão não devem se sobrepor. Caso contrário, o fluxo
de controle é ambíguo – não está claro para onde o fluxo prossegue após um nó de decisão.
• As condições devem incluir todas as possibilidades. Caso contrário, o fluxo de controle pode ficar
travado. Em caso de dúvida, insira uma saída com a condição else.
• Fork e join devem estar bem equilibrados. O número de fluxos que deixam uma bifurcação deve
corresponder ao número de fluxos que terminam na junção correspondente.

## ATP – Etapa 4

O que eu preciso desenvolver? Você deve elaborar um diagrama de classes, com base no cenário descrito na
semana 1. Você deve identificar as classes, atributos, métodos e relacionamentos entre as classes que
representam o cenário do Sistema Academia.
O que eu preciso entregar? Você deverá entregar o diagrama de classes produzido. Gere uma imagem dele e
insira na seção 4 – Diagrama de classes, do seu arquivo do Word. Garanta uma imagem nítida e legível.
Para ajudá-lo na especificação, produzimos um checklist de verificação.
Classes válidas e apropriadas
• Você adicionou todas as classes necessárias a partir dos requisitos (a maioria aparece como
substantivos)? Faça o cruzamento com as estórias de usuários apresentadas no cenário da etapa 1.
• Todos os nomes de classe estão escritos no singular e começam com uma letra maiúscula?
• Você nomeou cada classe para que seu significado possa ser entendido com precisão?
• Você já considerou casos em que há dois ou mais nomes para a mesma coisa e criou apenas uma
única classe?
• Você incluiu apenas classes para as quais os dados realmente precisam ser armazenados ou
manipulados?
Associações válidas e apropriadas
• Você adicionou todas as associações necessárias a partir dos requisitos (estórias de usuários)? Risque
frases nos requisitos quando as tiver utilizado para identificar relacionamento; por exemplo: Como
aluno, quero: ser capaz de consultar meus treinos diários (ou seja, o aluno consulta treino, havendo
uma relação entre a classe Aluno e a classe Treino).
• Todas as associações têm multiplicidade nos dois extremos? Exemplo: um aluno pode consultar um
ou mais treinos (conjunto de exercícios), mas um treino é referente a apenas um aluno.
• Você leu as associações nas duas direções e pensou na correção?
• Você tem alguma associação 1:1? Estes casos são extremamente raros e geralmente incorretos. Para
uma associação 1:1, sempre deve haver o mesmo número de instâncias de cada classe e elas devem
ser organizadas em pares.
• Os nomes dos métodos começam com letras minúsculas, são verbos de ação e significativos para uma
ação do sistema?
• Você tem uma classe representando os usuários finais do sistema? Se sim, está realmente
armazenando dados sobre os usuários? Caso contrário, exclua essas classes.
Atributos válidos e apropriados
• Você adicionou todos os atributos necessários?
• Os atributos representam dados simples que cada instância deve ter (string, int, double, date, boolean
etc.)?
• Você evitou escrever os atributos no plural na maioria dos casos?
Generalização e herança válidas e apropriadas
• Você usou o símbolo do triângulo aberto adequado, apontando para a superclasse?
• Tudo em cada superclasse também se aplica a cada uma de suas subclasses?
• Você evitou situações em que existem várias subclasses que não seriam significativamente
diferentes, ou seja, que não possuem atributos/métodos diferentes entre elas?
• Você pesquisou situações em que existem classes semelhantes e criou uma superclasse para os
elementos comuns?
Avaliação geral
• Você tem alguma classe com um grande número de atributos (mais de 10) ou associações (mais de
5)? Se sim, considere dividir essas classes em uma superclasse e uma subclasse; verifique se isso é
possível.
• Você consegue ver alguma maneira de simplificar seu modelo?
Chegou o momento de entrega da versão final do seu trabalho. Para auxiliar na autocorreção,
visualize a rubrica a seguir, que será utilizada para avaliarmos o seu trabalho. Dessa maneira,
considere este momento para efetuar os últimos ajustes nos seus artefatos.
Você deverá entregar um documento do Word contendo:
• Capa (elemento obrigatório), constando: nome da instituição, curso, autor, título, cidade e ano. Aqui,
você encontra um modelo: <https://www.normaseregras.com/normas-abnt/capa/>
• Sumário.
• Seção 1 – Diagrama de casos de uso.
• Seção 2 – Especificação de caso de uso.
• Seção 3 – Diagrama de atividades.
• Seção 4 – Diagrama de classes.
O documento deve ser de autoria própria e realizado individualmente – nenhuma exceção se aplica.
Os artefatos não devem apresentar similaridades com outros, dentro ou fora da internet. Similaridade
entende-se como cópias, reproduções e modificações de outros artefatos, total ou parcialmente, que
não sejam de autoria própria. Também não se aceitam plágios de qualquer tipo – integral: aquele em
que se copia palavra por palavra, sem citar a fonte; parcial: quando o trabalho é formado por cópia de
códigos de autores diversos, sem mencionar suas obras; conceitual: utiliza a ideia do autor,
escrevendo de outra forma.
São parte do processo de avaliação a apropriada formatação e organização do documento; logo, é
importante que os artefatos estejam legíveis e de fácil compreensão. A nota poderá ser ajustada
retroativamente caso alguma irregularidade seja detectada até seu fechamento.
É reservado ao professor-tutor o direito de julgamento e avaliação do correto atendimento a todos os
critérios informados.
