# Sistema de Gestão de Estoque

Sistema web para gerenciamento e controle de estoque, desenvolvido com o objetivo de centralizar o cadastro de produtos, registrar movimentações e fornecer informações para apoiar o controle e a reposição de mercadorias.

O projeto será desenvolvido como um **MVP (Minimum Viable Product)**, contemplando as principais funcionalidades necessárias para o gerenciamento de estoque de pequenos e médios negócios.

---

## Equipe

* **João Felipe Cavalcante Coelho**
* **André de Melo Marques**

---

## 1. Sobre o Projeto

A gestão de estoque realizada por meio de processos manuais, como planilhas e registros físicos, pode ocasionar inconsistências de informações, perdas de vendas, excesso de mercadorias e dificuldades no acompanhamento das movimentações.

Este projeto propõe uma aplicação web centralizada para automatizar o controle de estoque, permitindo registrar entradas e saídas de produtos, acompanhar os níveis de estoque e identificar produtos que necessitam de reposição.

### Objetivos

* Centralizar as informações de estoque.
* Automatizar o controle de entradas e saídas.
* Reduzir erros decorrentes de processos manuais.
* Impedir operações de venda sem estoque disponível.
* Identificar produtos abaixo do estoque mínimo.
* Disponibilizar informações para apoiar a tomada de decisão.

---

## 2. Problema

Pequenos e médios negócios podem enfrentar dificuldades relacionadas ao controle de seus estoques, principalmente quando dependem de processos manuais.

Entre os principais problemas identificados estão:

* **Ruptura de estoque:** indisponibilidade de produtos no momento da venda.
* **Excesso de estoque:** aquisição de mercadorias sem base em informações atualizadas.
* **Divergência de informações:** diferenças entre o estoque físico e o estoque registrado.
* **Baixa rastreabilidade:** dificuldade para identificar quando e como ocorreram determinadas movimentações.
* **Tomada de decisão lenta:** ausência de informações consolidadas sobre produtos que precisam de reposição.

---

## 3. Solução Proposta

A solução consiste em uma aplicação web composta por um **front-end desenvolvido em React** e um **back-end desenvolvido em Java com Spring Boot**, integrados a um banco de dados relacional.

O sistema permitirá o gerenciamento do catálogo de produtos e o registro das movimentações de estoque.

A cada entrada ou saída registrada, o saldo do produto será atualizado automaticamente.

Além disso, o sistema contará com uma regra de validação que impedirá a realização de uma saída quando a quantidade solicitada for superior ao estoque disponível.

---

## 4. Funcionalidades do MVP

### Produtos

* Cadastro de produtos.
* Consulta de produtos.
* Atualização de produtos.
* Exclusão de produtos.
* Definição de estoque mínimo.
* Controle de SKU e categoria.

### Movimentações

* Registro de entradas de produtos.
* Registro de saídas de produtos.
* Atualização automática do estoque.
* Validação de disponibilidade.
* Registro do histórico de movimentações.

### Dashboard

* Visualização do estoque atual.
* Identificação de produtos abaixo do estoque mínimo.
* Indicadores gerais de estoque.
* Informações para apoio à reposição de produtos.

---

## 5. Requisitos Funcionais

| ID   | Requisito                                                                         |
| ---- | --------------------------------------------------------------------------------- |
| RF01 | O sistema deve permitir cadastrar produtos.                                       |
| RF02 | O sistema deve permitir consultar produtos cadastrados.                           |
| RF03 | O sistema deve permitir editar produtos.                                          |
| RF04 | O sistema deve permitir excluir produtos.                                         |
| RF05 | O sistema deve permitir registrar entradas de estoque.                            |
| RF06 | O sistema deve permitir registrar saídas de estoque.                              |
| RF07 | O sistema deve atualizar automaticamente o saldo após cada movimentação.          |
| RF08 | O sistema deve impedir saídas quando não houver quantidade suficiente em estoque. |
| RF09 | O sistema deve permitir definir uma quantidade mínima para cada produto.          |
| RF10 | O sistema deve identificar produtos abaixo da quantidade mínima.                  |
| RF11 | O sistema deve armazenar o histórico das movimentações realizadas.                |
| RF12 | O sistema deve disponibilizar informações de estoque por meio de um dashboard.    |

---

## 6. Requisitos Não Funcionais

| ID    | Requisito                                                                             |
| ----- | ------------------------------------------------------------------------------------- |
| RNF01 | A aplicação deve possuir interface responsiva para diferentes tamanhos de tela.       |
| RNF02 | O back-end deve disponibilizar uma API REST.                                          |
| RNF03 | O sistema deve utilizar um banco de dados relacional.                                 |
| RNF04 | A aplicação deve garantir a integridade das operações de estoque.                     |
| RNF05 | O código deve seguir boas práticas de organização e manutenção de software.           |
| RNF06 | A aplicação deve utilizar controle de versão por meio do Git.                         |
| RNF07 | O projeto deve possuir documentação das principais decisões e componentes da solução. |

---

## 7. Histórias de Usuário

### US01 — Cadastro de Produtos

**Como** estoquista,
**quero** cadastrar novos produtos,
**para que** os itens comercializados pela empresa possam ser controlados pelo sistema.

### US02 — Registro de Entrada

**Como** estoquista,
**quero** registrar a entrada de mercadorias,
**para que** o estoque seja atualizado corretamente.

### US03 — Registro de Saída

**Como** vendedor,
**quero** registrar a saída de mercadorias,
**para que** o saldo do estoque seja atualizado após uma venda.

### US04 — Validação de Estoque

**Como** vendedor,
**quero** que o sistema valide a disponibilidade do produto antes de registrar uma saída,
**para que** não sejam realizadas operações com estoque insuficiente.

### US05 — Monitoramento

**Como** gestor,
**quero** visualizar os produtos abaixo do estoque mínimo,
**para que** eu possa planejar a reposição das mercadorias.

### US06 — Histórico

**Como** gestor,
**quero** consultar o histórico das movimentações,
**para que** eu possa acompanhar as entradas e saídas realizadas no sistema.

---

## 8. Arquitetura da Aplicação

A aplicação será estruturada seguindo uma arquitetura dividida entre front-end, back-end e banco de dados.

```text
┌──────────────────────────┐
│          Usuário         │
└────────────┬─────────────┘
             │
             ▼
┌──────────────────────────┐
│      React Front-end     │
│                          │
│  • Interface             │
│  • Dashboard             │
│  • Formulários           │
│  • Navegação             │
└────────────┬─────────────┘
             │
             │ HTTP / REST
             ▼
┌──────────────────────────┐
│    Spring Boot API       │
│                          │
│  • Controllers           │
│  • Services              │
│  • Repositories          │
│  • Regras de negócio     │
└────────────┬─────────────┘
             │
             │ JPA / Hibernate
             ▼
┌──────────────────────────┐
│    Banco de Dados        │
│   PostgreSQL / MySQL     │
└──────────────────────────┘
```

---

## 9. Estrutura do Repositório

```text
meu-repositorio/
│
├── frontend/
│   ├── src/
│   ├── public/
│   ├── package.json
│   └── ...
│
├── backend/
│   ├── src/
│   ├── pom.xml
│   └── ...
│
├── docs/
│   ├── DER/
│   ├── wireframes/
│   ├── requisitos/
│   └── ...
│
├── .gitignore
└── README.md
```

### `frontend/`

Contém o código da aplicação React, incluindo componentes, páginas, rotas, serviços e demais recursos relacionados à interface.

### `backend/`

Contém a aplicação Java com Spring Boot, incluindo controllers, services, repositories, entidades e regras de negócio.

### `docs/`

Contém os documentos relacionados ao projeto, como:

* Diagrama Entidade-Relacionamento (DER).
* Wireframes.
* Protótipos.
* Documentação de requisitos.
* Documentação técnica.

---

## 10. Tecnologias

| Tecnologia         | Finalidade                         |
| ------------------ | ---------------------------------- |
| React              | Desenvolvimento do front-end       |
| Java               | Desenvolvimento do back-end        |
| Spring Boot        | Construção da API REST             |
| Spring Data JPA    | Persistência de dados              |
| Hibernate          | ORM                                |
| PostgreSQL / MySQL | Banco de dados                     |
| Figma              | Prototipação UI/UX                 |
| Git                | Controle de versão                 |
| GitHub             | Hospedagem e colaboração no código |

---

## 11. Modelo de Dados

O modelo de dados será definido durante a etapa de modelagem do projeto.

As principais entidades previstas para o MVP são:

### Produto

| Campo              | Descrição                        |
| ------------------ | -------------------------------- |
| `id`               | Identificador do produto         |
| `nome`             | Nome do produto                  |
| `sku`              | Código de identificação          |
| `categoria`        | Categoria do produto             |
| `preco`            | Preço do produto                 |
| `quantidade`       | Quantidade disponível em estoque |
| `quantidadeMinima` | Quantidade mínima recomendada    |

### Movimentação

| Campo        | Descrição                     |
| ------------ | ----------------------------- |
| `id`         | Identificador da movimentação |
| `produto`    | Produto movimentado           |
| `tipo`       | Entrada ou saída              |
| `quantidade` | Quantidade movimentada        |
| `data`       | Data da movimentação          |
| `observacao` | Informações adicionais        |

O diagrama definitivo será disponibilizado em:

```text
/docs/DER/
```

---

## 12. Cronograma

O desenvolvimento do MVP será dividido em quatro ciclos semanais.

| Semana | Etapa                 | Principais atividades                                | Entrega                     |
| :----: | --------------------- | ---------------------------------------------------- | --------------------------- |
|    1   | Planejamento e Design | Requisitos, DER, protótipo e configuração do projeto | Protótipo e modelo de dados |
|    2   | Back-end              | Banco de dados, APIs e regras de negócio             | Back-end funcional          |
|    3   | Front-end             | Interfaces, dashboard e integração                   | Interface funcional         |
|    4   | Testes e Deploy       | Integração, testes, correções e implantação          | MVP 1.0                     |

---

## 13. Backlog

### Semana 1 — Planejamento e Infraestrutura

| ID  | Tarefa                      | Descrição                                   | Tamanho |
| --- | --------------------------- | ------------------------------------------- | :-----: |
| 1.1 | Levantamento de requisitos  | Definição das regras de negócio             |    P    |
| 1.2 | Modelagem de dados          | Criação do DER e estrutura inicial do banco |    M    |
| 1.3 | Prototipação                | Desenvolvimento das telas no Figma          |    G    |
| 1.4 | Configuração do repositório | GitHub, branches e documentação             |    P    |
| 1.5 | Configuração do ambiente    | Inicialização do React e Spring Boot        |    P    |

### Semana 2 — Back-end

| ID  | Tarefa                | Descrição                                           | Tamanho |
| --- | --------------------- | --------------------------------------------------- | :-----: |
| 2.1 | Configuração do banco | Integração com JPA/Hibernate                        |    P    |
| 2.2 | API de produtos       | Implementação do CRUD                               |    M    |
| 2.3 | API de movimentações  | Implementação de entradas e saídas                  |    M    |
| 2.4 | Controle de estoque   | Implementação das regras de atualização e validação |    G    |
| 2.5 | Testes unitários      | Testes das principais regras de negócio             |    M    |

### Semana 3 — Front-end

| ID  | Tarefa          | Descrição                                    | Tamanho |
| --- | --------------- | -------------------------------------------- | :-----: |
| 3.1 | Roteamento      | Configuração da navegação da aplicação       |    P    |
| 3.2 | Catálogo        | Listagem e gerenciamento de produtos         |    M    |
| 3.3 | Movimentações   | Interfaces de entrada e saída                |    M    |
| 3.4 | Dashboard       | Indicadores e alertas                        |    G    |
| 3.5 | Componentização | Desenvolvimento de componentes reutilizáveis |    P    |

### Semana 4 — Integração e Deploy

| ID  | Tarefa              | Descrição                             | Tamanho |
| --- | ------------------- | ------------------------------------- | :-----: |
| 4.1 | Integração          | Comunicação entre React e API         |    G    |
| 4.2 | Tratamento de erros | Implementação das mensagens de erro   |    M    |
| 4.3 | Testes de fluxo     | Validação dos principais casos de uso |    M    |
| 4.4 | Correção de bugs    | Correção dos problemas identificados  |    P    |
| 4.5 | Deploy              | Implantação da aplicação              |    M    |

---

## 14. Estratégia de Branches

O projeto utilizará uma estratégia simples de branches para organizar o desenvolvimento.

```text
main
│
└── develop
    │
    ├── feature/produtos
    ├── feature/movimentacoes
    ├── feature/dashboard
    └── feature/autenticacao
```

### Branches principais

* `main` — versão estável do projeto.
* `develop` — integração das funcionalidades em desenvolvimento.
* `feature/*` — desenvolvimento de novas funcionalidades.
* `hotfix/*` — correções emergenciais da versão estável.

---

## 15. Convenção de Commits

Os commits devem seguir uma convenção para facilitar a identificação das alterações realizadas.

```text
feat: adiciona cadastro de produtos
feat: implementa registro de movimentações
fix: corrige validação de estoque insuficiente
refactor: reorganiza camada de serviços
test: adiciona testes para movimentações
docs: atualiza documentação do projeto
```

### Tipos utilizados

| Tipo       | Utilização                                 |
| ---------- | ------------------------------------------ |
| `feat`     | Nova funcionalidade                        |
| `fix`      | Correção de problema                       |
| `refactor` | Refatoração sem alteração de comportamento |
| `test`     | Inclusão ou alteração de testes            |
| `docs`     | Alterações na documentação                 |
| `chore`    | Tarefas de manutenção/configuração         |

---

## 16. Execução do Projeto

### Pré-requisitos

Antes de executar o projeto, é necessário possuir:

* Git
* Node.js
* Java JDK
* Maven
* PostgreSQL ou MySQL

### Clonar o repositório

```bash
git clone URL_DO_REPOSITORIO
cd meu-repositorio
```

### Executar o Front-end

```bash
cd frontend
npm install
npm run dev
```

### Executar o Back-end

Linux/macOS:

```bash
cd backend
./mvnw spring-boot:run
```

Windows:

```bash
cd backend
mvnw.cmd spring-boot:run
```

> As configurações de conexão com o banco de dados deverão ser definidas conforme o ambiente de desenvolvimento.

---

## 17. Status do Projeto

**Em desenvolvimento**

### MVP

* [ ] Levantamento de requisitos
* [ ] Modelagem do banco de dados
* [ ] Protótipo UI/UX
* [ ] Configuração do back-end
* [ ] API de produtos
* [ ] API de movimentações
* [ ] Regras de controle de estoque
* [ ] Interface de produtos
* [ ] Interface de movimentações
* [ ] Dashboard
* [ ] Integração front-end / back-end
* [ ] Testes
* [ ] Deploy

---

## 18. Documentação

A documentação complementar do projeto está localizada no diretório:

```text
/docs
```

Materiais previstos:

* Requisitos.
* Diagramas.
* DER.
* Wireframes.
* Protótipos.
* Documentação técnica.

---

## 19. Licença

Projeto desenvolvido para fins acadêmicos e de aprendizado em desenvolvimento de software.

---

**Sistema de Gestão de Estoque**
*React · Java · Spring Boot · JPA/Hibernate · PostgreSQL/MySQL*
