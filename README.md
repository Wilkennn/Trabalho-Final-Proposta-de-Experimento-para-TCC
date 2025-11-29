# Trabalho-Final-Proposta-de-Experimento-para-TCC

# Plano de Experimento – Scoping e Planejamento

## 1. Identificação básica

### 1.1 Título do experimento

Detecção de Lacunas na Elicitação de Requisitos: Uma abordagem comparativa assistida por Inteligência Artificial Generativa.

### 1.2 ID / código

PRE-TCC-001

### 1.3 Versão do documento e histórico de revisão

* **Versão Atual:** v1.1 (Detalhamento Metodológico)
* **Histórico:**
  * **v1.0 (21/11/2025):** Criação inicial da proposta de Scoping.
  * **v1.1 (26/11/2025):** Inclusão da matriz GQM, definição detalhada de métricas, refinamento do contexto fiscal e análise de riscos.

### 1.4 Datas (criação, última atualização)

* **Data de criação:** 21/11/2025
* **Última atualização:** 26/11/2025

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

O experimento será conduzido em um ambiente acadêmico controlado, simulando o desenvolvimento de um módulo de Documentos Fiscais Eletrônicos (DF-e) integrado a um sistema de gestão (ERP). O cenário foi delimitado estrategicamente considerando o atual momento de transição tributária no Brasil, marcado pela implementação do Padrão Nacional de NFS-e, que visa unificar os layouts municipais.

A escolha do domínio de Nota Fiscal de Serviço Eletrônica (NFS-e) serve estritamente como um cenário de validação para a ferramenta de IA. Este contexto foi selecionado por oferecer um terreno ideal para mensurar resultados: a existência de um "gabarito" claro e incontestável. Enquanto a maioria dos sistemas possui requisitos subjetivos, o ambiente fiscal impõe regras binárias — ou o requisito atende à legislação e aos Manuais de Orientação (MOC), ou não atende. Essa característica permite verificar com exatidão matemática os acertos e erros da Inteligência Artificial, eliminando a ambiguidade na hora de avaliar a eficácia da ferramenta.

No que tange aos atores envolvidos, o pesquisador assumirá o papel de um Analista de Requisitos em formação, responsável por especificar fluxos básicos de faturamento ("Caminho Feliz"), deliberadamente suscetíveis ao desconhecimento das minúcias do novo padrão nacional. Em contrapartida, o Agente Inteligente atuará como um "Auditor Fiscal Digital", confrontando os requisitos humanos contra a base legal para identificar falhas de conformidade, ausência de tratamento de contingência (como a indisponibilidade da API da Receita) e erros de validação de esquema.

Para operacionalizar o experimento, será utilizado um arcabouço tecnológico baseado na linguagem Python 3.x para a orquestração e análise comparativa, consumindo o modelo OpenAI GPT-4o via API. Todo o processo seguirá uma abordagem de Engenharia de Requisitos Ágil, utilizando Histórias de Usuário  e Critérios de Aceite, refletindo a realidade das *Software Houses* modernas que necessitam de agilidade sem abrir mão da rigorosa conformidade legal exigida pela Lei da Liberdade Econômica.

### 2.3 Trabalhos e evidências prévias (internos e externos)

Esta proposta situa-se na interseção entre a prática empírica de desenvolvimento de software e o estado da arte da pesquisa em Inteligência Artificial Aplicada.

No contexto interno, observações realizadas durante a análise técnica da API nacional da SEFAZ evidenciaram um padrão crítico, alinhado ao que **Curtis, Krasner e Iscoe (1988)** descrevem como a "escassez de conhecimento de domínio". A validação manual tende a priorizar o "Caminho Feliz", negligenciando regras fiscais restritivas. Isso ocorre porque a tradução do *Manual de Orientação do Contribuinte (MOC)* para requisitos técnicos impõe uma barreira cognitiva significativa, onde a distância entre a linguagem jurídica e a implementação técnica gera lacunas de especificação.

No cenário externo, a literatura sobre *AI4RE (Artificial Intelligence for Requirements Engineering)* apresenta crescimento exponencial. Estudos recentes, como a revisão sistemática de **Zhao et al. (2023)**, demonstram a eficácia de Grandes Modelos de Linguagem (LLMs) na elicitação de requisitos. Contudo, conforme apontado por **Arora et al. (2023)**, a maioria das pesquisas concentra-se na capacidade generativa (criar artefatos) e menos na capacidade analítica de garantia de qualidade em domínios críticos.

Existe, portanto, uma lacuna científica quanto ao uso de LLMs para **Auditoria de Conformidade** em cenários regulados. Diferente da extração de requisitos gerais discutida por **Breaux (2009)**, este trabalho foca na precisão da IA moderna em validar a aderência normativa no cenário fiscal brasileiro, onde a tolerância a alucinações é nula.

### 2.4 Referencial teórico e empírico essencial

A fundamentação científica deste experimento conecta três áreas essenciais: a normalização da qualidade de software, a tecnologia de modelos de linguagem e a objetividade das regras fiscais.

No que tange à Engenharia de Requisitos, o estudo apoia-se nas definições da norma **ISO/IEC 29148**. O conceito central adotado aqui é o de **Completude**: em sistemas críticos, um requisito só é considerado completo se prevê não apenas o funcionamento básico, mas também todas as exceções e restrições. Esse olhar é complementado pela norma **ISO/IEC 25010**, que trata da qualidade do produto. Neste trabalho, entende-se que, para software fiscal, a **Conformidade Funcional** não é um atributo secundário, mas o núcleo da qualidade do sistema. Teoricamente, isso significa que deixar de especificar um tratamento de erro previsto no Manual da Receita não é apenas um esquecimento, é uma falha crítica de conformidade.

Para atuar sobre esse problema, a pesquisa explora os **Grandes Modelos de Linguagem (LLMs)** baseados na arquitetura *Transformer*. O diferencial teórico explorado não é o retreinamento da IA, mas sim sua capacidade de **Aprendizado em Contexto** (*In-Context Learning*). O experimento utiliza técnicas como a **Cadeia de Pensamento** (*Chain-of-Thought*), descrita por Wei et al. (2022), que induz o modelo a "raciocinar" passo a passo. Estudos empíricos indicam que essa abordagem melhora significativamente a capacidade da IA de validar regras lógicas e reduz as "alucinações" (respostas inventadas), tornando-a viável para tarefas de auditoria.

Por fim, a validação de todo esse processo exige um cenário de teste com regras indiscutíveis. É aqui que entra o conceito de **Oráculo de Teste**, oriundo da teoria de Teste de Software. O domínio de Documentos Fiscais Eletrônicos (DF-e) fornece exatamente isso: um "Oráculo Normativo". Diferentemente de áreas subjetivas, como a experiência do usuário, as regras de validação da SEFAZ funcionam como uma verdade fundamental (*Ground Truth*). Isso permite medir matematicamente a eficácia da IA, pois cada lacuna que ela apontar poderá ser verificada binariamente: ou a regra existe na legislação vigente, ou a IA cometeu um erro.


## 3. Objetivos e questões (Goal / Question / Metric)

### 3.1 Objetivo geral (Goal template)

Analisar o uso de Grandes Modelos de Linguagem (LLMs), especificamente a arquitetura GPT-4o, com o propósito de avaliar a eficácia técnica da ferramenta no apoio à auditoria de requisitos, com respeito à capacidade de detecção de lacunas de conformidade (compliance) e completude normativa, sob a perspectiva do Analista de Requisitos e da Engenharia de Software, no contexto da especificação de um módulo de emissão de Nota Fiscal de Serviço Eletrônica (NFS-e), caracterizado por regras de negócio rígidas e objetivas.

| **No Escopo (In Scope)** | **Fora do Escopo (Out of Scope)** |
| :--- | :--- |
| **Processo:** Validação e verificação de requisitos funcionais e não-funcionais de *compliance* fiscal (NFS-e). | **Processo:** Desenvolvimento de código-fonte, implementação de banco de dados, interfaces de usuário (telas) ou testes unitários. |
| **Ferramenta:** Utilização de LLMs (GPT-4o) via API e técnicas de Engenharia de Prompt (*Few-Shot*, *Chain-of-Thought*). | **Ferramenta:** Treinamento (*Fine-tuning*) de novos modelos de IA ou criação de arquiteturas de redes neurais do zero. |
| **Domínio:** Regras de emissão de Nota Fiscal de Serviço (NFS-e) e integração com o Padrão Nacional. | **Domínio:** Regras de NF-e (Mercadorias), CT-e (Transporte), SPED Contábil ou cálculos tributários complexos de ICMS. |
| **Artefato:** Histórias de Usuário (*User Stories*), Critérios de Aceite e Regras de Negócio textuais. | **Artefato:** Diagramas UML complexos, Prototipação de telas (*Wireframes*), Testes de Carga ou Documentação de Arquitetura. |

### 3.2 Objetivos específicos
Para alcançar o objetivo geral, o experimento ramifica-se nos seguintes objetivos especificos:

* **O1:** **Mapear e definir o padrão-ouro (*Ground Truth*)** de requisitos para emissão de NFS-e, baseando-se estritamente na legislação vigente e nos Manuais da ABRASF, para servir como gabarito de correção.
* **O2:** **Elaborar um conjunto de requisitos "falhos"**, simulando especificações incompletas típicas de analistas júnior (com omissões de contingência, segurança e validação), criando assim a base de teste controlada.
* **O3:** **Implementar e calibrar o agente de IA**, desenvolvendo estratégias de *prompt* que induzam o modelo a atuar como um auditor fiscal, maximizando a detecção de erros e minimizando respostas genéricas.
* **O4:** **Realizar a auditoria automatizada e comparar os resultados**, cruzando as sugestões da IA com o gabarito oficial para classificar cada apontamento como: acerto (lacuna real), erro (alucinação) ou irrelevante.

### 3.3 Questões de pesquisa / de negócio

| Questão de Pesquisa (Question) | Métricas Associadas (Metric) |
| :--- | :--- |
| **Q1.1:** Qual a volumetria de regras mandatórias extraídas dos manuais oficiais? | M1 (Total de Regras Mapeadas)<br>M2 (Densidade Regulatória) |
| **Q1.2:** Qual a complexidade ciclomática média das regras de negócio mapeadas? | M3 (Complexidade da Regra)<br>M4 (Nível de Dependência) |
| **Q1.3:** Quais categorias de requisitos (Segurança, Fiscal, Dados) são mais prevalentes? | M5 (Distribuição por Categoria)<br>M1 (Total de Regras Mapeadas) |
| **Q2.1:** Qual a taxa de omissão intencional inserida no artefato de controle? | M6 (Taxa de Defeito Injetado)<br>M7 (Severidade da Omissão) |
| **Q2.2:** O artefato reflete a realidade de uma especificação júnior típica? | M8 (Índice de Similaridade Júnior)<br>M9 (Legibilidade do Requisito) |
| **Q2.3:** As falhas inseridas cobrem todas as categorias críticas mapeadas no O1? | M10 (Cobertura de Falhas por Categoria)<br>M5 (Distribuição por Categoria) |
| **Q3.1:** Qual técnica de prompt gera respostas mais estruturadas (JSON vs Texto)? | M11 (Taxa de Conformidade de Saída)<br>M12 (Tempo de Inferência) |
| **Q3.2:** A IA consegue manter o contexto das regras fiscais em conversas longas? | M13 (Janela de Contexto Efetiva)<br>M14 (Estabilidade da Resposta) |
| **Q3.3:** O custo computacional (tokens) viabiliza o uso da ferramenta em escala? | M15 (Custo por Requisito Analisado)<br>M16 (Consumo de Tokens) |
| **Q4.1:** Qual a eficácia da IA em encontrar as lacunas injetadas (Recall)? | M17 (Recall / Revocação)<br>M18 (Falsos Negativos) |
| **Q4.2:** Qual a confiabilidade das sugestões da IA (evitando alucinações)? | M19 (Precision / Precisão)<br>M20 (Taxa de Alucinação) |
| **Q4.3:** Qual o ganho de eficiência comparado a uma revisão manual estimada? | M21 (Tempo Economizado Estimado)<br>M22 (F-Measure) |

### 3.4 Métricas associadas (GQM)

Abaixo, detalham-se todas as métricas citadas no GQM, com suas descrições operacionais e unidades de medida.

| ID | Nome da Métrica | Descrição Operacional | Unidade |
| :--- | :--- | :--- | :--- |
| **M1** | Total de Regras Mapeadas | Contagem absoluta de regras extraídas do Manual (MOC) para o gabarito. | Inteiro (Qtd) |
| **M2** | Densidade Regulatória | Razão entre número de regras e número de campos do layout da nota. | Regras/Campo |
| **M3** | Complexidade da Regra | Classificação da regra: 1 (Simples/Formato), 2 (Lógica), 3 (Dependência Externa). | Escala Ordinal (1-3) |
| **M4** | Nível de Dependência | Quantidade de outras regras que precisam ser validadas antes da atual. | Inteiro (Qtd) |
| **M5** | Distribuição por Categoria | Percentual de regras pertencentes a cada grupo (Fiscal, TI, Segurança). | Porcentagem (%) |
| **M6** | Taxa de Defeito Injetado | Porcentagem de regras do gabarito que foram removidas propositalmente no artefato falho. | Porcentagem (%) |
| **M7** | Severidade da Omissão | Classificação do impacto da falta do requisito: Baixo, Médio, Crítico (Impede emissão). | Escala Ordinal |
| **M8** | Índice de Similaridade Júnior | Avaliação subjetiva (Expert) de quão realista é o erro inserido. | Escala Likert (1-5) |
| **M9** | Legibilidade do Requisito | Índice Flesch-Kincaid ou contagem de palavras do requisito escrito. | Índice/Inteiro |
| **M10** | Cobertura de Falhas | Porcentagem de categorias do MOC que possuem pelo menos uma falha inserida. | Porcentagem (%) |
| **M11** | Taxa de Conformidade de Saída | Porcentagem de respostas da IA que respeitam o formato solicitado (ex: JSON válido). | Porcentagem (%) |
| **M12** | Tempo de Inferência | Tempo decorrido entre o envio do prompt e o retorno completo da IA. | Segundos (s) |
| **M13** | Janela de Contexto Efetiva | Quantidade máxima de tokens que a IA processou sem perder a referência das regras. | Tokens |
| **M14** | Estabilidade da Resposta | Variação da resposta da IA para o mesmo prompt executado 3 vezes (Temperatura 0). | Booleano (Igual/Diferente) |
| **M15** | Custo por Requisito | Custo financeiro da API dividido pelo número de requisitos analisados. | USD ($) |
| **M16** | Consumo de Tokens | Total de tokens (input + output) gastos na sessão. | Inteiro (Tokens) |
| **M17** | Recall (Revocação) | Fórmula: `Lacunas Reais Encontradas / Total de Lacunas Injetadas`. | Decimal (0.0 - 1.0) |
| **M18** | Falsos Negativos | Quantidade de lacunas injetadas que a IA **não** conseguiu encontrar. | Inteiro (Qtd) |
| **M19** | Precision (Precisão) | Fórmula: `Sugestões Corretas / Total de Sugestões Dadas pela IA`. | Decimal (0.0 - 1.0) |
| **M20** | Taxa de Alucinação | Quantidade de sugestões da IA que não existem no Gabarito Oficial (Falsos Positivos). | Inteiro (Qtd) |
| **M21** | Tempo Economizado | Diferença entre tempo da IA e tempo médio humano para revisão (estimado). | Horas/Minutos |
| **M22** | F-Measure | Média harmônica entre Precision e Recall. | Decimal (0.0 - 1.0) |

## 4. Escopo e contexto do experimento

### 4.1 Escopo funcional / de processo (incluído e excluído)

O experimento concentra seus esforços exclusivamente na fase de **Elicitação e Análise de Requisitos**. Na prática, o trabalho consiste em especificar e revisar as regras para a emissão de Nota Fiscal de Serviço (NFS-e), utilizando artefatos de texto como Histórias de Usuário e Critérios de Aceite. A grande intervenção aqui é o uso do modelo GPT-4o (via API) para atuar como um "revisor inteligente", aplicando técnicas de Engenharia de Prompt para validar se essas regras estão em conformidade com a lei.

Por outro lado, é importante esclarecer que o estudo não avança para a construção do software em si. Atividades como escrever código-fonte, criar banco de dados ou desenhar telas estão fora do escopo, assim como não faremos o treinamento (*fine-tuning*) de novos modelos de IA. O foco também é cirúrgico no domínio da NFS-e e do Padrão Nacional, deixando de lado outras complexidades tributárias, como ICMS ou contabilidade fiscal, para não perder o foco do experimento.

### 4.2 Contexto do estudo (tipo de organização, projeto, experiência)

O estudo acontece em um ambiente controlado, mas que simula um cenário bem comum no mercado atual: uma *Software House* de pequeno ou médio porte correndo para adaptar seu ERP às novas regras fiscais nacionais. O projeto simulado é a criação de um módulo "Emissor Fiscal", tratado como crítico porque qualquer erro ali pode gerar multas pesadas para os clientes.

A dinâmica do experimento funciona como um "duelo" de perfis. De um lado temos o **Pesquisador**, atuando como um Analista Júnior que entende de sistemas, mas não domina todas as leis fiscais. Do outro, temos o **Auditor Virtual (IA)**, configurado para agir como um Especialista Sênior que "leu" todos os manuais da Receita e vai apontar onde o humano errou.

### 4.3 Premissas

Para que esse plano funcione, partimos de algumas bases fundamentais. A principal delas é que a API da OpenAI se mantenha estável e que o modelo GPT-4o consiga processar o contexto das leis fiscais sem "esquecer" informações no meio do processo. Também assumimos que as regras da ABRASF e da Receita Federal não vão mudar drasticamente nas próximas semanas, garantindo que o nosso "gabarito" de correção permaneça válido durante todo o estudo.

### 4.4 Restrições

O projeto precisa respeitar alguns limites práticos. O primeiro é financeiro: como o uso da API é pago em dólar, temos um orçamento restrito que inviabiliza testes em massa. O segundo é o tempo: a coleta e análise de dados precisam caber no cronograma letivo, durando no máximo de quatro a seis semanas. E, claro, existe a restrição ética: para respeitar a LGPD, jamais usaremos dados reais de empresas ou cidadãos; tudo no experimento será feito com dados fictícios.

### 4.5 Limitações previstas

É importante ser transparente sobre o que pode distorcer os resultados. O ponto principal é que escolhemos um domínio "fácil" para a IA (o fiscal), onde as regras são preto-no-branco. Isso significa que o sucesso aqui pode não se repetir em áreas mais subjetivas, como redes sociais.

Além disso, a própria natureza da IA generativa pode variar as respostas ligeiramente, mesmo quando tentamos controlar tudo. Por fim, como é o próprio pesquisador quem cria os "erros propositais" para a IA achar, existe o risco inconsciente de criar apenas os tipos de erro que já sabemos que a ferramenta consegue resolver.

## 5. Stakeholders e impacto esperado

### 5.1 Stakeholders principais

A realização deste experimento interessa diretamente a três grupos distintos dentro do ecossistema de desenvolvimento de software:

* **Equipes de Engenharia (Devs e QAs):** Os profissionais que estão na "linha de frente", escrevendo código e testando regras, muitas vezes sem domínio profundo da legislação.
* **Gestores de Produto (Product Owners/PMs):** Os responsáveis por definir *o que* deve ser construído e que sofrem as consequências quando um requisito mal especificado gera retrabalho.
* **Líderes Técnicos e de Inovação (CTOs/Tech Leads):** Decisores estratégicos que precisam saber se investir em ferramentas de IA traz retorno real ou se é apenas um custo adicional sem ganho de produtividade.

### 5.2 Interesses e expectativas dos stakeholders

Cada grupo olha para este estudo com uma expectativa diferente. Para a **Engenharia**, a esperança é descobrir uma "rede de segurança": eles querem saber se a IA pode atuar como um par de olhos extra que avisa sobre erros de legislação antes que virem bugs, reduzindo a pressão cognitiva de ter que decorar manuais fiscais.

Para o **Produto**, o interesse é na mitigação de risco. Eles esperam evidências de que a ferramenta pode impedir que o software seja lançado em desconformidade com a lei, evitando multas para os clientes e danos à reputação. Já para a **Liderança**, a busca é por eficiência operacional. Eles querem ver números: o experimento deve provar se usar IA reduz o tempo total de levantamento de requisitos ou se o custo de revisar as sugestões da máquina torna o processo mais caro do que fazer manualmente.

### 5.3 Impactos potenciais no processo / produto

A introdução desse "Auditor Virtual" no fluxo de trabalho gera impactos imediatos. Positivamente, espera-se um aumento na **robustez inicial** da especificação; ou seja, os requisitos chegam para o desenvolvedor já prevendo cenários de erro (como "SEFAZ fora do ar"), o que melhora a qualidade do código final.

Por outro lado, existe um impacto na carga de trabalho de revisão. O processo não fica "automático"; ele muda de perfil. Em vez de gastar tempo escrevendo tudo do zero, o analista passará a gastar tempo *validando* se as sugestões da IA fazem sentido. Se a ferramenta alucinar muito, esse tempo de validação pode virar um gargalo, atrasando o cronograma em vez de acelerá-lo.

## 6. Riscos de alto nível, premissas e critérios de sucesso

### 6.1 Riscos de alto nível (negócio, técnicos, etc.)

Olhando para o cenário macro, identificamos três grandes riscos que podem comprometer o experimento:

* **Risco de "Alucinação Convincente" (Técnico):** O maior perigo é a IA inventar uma regra fiscal que *parece* muito real (ex: citar um artigo de lei inexistente) e o pesquisador, por não ser um advogado tributarista, aceitar aquilo como verdade. Isso invalidaria os resultados.
* **Risco de Obsolescência do Conhecimento (Técnico):** Como o modelo GPT-4 possui uma data de corte de conhecimento (*knowledge cutoff*), ele pode desconhecer uma Lei ou Nota Técnica publicada recentemente, gerando orientações desatualizadas.
* **Risco de Custo Proibitivo (Negócio):** Se a complexidade dos *prompts* exigir o envio de manuais inteiros a cada requisição, o custo da API pode estourar o orçamento previsto rapidamente, forçando a interrupção da coleta de dados.

### 6.2 Critérios de sucesso globais (go / no-go)

Para considerarmos que o experimento "deu certo" — independentemente de a IA ser boa ou ruim —, precisamos atingir condições mínimas de qualidade científica:

1.  **Reprodutibilidade:** O experimento será um sucesso se os *prompts* criados gerarem resultados consistentes em pelo menos 80% das execuções. Se a ferramenta for instável demais, ela é inviável para uso corporativo (decisão *No-Go*).
2.  **Taxa de Precisão Mínima:** Estabelecemos um piso de 70% de precisão. Se a IA errar mais de 30% das sugestões (falsos positivos), concluiremos que o esforço de revisão humana não compensa o uso da ferramenta.
3.  **Ganho de Cobertura:** O experimento deve demonstrar que a IA encontrou, no mínimo, **uma lacuna crítica** de conformidade que passaria despercebida na revisão manual padrão.

### 6.3 Critérios de parada antecipada (pré-execução)

Existem situações que, se ocorrerem agora, nos obrigam a cancelar ou adiar o projeto antes mesmo de começar a rodar os scripts:

* **Indisponibilidade da API:** Se a OpenAI suspender o acesso ou mudar drasticamente a política de preços/limites, inviabilizando o orçamento pessoal.
* **Mudança Radical na Legislação:** Se a Receita Federal revogar o Padrão Nacional de NFS-e ou adiar a obrigatoriedade por tempo indeterminado nas próximas semanas, o "gabarito" do estudo perde a validade e o objeto de pesquisa deixa de ser relevante.
* **Falta de Acesso aos Manuais:** Se, por algum motivo, os portais da ABRASF ou do SPED saírem do ar, impedindo a consulta às regras oficiais para montar a base de comparação.

## 7. Modelo conceitual e hipóteses

### 7.1 Modelo conceitual do experimento
O modelo baseia-se na premissa de que a "camada fina de conhecimento" (*thin spread of domain knowledge*) é a principal causa de falhas na especificação manual feita por analistas não-especialistas.

Acredita-se que a introdução do Agente de IA (GPT-4o), contextualizado com os manuais fiscais (MOC), atuará como uma **variável independente** que impactará positivamente a **Detecção de Lacunas (Recall)**. O modelo sugere que a capacidade de varredura massiva da IA superará a atenção humana limitada, identificando requisitos de exceção que passariam despercebidos. Por outro lado, o modelo reconhece um *trade-off*: espera-se que a IA gere um número maior de falsos positivos (menor **Precisão**) do que a revisão humana conservadora.

### 7.2 Hipóteses formais (H0, H1)
As hipóteses abaixo formalizam a comparação entre o método de Revisão Manual (Controle) e a Revisão Assistida por IA (Tratamento).

* **Hipótese 1 - Eficácia na Detecção (Recall):**
  * **H0₁ (Nula):** `Recall(IA) ≤ Recall(Manual)` — O uso da IA não aumenta a quantidade de lacunas críticas encontradas em relação à revisão manual.
  * **H1₁ (Alternativa):** `Recall(IA) > Recall(Manual)` — O uso da IA aumenta significativamente a identificação de lacunas críticas de conformidade.

* **Hipótese 2 - Confiabilidade/Alucinação (Precision):**
  * **H0₂ (Nula):** `Precision(IA) = Precision(Manual)` — A taxa de acerto das sugestões da IA é equivalente à do humano.
  * **H1₂ (Alternativa):** `Precision(IA) < Precision(Manual)` — A IA gera proporcionalmente mais sugestões inválidas (alucinações) do que o humano.

### 7.3 Nível de significância e considerações de poder
O experimento adotará um nível de significância padrão de **α = 0,05** (95% de confiança).
Considerando as restrições de um TCC (amostra limitada de requisitos), reconhece-se que o **Poder Estatístico (1 - β)** pode ser reduzido. Para mitigar isso, buscar-se-á um *Effect Size* (Tamanho de Efeito) grande, focando em lacunas binárias e óbvias (ex: "Falta contingência"), onde a diferença de performance entre o Humano Júnior e a IA Sênior tende a ser expressiva.

## 8. Variáveis, fatores, tratamentos e objetos de estudo

### 8.1 Objetos de estudo
O objeto a ser analisado é um conjunto controlado de **Especificações de Requisitos para Emissão de NFS-e**. Este conjunto (o "Artefato Defeituoso") conterá:
* 10 a 20 Histórias de Usuário (*User Stories*).
* Falhas injetadas deliberadamente (ex: omissão de validação de XSD, falta de tratamento de *timeout* da SEFAZ, ausência de retenção de ISS).

### 8.2 Sujeitos / participantes (visão geral)
Devido à natureza *in vitro* e automatizada do experimento, os "sujeitos" que executam a tarefa de revisão são:
1.  **Sujeito A (Humano/Controle):** O próprio pesquisador, simulando a revisão de um Analista Pleno sem acesso a ferramentas de IA.
2.  **Sujeito B (Agente Virtual/Tratamento):** O modelo GPT-4o configurado via API.

### 8.3 Variáveis independentes (fatores) e seus níveis
O fator principal manipulado neste estudo é o **Método de Revisão**.

### 8.4 Tratamentos (condições experimentais)
A tabela abaixo descreve o desenho fatorial simples do experimento (1 Fator, 2 Níveis).

| Fator | Nível / Tratamento | Descrição da Condição |
| :--- | :--- | :--- |
| **Método de Revisão** | **T1: Manual (Controle)** | Revisão realizada exclusivamente por humano, consultando manuais PDF, sem auxílio de IA. Representa o *baseline*. |
| | **T2: Assistido por IA** | Revisão realizada pelo agente GPT-4o com *Prompt* de Auditoria Fiscal (CoT). |

### 8.5 Variáveis dependentes (respostas)
A tabela a seguir detalha todas as variáveis monitoradas, seus tipos e como serão coletadas.

| Tipo de Variável | Nome | Descrição | Escala / Unidade |
| :--- | :--- | :--- | :--- |
| **Independente** | Método de Revisão | A técnica aplicada para encontrar lacunas. | Nominal (Manual / IA) |
| **Dependente** | **Recall (Revocação)** | Capacidade de encontrar o erro. Fórmula: `Lacunas Encontradas / Total de Lacunas Injetadas`. | Razão (0.00 a 1.00) |
| **Dependente** | **Precision (Precisão)** | Qualidade da sugestão. Fórmula: `Sugestões Válidas / Total de Sugestões`. | Razão (0.00 a 1.00) |
| **Controle** | Modelo de LLM | Versão exata do modelo utilizado (ex: `gpt-4o-2024-05-13`) para garantir consistência. | Nominal |
| **Controle** | Temperatura da IA | Parâmetro de aleatoriedade do modelo, fixado em 0.0 ou 0.1. | Numérica (0.0 - 1.0) |
| **Controle** | Domínio | O escopo das regras (apenas NFS-e Padrão Nacional). | Nominal |

### 8.6 Variáveis de controle / bloqueio
Fatores mantidos constantes para evitar ruído nos dados:
* **Temperatura:** Fixada próxima a zero para minimizar a criatividade e focar na análise determinística.
* **Prompt Base:** A estrutura do prompt será idêntica para todas as execuções do grupo de tratamento.
* **Complexidade dos Requisitos:** Todos os requisitos testados terão nível de complexidade similar (regras de negócio de validação).

### 8.7 Possíveis variáveis de confusão conhecidas
* **Qualidade do Prompt:** Um prompt mal escrito pode fazer a IA falhar não por falta de capacidade, mas por falta de instrução. Isso será monitorado na fase de calibração (O3).
* **Viés do Pesquisador:** Como o pesquisador criou os defeitos e também validará as respostas, existe risco de subjetividade na classificação de "Sugestão Válida".

## 9. Desenho experimental

### 9.1 Tipo de desenho
O estudo utilizará um **Desenho de Um Fator com Dois Níveis (One-Factor Two-Level Design)**, aplicando uma abordagem de **Medidas Repetidas (Paired Comparison)** sobre o objeto de estudo.

* *Justificativa:* O mesmo conjunto de requisitos (Artefato Defeituoso) será submetido aos dois tratamentos (Manual e IA). Isso elimina a variância que existiria se usássemos requisitos diferentes para cada grupo, permitindo uma comparação direta ("Maçãs com Maçãs").

### 9.2 Randomização e alocação
* **O que será randomizado:** A ordem de apresentação dos requisitos dentro do *prompt* (ou a ordem de execução dos scripts) será aleatorizada para evitar que a IA sofra de "viés de atenção" (onde o modelo tende a analisar melhor o início ou o fim do texto — *primacy/recency effect*).
* **Ferramenta:** Utilização da função `random.shuffle()` do Python para embaralhar a lista de User Stories antes do envio à API.

### 9.3 Balanceamento e contrabalanço
* **Balanceamento:** O número de observações será idêntico para ambos os grupos (ex: se houver 20 lacunas injetadas, ambos os métodos terão a chance de encontrar as mesmas 20).
* **Contrabalanço:** Não se aplica fortemente pois a IA não sofre de "aprendizado" entre sessões (a memória é resetada a cada chamada de API), e o humano fará a revisão manual *antes* de ver o resultado da IA para não ser influenciado pelas respostas dela.

### 9.4 Número de grupos e sessões
* **Grupos:** 2 Grupos de Dados (Resultados Manuais vs. Resultados IA).
* **Sessões:**
  * 1 Sessão de Revisão Manual (Baseline).
  * 1 Sessão de Execução Automatizada (IA).
  * *Justificativa:* Como o custo da API é um fator limitante e o modelo é determinístico (com Temp=0), múltiplas rodadas massivas não adicionariam valor estatístico significativo para este escopo de TCC.

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