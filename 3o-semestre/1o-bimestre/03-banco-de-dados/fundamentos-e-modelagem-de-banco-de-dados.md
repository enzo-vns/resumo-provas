# Banco de Dados — Aulas 1 a 4

## Aula 1: Fundamentos de Banco de Dados

### 1. O que é um Banco de Dados (BD)?

**Definição:** Uma solução organizada de dados relacionados que representa determinado aspecto do mundo real (o *universo de discurso*), construída para uma finalidade específica e destinada ao compartilhamento controlado por usuários e aplicações [1].

**Pilares do Banco de Dados:**

- **Organização:** Os dados não estão soltos; eles são estruturados segundo um modelo formal determinado [1].
- **Compartilhamento:** Diferentes usuários e aplicações podem acessar os dados simultaneamente e de forma controlada [1].
- **Universo de discurso (*miniworld*):** O banco representa um recorte relevante do mundo real (ex.: dados de uma clínica, não de todas as clínicas) [1].
- **Finalidade:** Os dados são armazenados para atender necessidades organizacionais específicas [1].

### 2. O que distingue um BD genuíno?

- **Autodescrição:** O sistema contém os dados e a descrição de sua própria estrutura (o catálogo de metadados), consultável pelo sistema e pelos usuários [1].
- **Abstração e isolamento:** Aplicações acessam os dados por meio de uma estrutura conceitual. O armazenamento físico interno pode mudar sem quebrar os programas existentes [1].
- **Múltiplas visões:** Diferentes usuários enxergam subconjuntos distintos do banco (ex.: a recepção vê a agenda de horários; o médico vê o histórico clínico protegido) [1].
- **Compartilhamento multiusuário:** O processamento de transações e o controle de acesso concorrente preservam a consistência diante de edições simultâneas [1].

### 3. Conceitos fundamentais

**Dado vs. informação:**

- **Dado:** Valor bruto, sem contexto (ex.: `37`) [2].
- **Informação:** Dado interpretado dentro de um contexto (ex.: “O paciente João tem 37 anos”) [2].

**Persistência vs. Banco de Dados:**

- **Persistência:** Significa salvar dados de forma durável, permitindo que sobrevivam ao encerramento do programa [2].
- **Atenção:** Salvar um arquivo `.txt` é persistência, mas, por si só, não oferece as características de um BD descritas aqui, como autodescrição e controle multiusuário [2].

### 4. Os cinco passos para o levantamento de requisitos

1. **Atores:** Quem interage com o sistema (ex.: paciente, recepcionista, médico) [2].
2. **Operações:** O que cada ator faz (ex.: cadastrar, consultar) [2].
3. **Objetos de interesse (entidades):** Dados cruciais (ex.: paciente, consulta, produto) [2].
4. **Regras de negócio:** Restrições do sistema (ex.: “CPF deve ser único”; “Uma consulta deve ter um médico”) [2].
5. **Perguntas de esclarecimento:** Dúvidas a discutir com o cliente para evitar ambiguidades [2].

---

## Aula 2: Arquitetura e Modelagem

### 1. Modelo de dados × esquema × instância

- **Modelo de dados (“regras do jogo”):** Conjunto geral de conceitos e regras utilizados para representar dados, estruturas e relações; é a “caixa de ferramentas” conceitual do SGBD [3].
- **Esquema (“planta baixa”):** Estrutura relativamente fixa de um BD (ex.: nomes das tabelas e colunas, tipos de dados e restrições) [3].
- **Instância (“moradores”):** Conjunto de dados armazenados em um determinado momento (ex.: registros inseridos por comandos `INSERT`) [3].

### 2. Arquitetura de três esquemas

O SGBD projeta visões personalizadas, fazendo cada usuário acreditar que o banco foi construído sob medida para ele [3]:

1. **Nível externo (visões/*views*):** Como cada usuário vê os dados (ex.: o médico vê o histórico clínico; a recepcionista vê o telefone) [3].
2. **Nível conceitual/lógico:** A estrutura completa das tabelas e dos relacionamentos, sem se preocupar com a forma de gravação no disco [3].
3. **Nível interno (físico):** Como os dados são realmente gravados em disco, em bytes e índices [3].

### 3. Independência de dados

- **Independência lógica de dados:** Capacidade de alterar o esquema conceitual (ex.: adicionar uma tabela ou coluna) sem quebrar os esquemas externos ou os sistemas [3].
- **Independência física de dados:** Capacidade de alterar o armazenamento físico ou a estrutura interna (ex.: criar índices) sem quebrar o esquema conceitual nem os programas. A infraestrutura física muda, mas a estrutura lógica permanece a mesma [3].

---

## Aula 3: Processo e Pipeline de Projeto

### 1. Por que não começar criando tabelas diretamente em SQL?

Começar diretamente pelo código pode gerar retrabalho, perda de dados e estruturas inadequadas quando uma regra de negócio é descoberta durante o desenvolvimento [4].

### 2. Pipeline de projeto de Banco de Dados

**Necessidade → Requisitos → Modelo Conceitual → Modelo Lógico → Modelo Físico** [4].

### 3. Diferença entre os três modelos de dados

- **Modelo conceitual — “O que existe no negócio?”** Independe de tecnologia e utiliza entidades e relacionamentos [4].
- **Modelo lógico — “Como organizar em tabelas?”** Define tabelas, colunas, chaves primárias (PK) e chaves estrangeiras (FK) [4].
- **Modelo físico — “Como implementar no SGBD?”** Produz scripts em SQL com tipos reais (`VARCHAR`, `BIGINT`, `NOT NULL` etc.) para o banco escolhido (ex.: PostgreSQL) [4].

---

## Aula 4: Modelagem Conceitual e Notação de Chen

### 1. Do mundo real para o sistema

- **Conceitual:** Primeiro nível de abstração, com foco nas regras de negócio, em que os requisitos do mundo real são traduzidos em um diagrama visual [5].
- **Objetivo:** Traduzir a “dor” do negócio em requisitos de dados, sem entrar em código, tabelas, chaves estrangeiras ou SGBD [5].
- **Dor (necessidade do negócio):** “A recepção perde muito tempo para achar o telefone dos pacientes quando há um cancelamento” [5].
- **Regra (requisito de dados):** “O sistema deve armazenar um ou mais telefones de contato para cada paciente cadastrado” [5].
- **Vocabulário:** A notação de Chen é uma linguagem visual para construir o Diagrama Entidade-Relacionamento (DER) [5].

### 2. Componentes do Diagrama Entidade-Relacionamento (DER)

**Entidades — retângulos (`□`):** Representam objetos ou conceitos com existência própria no sistema (ex.: paciente, médico, especialidade, consulta) [5].

- **Entidade forte:** Possui identificador próprio e existe por si só (ex.: paciente) [5].
- **Entidade fraca:** Sua existência depende de uma entidade forte titular (ex.: dependente) [5].

**Atributos — elipses (`○`):** Descrevem características das entidades [5].

- **Identificador:** É sublinhado e distingue cada ocorrência de forma única (ex.: <u>id_paciente</u>) [5].
- **Simples:** É atômico, indivisível (ex.: nome, rua, CEP) [5].
- **Composto:** Pode ser subdividido (ex.: endereço, dividido em rua, bairro e CEP) [5].
- **Multivalorado:** Pode ter mais de um valor simultaneamente; é representado por elipse dupla (ex.: telefones de contato) [5].
- **Derivado:** É calculado a partir de outro dado; é representado por elipse pontilhada (ex.: idade calculada a partir da data de nascimento) [5].

---

> **Nota:** As referências [1]–[5] foram mantidas conforme o material fornecido. Os dados bibliográficos dessas fontes não foram informados.
