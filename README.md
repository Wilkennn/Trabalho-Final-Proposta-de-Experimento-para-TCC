# Trabalho-Final-Proposta-de-Experimento-para-TCC

# Plano de Experimento – Scoping e Planejamento

## 1. Identificação básica

### 1.1 Título do experimento

Detecção de Lacunas na Elicitação de Requisitos: Uma abordagem comparativa assistida por Inteligência Artificial Generativa.

### 1.2 ID / código

PRE-TCC-001

### 1.3 Versão do documento e histórico de revisão

Versão Atual: v1.0 (Versão Inicial - Proposta de Scoping)

Histórico: Criação inicial do documento de planejamento.

### 1.4 Datas (criação, última atualização)

Data de criação: 21/11/2025

Última atualização: 21/11/2025

### 1.5 Autores (nome, área, contato)

Wilken Henrique Moreira
    - Instituição: PUC Minas
    - Curso: Engenharia de Software (4º Período)
    - Contato: wilkenhenriquemoreira@gmail.com

### 1.6 Responsável principal (PI / dono do experimento)

Wilken Henrique Moreira (Pesquisador Principal)

### 1.7 Projeto / produto / iniciativa relacionada

- Contexto Acadêmico: Trabalho de Conclusão de Curso (Pré-TCC) em Engenharia de Software - PUC Minas.
- Área de Conhecimento: Engenharia de Requisitos e Inteligência Artificial Aplicada.
- Natureza do Trabalho: Pesquisa Experimental e Prototipação de Ferramenta de Apoio à Decisão.

## 2. Contexto e problema

### 2.1 Descrição do problema / oportunidade

Como evidenciado por Wiegers e Beatty (2013), requisitos frequentemente permanecem não declarados devido à suposição de 'conhecimento comum' (tacit knowledge). Analistas podem falhar em explicitar fluxos de exceção e requisitos não-funcionais por assumirem que estes são óbvios ou por falta de questionamento direcionado durante a elicitação.

Desse modo, fatores humanos como a inexperiência, fadiga cognitiva ou falhas de atenção resultam em lacunas críticas nos documentos de especificação. Consequentemente, tais omissões só são identificadas tardiamente, nas etapas de desenvolvimento ou produção, gerando um aumento exponencial nos custos de correção, conforme alerta Boehm (1981).

### 2.2 Contexto organizacional e técnico

O experimento será conduzido em um **ambiente acadêmico controlado**, simulando o desenvolvimento de um módulo de **Documentos Fiscais Eletrônicos (DF-e)** para um sistema ERP.

* **Ambiente e Objeto de Estudo:**
  O estudo focará na especificação de requisitos para um módulo emissor de **Nota Fiscal de Serviço Eletrônica (NFS-e)** seguindo o padrão nacional (ou padrão ABRASF). Este domínio foi selecionado por possuir regras de negócio rígidas, definidas por legislação vigente e Manuais de Orientação do Contribuinte (MOC), o que fornece um "gabarito" objetivo para a validação das sugestões da IA.

* **Atores Envolvidos:**
  * **Pesquisador (Humano):** Atuará como Analista de Requisitos simulando a especificação de um fluxo básico de faturamento ("Caminho Feliz").
  * **Agente Inteligente (IA):** Atuará como o "Especialista Fiscal/Tributário", responsável por identificar lacunas de *Compliance* (Conformidade), tratamento de exceções (ex: SEFAZ indisponível) e requisitos de segurança (Certificados Digitais).

* **Stack Tecnológica:**
  * **Linguagem de Script:** Python 3.x (para orquestração das chamadas).
  * **Modelo de IA (LLM):** OpenAI GPT-4o (via API).
  * **Base de Conhecimento (Contexto):** Manuais de Integração da SEFAZ/Prefeituras e Lei da Liberdade Econômica.

* **Processo de Desenvolvimento:**
  O experimento seguirá uma abordagem de **Engenharia de Requisitos Ágil**, focada na escrita de Histórias de Usuário (*User Stories*) e Critérios de Aceite, prescindindo de documentações extensas em formato de casos de uso tradicionais, para alinhar-se às práticas modernas de *Software House*.

### 2.3 Trabalhos e evidências prévias (internos e externos)

Esta proposta situa-se na interseção entre a prática observada em projetos de desenvolvimento de software e o estado da arte da pesquisa em Inteligência Artificial. No contexto acadêmico e profissional do autor, especificamente durante a modelagem de sistemas para o terceiro setor e na análise da API nacional da SEFAZ, observou-se que a validação manual de requisitos tende a priorizar excessivamente as funcionalidades visíveis — o chamado "Caminho Feliz". Frequentemente, regras de negócio restritivas e fluxos de exceção são negligenciados, uma vez que a tradução do *Manual de Orientação do Contribuinte (MOC)* em requisitos de software claros impõe uma barreira técnica significativa para analistas em formação.

Externamente, a literatura sobre *AI4RE (Artificial Intelligence for Requirements Engineering)* tem apresentado crescimento exponencial. Embora estudos recentes demonstrem a eficácia de Grandes Modelos de Linguagem (LLMs) na extração criativa de histórias de usuário, nota-se uma escassez de trabalhos focados na capacidade destes modelos atuarem como validadores de conformidade (*Compliance Checking*) em domínios altamente regulamentados. A maioria das pesquisas atuais concentra-se na geração de artefatos, deixando uma lacuna científica quanto à precisão da IA na verificação de aderência normativa no cenário fiscal brasileiro, onde a tolerância a erros é nula.

### 2.4 Referencial teórico e empírico essencial

A fundamentação teórica que sustenta o desenho deste experimento estrutura-se sobre três pilares essenciais. Primeiramente, adota-se a perspectiva da Qualidade de Requisitos baseada nas normas **ISO/IEC 29148** e **ISO 25010**, focando nos atributos de Completude e Consistência. Neste estudo, assume-se que, no domínio fiscal, a completude transcende a funcionalidade básica, tornando-se um imperativo legal; a omissão de cenários de erro, como falhas de comunicação com a SEFAZ, é tratada como uma violação direta do critério de Robustez.

O segundo pilar refere-se à aplicação de **Grandes Modelos de Linguagem (LLMs)** baseados na arquitetura *Transformer*. O experimento explora capacidades avançadas desses modelos, como o *Few-Shot Learning* e o *Chain-of-Thought (CoT)*, utilizando técnicas de *Role Playing* para contextualizar a IA como um auditor especialista, visando mitigar alucinações e aumentar a precisão das inferências. Por fim, a base empírica para a validação dos resultados reside no domínio dos **Documentos Fiscais Eletrônicos (DF-e)**. Diferentemente de áreas onde requisitos podem ser subjetivos, as regras contidas nos Manuais de Orientação do Contribuinte (MOC) e na legislação vigente funcionam como um "Oráculo" objetivo. Isso permite estabelecer um padrão-ouro binário para mensurar a eficácia da IA em identificar lacunas obrigatórias versus as omissões cometidas na elicitação humana.

## 3. Objetivos e questões (Goal / Question / Metric)

### 3.1 Objetivo geral (Goal template)
Preencha o objetivo geral usando um template claro (por exemplo, GQM), deixando explícito o que será analisado, com qual propósito, sob qual perspectiva e em qual contexto.

### 3.2 Objetivos específicos
Decomponha o objetivo geral em metas mais focadas (O1, O2, etc.), que descrevam resultados concretos de aprendizado ou decisão que o experimento deve gerar.

### 3.3 Questões de pesquisa / de negócio
Formule perguntas claras que o experimento deverá responder (Q1, Q2, etc.), em linguagem que faça sentido para os stakeholders técnicos e de negócio.

### 3.4 Métricas associadas (GQM)
Associe a cada questão as métricas que serão usadas para respondê-la, com nome, definição, unidade e fonte dos dados, garantindo alinhamento entre G, Q e M.

## 4. Escopo e contexto do experimento

### 4.1 Escopo funcional / de processo (incluído e excluído)
Explique claramente o que será coberto (atividades, artefatos, equipes, módulos) e o que ficará fora do experimento, para evitar interpretações divergentes.

### 4.2 Contexto do estudo (tipo de organização, projeto, experiência)
Caracterize o contexto em que o estudo ocorrerá: tipo e tamanho de organização, tipo de projeto, criticidade e perfil de experiência dos participantes.

### 4.3 Premissas
Liste as suposições consideradas verdadeiras para o plano funcionar (por exemplo, disponibilidade de ambiente, estabilidade do sistema), mesmo que não possam ser garantidas.

### 4.4 Restrições
Registre limitações práticas como tempo, orçamento, ferramentas, acessos ou regras organizacionais que impõem limites ao desenho.

### 4.5 Limitações previstas
Explique fatores que podem prejudicar a generalização dos resultados (validez externa), como contexto muito específico ou amostra pouco representativa.

## 5. Stakeholders e impacto esperado

### 5.1 Stakeholders principais
Liste os grupos ou papéis que têm interesse ou serão impactados pelo experimento (por exemplo, devs, QA, produto, gestores, clientes internos).

### 5.2 Interesses e expectativas dos stakeholders
Descreva o que cada grupo espera obter do experimento (insights, evidências, validação de decisão, mitigação de risco, etc.).

### 5.3 Impactos potenciais no processo / produto
Antecipe como a execução do experimento pode afetar prazos, qualidade, carga de trabalho ou o próprio produto durante e após o estudo.

## 6. Riscos de alto nível, premissas e critérios de sucesso

### 6.1 Riscos de alto nível (negócio, técnicos, etc.)
Identifique os principais riscos para negócio e tecnologia (atrasos, falhas de ambiente, indisponibilidade de dados, etc.) em nível macro.

### 6.2 Critérios de sucesso globais (go / no-go)
Defina as condições sob as quais o experimento será considerado útil e viável, inclusive critérios que sustentem uma decisão de seguir ou não com mudanças.

### 6.3 Critérios de parada antecipada (pré-execução)
Descreva situações em que o experimento deve ser adiado ou cancelado antes de começar (falta de recursos críticos, reprovação ética, mudanças de contexto).

## 7. Modelo conceitual e hipóteses

### 7.1 Modelo conceitual do experimento
Explique, em texto ou esquema, como você acredita que os fatores influenciam as respostas (por exemplo, "técnica A reduz defeitos em relação a B").

### 7.2 Hipóteses formais (H0, H1)
Formule explicitamente as hipóteses nulas e alternativas para cada questão principal, incluindo a direção esperada do efeito quando fizer sentido.

### 7.3 Nível de significância e considerações de poder
Defina o nível de significância (por exemplo, α = 0,05) e comente o que se espera em termos de poder estatístico, relacionando-o ao tamanho de amostra planejado.

## 8. Variáveis, fatores, tratamentos e objetos de estudo

### 8.1 Objetos de estudo
Descreva o que será efetivamente manipulado ou analisado (módulos de código, requisitos, tarefas, casos de teste, issues, etc.).

### 8.2 Sujeitos / participantes (visão geral)
Caracterize em alto nível quem serão os participantes (desenvolvedores, testadores, estudantes, etc.), sem ainda entrar em detalhes de seleção.

### 8.3 Variáveis independentes (fatores) e seus níveis
Liste os fatores que serão manipulados (por exemplo, técnica, ferramenta, processo) e indique os níveis de cada um (A/B, X/Y, alto/baixo).

### 8.4 Tratamentos (condições experimental)
Descreva claramente cada condição de experimento (grupo controle, tratamento 1, tratamento 2, etc.) e o que distingue uma da outra.

### 8.5 Variáveis dependentes (respostas)
Informe as medidas de resultado que você observará (por exemplo, número de defeitos, esforço em horas, tempo de conclusão, satisfação).

### 8.6 Variáveis de controle / bloqueio
Liste fatores que você não está estudando diretamente, mas que serão mantidos constantes ou usados para formar blocos (por exemplo, experiência, tipo de tarefa).

### 8.7 Possíveis variáveis de confusão conhecidas
Identifique fatores que podem distorcer os resultados (como diferenças de contexto, motivação ou carga de trabalho) e que você pretende monitorar.

## 9. Desenho experimental

### 9.1 Tipo de desenho (completamente randomizado, blocos, fatorial, etc.)
Indique qual tipo de desenho será utilizado e justifique brevemente por que ele é adequado ao problema e às restrições.

### 9.2 Randomização e alocação
Explique o que será randomizado (sujeitos, tarefas, ordem de tratamentos) e como a randomização será feita na prática (ferramentas, procedimentos).

### 9.3 Balanceamento e contrabalanço
Descreva como você garantirá que os grupos fiquem comparáveis (balanceamento) e como lidará com efeitos de ordem ou aprendizagem (contrabalanço).

### 9.4 Número de grupos e sessões
Informe quantos grupos existirão e quantas sessões ou rodadas cada sujeito ou grupo irá executar, com uma breve justificativa.

## 10. População, sujeitos e amostragem

### 10.1 População-alvo
Descreva qual é a população real que você deseja representar com o experimento (por exemplo, "desenvolvedores Java de times de produto web").

### 10.2 Critérios de inclusão de sujeitos
Especifique os requisitos mínimos para um participante ser elegível (experiência, conhecimento, papel, disponibilidade, etc.).

### 10.3 Critérios de exclusão de sujeitos
Liste condições que impedem participação (conflitos de interesse, falta de skills essenciais, restrições legais ou éticas).

### 10.4 Tamanho da amostra planejado (por grupo)
Defina quantos participantes você pretende ter no total e em cada grupo, relacionando a decisão com poder, recursos e contexto.

### 10.5 Método de seleção / recrutamento
Explique como os participantes serão escolhidos (amostra de conveniência, sorteio, convite aberto, turma de disciplina, time específico).

### 10.6 Treinamento e preparação dos sujeitos
Descreva qual treinamento ou material preparatório será fornecido para nivelar entendimento e reduzir vieses por falta de conhecimento.

## 11. Instrumentação e protocolo operacional

### 11.1 Instrumentos de coleta (questionários, logs, planilhas, etc.)
Liste todos os instrumentos que serão usados para coletar dados (arquivos, formulários, scripts, ferramentas), com uma breve descrição do papel de cada um.

### 11.2 Materiais de suporte (instruções, guias)
Descreva as instruções escritas, guias rápidos, slides ou outros materiais que serão fornecidos a participantes e administradores do experimento.

### 11.3 Procedimento experimental (protocolo – visão passo a passo)
Escreva, em ordem, o que acontecerá na operação (do convite ao encerramento), de modo que alguém consiga executar o experimento seguindo esse roteiro.

### 11.4 Plano de piloto (se haverá piloto, escopo e critérios de ajuste)
Indique se um piloto será realizado, com que participantes e objetivos, e defina que tipo de ajuste do protocolo poderá ser feito com base nesse piloto.

## 12. Plano de análise de dados (pré-execução)

### 12.1 Estratégia geral de análise (como responderá às questões)
Explique, em alto nível, como os dados coletados serão usados para responder cada questão de pesquisa ou de negócio.

### 12.2 Métodos estatísticos planejados
Liste os principais testes ou técnicas estatísticas que pretende usar (por exemplo, t-teste, ANOVA, testes não paramétricos, regressão).

### 12.3 Tratamento de dados faltantes e outliers
Defina previamente as regras para lidar com dados ausentes e valores extremos, evitando decisões oportunistas após ver os resultados.

### 12.4 Plano de análise para dados qualitativos (se houver)
Descreva como você tratará dados qualitativos (entrevistas, comentários, observações), especificando a técnica de análise (codificação, categorias, etc.).

## 13. Avaliação de validade (ameaças e mitigação)

### 13.1 Validade de conclusão
Liste ameaças que podem comprometer a robustez das conclusões estatísticas (baixo poder, violação de suposições, erros de medida) e como pretende mitigá-las.

### 13.2 Validade interna
Identifique ameaças relacionadas a causas alternativas para os efeitos observados (history, maturation, selection, etc.) e explique suas estratégias de controle.

### 13.3 Validade de constructo
Reflita se as medidas escolhidas realmente representam os conceitos de interesse e descreva como você reduzirá ambiguidades de interpretação.

### 13.4 Validade externa
Discuta em que contextos os resultados podem ser generalizados e quais diferenças de cenário podem limitar essa generalização.

### 13.5 Resumo das principais ameaças e estratégias de mitigação
Faça uma síntese das ameaças mais críticas e das ações planejadas, de preferência em forma de lista ou tabela simples.

## 14. Ética, privacidade e conformidade

### 14.1 Questões éticas (uso de sujeitos, incentivos, etc.)
Descreva potenciais questões éticas (pressão para participar, uso de estudantes, incentivos, riscos de exposição) e como serão tratadas.

### 14.2 Consentimento informado
Explique como os participantes serão informados sobre objetivos, riscos, benefícios e como registrarão seu consentimento.

### 14.3 Privacidade e proteção de dados
Indique que dados pessoais serão coletados, como serão protegidos (anonimização, pseudoanonimização, controle de acesso) e por quanto tempo serão mantidos.

### 14.4 Aprovações necessárias (comitê de ética, jurídico, DPO, etc.)
Liste órgãos ou pessoas que precisam aprovar o experimento (comitê de ética, jurídico, DPO, gestores) e o status atual dessas aprovações.

## 15. Recursos, infraestrutura e orçamento

### 15.1 Recursos humanos e papéis
Identifique os membros da equipe do experimento e descreva brevemente o papel e responsabilidade de cada um.

### 15.2 Infraestrutura técnica necessária
Liste ambientes, servidores, ferramentas, repositórios e integrações que devem estar disponíveis para executar o experimento.

### 15.3 Materiais e insumos
Relacione materiais físicos ou digitais necessários (máquinas, licenças, formulários, dispositivos) que precisam estar prontos antes da operação.

### 15.4 Orçamento e custos estimados
Faça uma estimativa dos principais custos envolvidos (horas de pessoas, serviços, licenças, infraestrutura) e a fonte de financiamento.

## 16. Cronograma, marcos e riscos operacionais

### 16.1 Macrocronograma (até o início da execução)
Defina as principais datas e marcos (conclusão do plano, piloto, revisão, início da operação) com uma visão de tempo realista.

### 16.2 Dependências entre atividades
Indique quais atividades dependem de outras para começar (por exemplo, treinamento após aprovação ética), deixando essas dependências claras.

### 16.3 Riscos operacionais e plano de contingência
Liste riscos ligados a cronograma, disponibilidade de pessoas ou recursos, e descreva ações de contingência caso esses riscos se materializem.

## 17. Governança do experimento

### 17.1 Papéis e responsabilidades formais
Defina quem decide, quem executa, quem revisa e quem apenas deve ser informado, deixando claro o fluxo de responsabilidade.

### 17.2 Ritos de acompanhamento pré-execução
Descreva as reuniões, checkpoints e revisões previstos antes da execução, incluindo frequência e participantes.

### 17.3 Processo de controle de mudanças no plano
Explique como mudanças no desenho ou no escopo do experimento serão propostas, analisadas, aprovadas e registradas.

## 18. Plano de documentação e reprodutibilidade

### 18.1 Repositórios e convenções de nomeação
Indique onde o plano, instrumentos, scripts e dados (futuros) serão armazenados e quais convenções de nomes serão usadas.

### 18.2 Templates e artefatos padrão
Liste os modelos (questionários, formulários, checklists, scripts) que serão usados e onde podem ser encontrados.

### 18.3 Plano de empacotamento para replicação futura
Descreva o que será organizado desde já (documentos, scripts, instruções) para facilitar a replicação do experimento por outras equipes ou no futuro.

## 19. Plano de comunicação

### 19.1 Públicos e mensagens-chave pré-execução
Liste os grupos que precisam ser comunicados e quais mensagens principais devem receber (objetivos, escopo, datas, impactos esperados).

### 19.2 Canais e frequência de comunicação
Defina por quais canais (e-mail, reuniões, Slack/Teams, etc.) e com que frequência as comunicações serão feitas.

### 19.3 Pontos de comunicação obrigatórios
Especifique os eventos que exigem comunicação formal (aprovação do plano, mudanças relevantes, adiamentos, cancelamentos).

## 20. Critérios de prontidão para execução (Definition of Ready)

### 20.1 Checklist de prontidão (itens que devem estar completos)
Liste os itens que precisam estar finalizados e aprovados (plano, instrumentos, aprovação ética, recursos, comunicação) para autorizar o início da operação.

### 20.2 Aprovações finais para iniciar a operação
Indique quem precisa dar o "ok final" (nomes ou cargos) e como esse aceite será registrado antes da execução começar.