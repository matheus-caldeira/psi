# Orientação - Atividade Prática (ATP)

## Descrição

Você será desafiado, neste projeto, a aplicar os conhecimentos em design orientado a objetos que irá adquirir ao longo da disciplina, evoluindo e documentando, utilizando UML para criar diagramas técnicos.

Imagine a seguinte situação: ao projetar um edifício, os arquitetos criam esboços para visualizar e experimentar vários projetos. Esses esboços são produzidos rapidamente e uma maneira intuitiva de comunicar o design ao cliente, mas não são detalhados o suficiente para os construtores. Quando os arquitetos se comunicam com as pessoas que irão construir o edifício, eles fornecem projetos detalhados que contêm medidas exatas de vários componentes. Esses detalhes extras permitem que os construtores construam exatamente o que o arquiteto imagina. Para o software, os analistas usam diagramas técnicos, chamados diagramas UML, para expressar seus designs para os desenvolvedores. É isso que vamos aprender e colocar em prática ao logo deste projeto.

A UML é uma notação visual considerada uma linguagem de modelagem utilizada para visualizar, especificar, construir e documentar projetos de software. Ela foi criada para auxiliar os analistas de sistemas a focar nas vantagens provenientes do uso do paradigma orientado a objetos e, assim, elaborar a estrutura de sistemas complexos de software.

Em conjunto com o conteúdo disponibilizado nesta disciplina, propomos a você o desenvolvimento de uma Atividade Prática (ATP), que poderá ser realizada em equipe de até 4 pessoas. Trata-se de uma atividade na qual você desenvolverá artefatos utilizando UML, em quatro etapas. Com o conteúdo que estudou nas semanas 1 e 2, terá subsídios para desenvolver a etapa 1, e assim sucessivamente. Como uma etapa utiliza o que foi desenvolvido na anterior, evite pulá-las e/ou executá-las fora da ordem recomendada.

Você não precisará entregar os artefatos referentes às diferentes etapas enquanto estão em andamento – a divisão em etapas serve para que consiga melhor organizar suas atividades e evitar contratempos. Na semana 4, nós teremos um checkpoint. Nesse momento, disponibilizaremos um checklist para que consiga se autoavaliar e resolver possíveis problemas a tempo. É extremamente recomendável que gerencie o seu tempo para que possa criar os artefatos referentes a cada uma das etapas de acordo com as semanas propostas, evitando contratempos e mitigando as possíveis dúvidas por meio da dedicação requerida.

Após finalizar todas as etapas, durante as últimas semanas da disciplina, você fará a entrega do documento já finalizado, a qual englobará tudo que desenvolveu durante as etapas em um único arquivo do Word, escrito nas normas da ABNT.

Nesta ATP, você deverá criar diagramas UML para especificar o cenário apresentado a seguir. Cada artefato deverá sempre levar em consideração o que foi apresentado nesse cenário.

## SISTEMA ACADEMIA

### Cenário

Sua equipe foi contratada para desenvolver um sistema de monitoramento e controle das atividades dos alunos de uma academia. O cliente é uma academia de alto nível e de grande porte, com uma média de 2.000 alunos matriculados no ano, em suas diversas modalidades. Seu objetivo estratégico é a fidelização do aluno, que passará a ter suas atividades acompanhadas e realizadas no local, tais como:

- treino personalizado;
- avaliação física periódica;
- evolução física;
- relacionamento aluno x professor.

A necessidade do cliente é ter essas atividades gerenciadas pelo sistema.

Não há interesse do cliente em ter, neste momento, um novo módulo de controle financeiro, pois, para isso, ele já possui outro sistema. Contudo, será necessária a integração entre o sistema a ser desenvolvido e o sistema financeiro, uma vez que algumas das atividades dos alunos podem ser cobradas separadamente e o professor tem um percentual de comissão por resultados alcançados na evolução deles.

O sistema será dividido em dois módulos. O primeiro terá funcionalidades que estarão disponíveis por meio dos computadores localizados dentro da academia, conectados a uma central. Por essas funcionalidades, o aluno poderá obter sua programação para o treino diário, o qual será fornecido pelo professor periodicamente. O segundo conterá funcionalidades disponibilizadas aos alunos para consulta via web, como sua agenda de atividades, sua evolução e a possibilidade de comunicação direta com o seu professor.

É importante destacar que essas funcionalidades podem ser acessadas por celulares, além de atender aos navegadores mais comumente utilizados. É desejável que a aplicação também seja acessível, uma vez que a academia atende a alunos portadores de necessidades especiais.
Para que o sistema realmente atenda às necessidades do negócio, o cliente solicita que um de seus gerentes esteja alocado como analista de negócios do projeto, ajudando na descrição e modelagem do processo interno.

A equipe pode e deve sugerir funcionalidades não previstas pelo cliente, tendo atenção para desenvolver somente aquelas aprovadas pelo patrocinador. É importante também identificar atores que interagem com o sistema, além dos descritos a seguir.

### Estórias dos usuários

#### Como aluno, quero

- Ser capaz de consultar meus treinos diários, porque, assim, posso ter agilidade e independência na hora da execução.
- Agendar minhas avaliações físicas periódicas e aulas nas diversas modalidades a partir do site, para poder concentrar minhas atividades na academia.
- Consultar minha evolução física e minha agenda a partir do site, porque quero ter o controle dos resultados efetivos do treinamento.
- Ter um canal de comunicação com meu professor, pois gostaria de um acompanhamento mais direcionado das minhas atividades e do meu progresso físico.

#### Como professor, preciso

- Registrar o treinamento programado dos alunos periodicamente, porque gostaria de concentrar minha atenção no acompanhamento da execução da atividade de cada aluno.
- Alimentar os dados sobre a evolução física dos alunos e suas avaliações periódicas, porque, assim, as informações sobre a sua evolução estarão disponíveis para consulta.
- De relatórios sobre a evolução dos meus alunos, de forma individual e por grupos, para poder avaliar a efetividade do seu treinamento.

#### Como administrador da academia, necessito

- Que o sistema exporte as atividades extras realizadas pelo aluno e sua frequência na academia, porque, assim, posso controlar, pelo sistema financeiro, suas despesas na academia.
- Que o sistema exporte as avaliações e estatísticas de evolução do grupo de alunos por professor, pois esses dados serão utilizados para o cálculo dos percentuais de comissão.
- Conhecer o número de alunos matriculados em cada modalidade disponível, para fazer o controle das modalidades e turmas oferecidas.

#### Como médico, preciso

- Consultar registros anteriores de avaliações físicas e atualizar com informações das avaliações periódicas, para fazer o acompanhamento físico do aluno.
- Consultar minha agenda via web, porque, assim, posso ter o controle dos meus compromissos com os alunos.
- O desenvolvimento integral da ATP prevê apenas uma entrega no fim da disciplina (semana 7 ou 8).  

## Avaliação

- A realização das etapas intermediárias de construção da atividade é fundamental, porém não prevê entregas isoladas.  

- Embora as etapas não precisem ser entregues, você será acompanhado e supervisionado pelo professor-tutor no decorrer das semanas.  
- Atente-se ao CHECKPOINT DA ATP na semana 4. Nessa semana, você responderá a questões referentes à(s) etapa(s) já realizada(s), as quais fornecerão dados que comprovam o cumprimento dos prazos e o alcance de resultados parciais.
- Explore efetivamente os canais de comunicação: fóruns, Fale com o Prof-Tutor e sessões de webconferência. Sua participação ativa será considerada no momento de avaliação da atividade.
- Esta atividade deve ser autoral e inédita, não sendo aceitas cópias, sob pena de não atribuição de nota, portanto não se esqueça de colocar todas as fontes consultadas ou utilizadas para esta atividade.
- Ao salvar o arquivo para entrega, atente-se à extensão dele. O ambiente virtual aceita apenas as seguintes extensões de arquivo: .doc; .docx; .xls; .xlsx; .pdf; .jpeg; .png; .zip e .rar (no caso de arquivos compactados). Confira os tipos de arquivos aceitos em cada atividade.
- Lembramos que é de sua responsabilidade a integridade e execução do arquivo. Caso o arquivo entregue esteja corrompido ou impossibilitado de execução o mesmo não será aceito.
