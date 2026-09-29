# Fundamentos e Ambientes da Engenharia de Requisitos

## 1. Fundamentos e Contexto da Engenharia de Requisitos

- **O erro que mudou tudo (Sonda Mariner 1, 1962):** Um erro clássico na tradução de especificações matemáticas (um hífen/fórmula de transição omitido em um documento manuscrito copiado para o código) fez a nave desviar da rota logo após o lançamento, exigindo sua destruição intencional. **Aplicação:** Demonstra que falhas na especificação ou na comunicação de requisitos geram prejuízos catastróficos.
- **Manifesto Ágil (2001):** Conjunto de valores e princípios que prioriza indivíduos e interações, software em funcionamento, colaboração com o cliente e resposta rápida a mudanças, em vez de processos rígidos. **Aplicação:** Na Engenharia de Requisitos moderna, ajuda a negociar requisitos de forma iterativa em vez de engessar tudo no início.
- **Por que a Engenharia de Requisitos é essencial:**
  - **Base do projeto:** Evita construir a coisa certa do jeito errado ou (pior) a coisa errada.
  - **Melhoria da comunicação:** Alinha o que o cliente quer com o que o desenvolvedor programa.
  - **Redução de risco:** Identifica problemas antes que o código seja escrito.
  - **Qualidade de produto:** Garante que o software atenda às expectativas reais de uso.
- **Indústria do Software no Brasil e características:** Caracterizada por um mercado dinâmico, forte dependência de capital humano qualificado (desenvolvedores, analistas) e baixo custo físico de replicação de produtos, mas desafiada por marcos regulatórios complexos (como leis tributárias e LGPD).

---

## 2. Conceitos Básicos e Ambientes de Desenvolvimento

### Ambientes de desenvolvimento

1. **Desenvolvimento (Dev):** Onde o programador escreve e testa o código isoladamente.
2. **Homologação (Staging/Testes):** Ambiente espelhado na produção onde o cliente valida se o sistema atende ao que foi pedido.
3. **Treinamento:** Ambiente separado com dados fictícios para capacitar os usuários finais a mexerem no sistema sem estragar os dados reais (altera a base de dados de treino).
4. **Produção (Prod):** O ambiente real, seguro e oficial onde o cliente final utiliza o sistema funcionando.

- **O que é um requisito:** Condição ou capacidade necessária para que um sistema resolva um problema ou alcance um objetivo de negócio.
- **Stakeholders:** Todos os envolvidos ou afetados pelo sistema (clientes, usuários finais, gestores, equipe de TI, auditores).
- **Problemas comuns na Engenharia de Requisitos:** Estatísticas reais mostram que a maior parte dos fracassos em projetos vem de falhas humanas e de escopo (ex.: **48% por requisitos incompletos** e **41% por falhas de comunicação**).

---

## 3. Tipos de Requisitos

- **Requisitos Funcionais (RF):** O que o sistema faz (ex.: *“O sistema deve emitir nota fiscal”*, *“O usuário deve conseguir fazer login”*).
- **Requisitos Não Funcionais (RNF):** Como o sistema se comporta ou suas restrições de qualidade (desempenho, segurança, usabilidade). Eles se dividem em:
  - **Requisitos de Produto:** Comportamento em tempo de execução (ex.: tempo de resposta menor que 2 segundos).
  - **Requisitos Externos:** Restrições legais ou de interoperabilidade (ex.: atender à LGPD, integrar com sistema do governo).
  - **Requisitos Organizacionais / de Projeto (não do produto):** Referem-se ao processo de desenvolvimento (ex.: *“O sistema deve ser desenvolvido em PHP utilizando MySQL”*, prazo de entrega, ferramentas obrigatórias).
- **Requisitos de Domínio:** Derivados do próprio nicho de negócio (ex.: em um sistema médico, regras sobre sigilo de prontuários que vêm das normas da medicina, não apenas do cliente).

---

## 4. Técnicas de Elicitação e Levantamento

Elicitação é o processo de descobrir, minerar e entender as necessidades do cliente. As principais técnicas são:

- **Entrevistas:** Conversas estruturadas ou abertas com stakeholders.
  - **Etapas:** Planejamento (definir perguntas e quem entrevistar), condução (executar a conversa e ouvir ativamente), análise (processar as anotações) e validação (confirmar com o entrevistado se você entendeu certo).
  - **Vantagens:** Permite profundidade. **Desvantagens:** Consome muito tempo e depende da boa vontade/clareza do entrevistado.
- **Questionários:** Ótimos para coletar dados quantitativos de um público amplo e disperso rapidamente.
- **Observação / Etnografia:** O analista vai até o local de trabalho do usuário e observa como ele executa a tarefa na prática. **Aplicação:** Excelente para descobrir *“requisitos tácitos”* (coisas que o usuário faz por hábito e esquece de contar na entrevista).
- **Brainstorming e prototipagem:**
  - **Brainstorming estruturado:** Reunião para gerar ideias em equipe seguindo regras focadas em um tema específico.
  - **Prototipagem de baixa fidelidade:** Desenhos em papel (wireframes rápidos) para validar conceitos visuais antes de gastar tempo codificando.
- **Workshops de Requisitos:** Reuniões colaborativas intensivas com vários stakeholders reunidos para negociar e definir o escopo juntos (envolve preparação, facilitação dinâmica e registro de acordos).
- **Método 5W2H:** Ferramenta gerencial para detalhar um problema ou requisito respondendo: *What* (O quê), *Why* (Por quê), *Who* (Quem), *Where* (Onde), *When* (Quando), *How* (Como) e *How much* (Quanto custa).
- **Histórias de Usuário (User Stories):** Descrições curtas e simples de um requisito sob a perspectiva do usuário (*“Como [papel], eu quero [funcionalidade] para que [benefício]”*). Muito usadas em metodologias ágeis.

---

## 5. Documentação, Qualidade e Gerência (CMMI)

- **Formas de documentar:** Especificação de Requisitos de Software (SRS/ERS), modelos de Casos de Uso, matrizes de rastreabilidade e backlogs de produto.
- **Critérios de qualidade (V&V — Validação e Verificação):**
  1. **Correto:** Atende à necessidade real.
  2. **Preciso / Não ambíguo:** Sem duplo sentido ou achismos.
  3. **Completo:** Descreve tudo o que é necessário.
  4. **Consistente:** Sem contradições entre os requisitos.
  5. **Verificável / Testável:** Deve ser possível provar por meio de testes se o requisito foi atendido ou não.
- **Rastreabilidade e mudanças:** Capacidade de ligar um requisito à linha de código ou caso de teste correspondente. **Aplicação:** Se uma lei muda (ex.: alíquota de imposto), a rastreabilidade mostra exatamente quais partes do sistema precisam ser alteradas.
- **Gerência de Requisitos no CMMI-DEV:** Área de processo do CMMI focada em gerenciar os requisitos do produto e garantir a consistência entre esses requisitos, os planos do projeto e os artefatos gerados. Envolve:
  1. Entender os requisitos com a concordância do cliente.
  2. Obter compromisso da equipe.
  3. Gerenciar mudanças de escopo de forma controlada.
  4. Manter a rastreabilidade bidirecional.

---

## 6. Modelagem Conceitual e Especificação

- **Domínio do Problema vs. Domínio da Solução:** O *domínio do problema* é o mundo real do cliente, suas dores e regras de negócio. O *domínio da solução* é o software, banco de dados e arquitetura técnica criados para resolver o problema.
- **Gap Semântico:** É a distância (o abismo) entre a forma como o usuário enxerga o seu negócio no dia a dia e a forma complexa como o computador e o código representam esses dados. A modelagem conceitual serve para diminuir esse gap.
- **Modelagem de Sistemas (visões dinâmica e estrutural):**
  - **Modelagem Comportamental (Dinâmica):** Mostra como o sistema age ao longo do tempo. *Exemplos:* Casos de Uso (interação geral), Diagrama de Atividades (fluxo de passos/processos) e Diagrama de Sequência (ordem cronológica de mensagens entre objetos).
  - **Modelagem Estrutural:** Mostra a parte estática do sistema (as “peças”). *Exemplos:* Diagrama de Classes (estruturas de dados e relacionamentos), Diagrama de Objetos e Diagrama de Componentes (módulos de software).

---

> **Nota:** As referências– foram mantidas conforme o texto fornecido. Os dados bibliográficos dessas fontes não foram informados.
