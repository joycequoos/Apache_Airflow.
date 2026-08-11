# Apache Airflow: a mais importante ferramenta de orquestração de dados

[← Voltar a Engenharia de Dados](https://github.com/joycequoos/Data_Enginer/blob/main/README.md)


O Airflow é uma plataforma para gerenciamento, programação e monitoramento de pipelines de dados. Ele permite criar, transformar e carregar dados por meio de processos simples ou complexos, utilizando um conjunto de tarefas independentes que facilita a automação e a escalabilidade — sendo, hoje, uma das principais ferramentas de Engenharia de Dados moderna.

Conteúdo relacionado: [Como surge a Engenharia de Dados?](https://github.com/joycequoos/Como-surge-engenharia-dados./blob/main/README.md)

---

## <img src="https://raw.githubusercontent.com/apache/airflow/main/airflow-core/docs/img/logos/airflow_64x64_emoji_transparent.png" width="28" valign="middle"> O que é o Apache Airflow

O Airflow é um projeto criado em 2015 e, como diversos outros projetos open source, acabou sendo doado e hoje é mantido pela **Apache Software Foundation**. É desenvolvido em **Python** e uma de suas principais características é a extensibilidade.

```mermaid
flowchart TD
    A[Airflow<br/>Orquestrador] -->|coordena o processamento em batch| B{Processamento ocorre em}
    B --> C[Sistema Operacional]
    B --> D[Banco de Dados]
    B --> E[Spark]
    B --> F[Elastic Search]
    B --> G[Etc.]

    A -.->|não processa dados| A
```

O objetivo do Airflow é **orquestrar pipelines de dados**. Para isso, desenvolve-se uma **DAG** (Directed Acyclic Graph) e, dentro dela, as tarefas (*tasks*) — incluindo a definição de qual a precedência entre elas.

```mermaid
flowchart LR
    A[Tarefa 1] -->|Precedência| B[Tarefa 2]
    A -->|Precedência| C[Tarefa 3]
    B -->|Paralelismo /<br/>Independência| D[Tarefa 4]
    C -->|Paralelismo /<br/>Independência| D
```

### Vantagens de usar uma pipeline de dados com Airflow

```mermaid
flowchart LR
    P((Pipeline)) --> A[Erros]
    P --> B[Log / Auditoria]
    P --> C[Monitoramento / Alertas]
    P --> D[Recuperação a partir<br/>de um Ponto]
    P --> E[Dados Históricos /<br/>Diferenciação]
    P --> F[Alta disponibilidade]
```

### Como o Airflow funciona

- **DAG** — é um pipeline do Airflow: define *o que* esse pipeline vai fazer.
- **Operators / Task** — definem *como* cada etapa do pipeline é executada.

---

## Trilha de Estudos (do básico ao avançado)

<!--
  Comentário: dividi as 37 anotações originais em 5 blocos temáticos,
  seguindo a progressão natural de quem está aprendendo Airflow:
  1) preparar o ambiente, 2) construir DAGs, 3) controlar o fluxo,
  4) trocar dados entre tasks, 5) configurações e extensibilidade.
-->

### 1. Preparação do Ambiente

| # | Tópico | Link |
|---|--------|------|
| 01 | Preparação do ambiente | [Ver Conteúdo](https://github.com/JosiTubaroski/Airflow_Preparar_Ambiente/blob/main/README.md) |
| 02 | Subir Docker e Airflow (caso a máquina tenha desligado) | [Ver Conteúdo](https://github.com/JosiTubaroski/Subir_Docker/blob/main/README.md) |
| 03 | Conhecendo o Airflow | [Ver Conteúdo](https://github.com/JosiTubaroski/Conhecendo_Airflow) |

### 2. Construindo e Estruturando DAGs

| # | Tópico | Link |
|---|--------|------|
| 04 | Criar a primeira DAG na prática | [Ver Conteúdo/Código](https://github.com/JosiTubaroski/Criar_DAG_Airflow) |
| 05 | Segunda DAG (paralelismo) / Terceira DAG (precedência) | [Ver Conteúdo/Código](https://github.com/JosiTubaroski/Segunda_Dag_Paralelismo) |
| 06 | DAG utilizando `with` e `set_upstream` | [Ver Conteúdo/Código](https://github.com/JosiTubaroski/Quarta_Dag/tree/main) |
| 10 | Estruturando DAGs um pouco mais complexas | [Ver Conteúdo/Código](https://github.com/JosiTubaroski/Criando_Dags_Complexas/tree/main) |
| 11 | Agrupamento de tasks (Task Group) | [Ver Conteúdo/Código](https://github.com/JosiTubaroski/Agrupando_com_task_group/blob/main/README.md) |
| 12 | DAG que executa outra DAG | [Ver Conteúdo/Código](https://github.com/JosiTubaroski/Dag_Executa_Dag) |
| 13 | Principais parâmetros de uma DAG | [Ver Conteúdo/Código](https://github.com/JosiTubaroski/Parametros_Dag/blob/main/README.md) |
| 14 | Criando DAG com dicionários | [Ver Conteúdo/Código](https://github.com/JosiTubaroski/Criando-Dag-com-Dicionarios/blob/main/README.md) |
| 16 | Criando DAGs com task Dummy | [Ver Conteúdo/Código](https://github.com/joycequoos/Dags_Exercicios/blob/main/README.md) |

### 3. Operadores, Controle de Fluxo e Gatilhos

| # | Tópico | Link |
|---|--------|------|
| 07 | Principais Operadores | [Ver anotações](https://github.com/JosiTubaroski/Principais_Operadores/blob/main/README.md) |
| 08 | Regras de Gatilho (Trigger Rules) | [Ver anotações](https://github.com/JosiTubaroski/Regras_Gatilho/blob/main/README.md) |
| 09 | Exemplos de Trigger | [Ver anotações](https://github.com/JosiTubaroski/Exemplo_Trigger/blob/main/README.md) |
| 21 | Branchs: decisões em DAGs | [PDF](https://github.com/JosiTubaroski/Apache_Airflow_Princial/blob/main/img/5.1.Branchs.pdf) |
| 22 | Criando uma DAG com Branch | [Ver código](https://github.com/joycequoos/DAG_com_Branch/blob/main/README.md) |
| 23 | Mais sobre o PythonOperator | [PDF](https://github.com/JosiTubaroski/Apache_Airflow_Princial/blob/main/img/6.1.Mais%20Python%20Operator.pdf) |
| 24 | Limpeza de dados com PythonOperator | [Ver código](https://github.com/joycequoos/pythonoperator/blob/main/README.md) |

### 4. Comunicação e Dados entre Tasks

| # | Tópico | Link |
|---|--------|------|
| 15 | Fundamentos de XCom / utilizando XCom | [Ver anotações](https://github.com/JosiTubaroski/Xcom/blob/main/README.md) |
| 25 | Conhecendo Datasets | [PDF](https://github.com/JosiTubaroski/Apache_Airflow_Princial/blob/main/img/7.1.Datasets.pdf) |
| 26 | DAG consumindo Datasets (Produtor) | [Ver código](https://github.com/joycequoos/producer/blob/main/README.md) |
| 27 | DAG consumindo Datasets (Consumidor) | [Ver código](https://github.com/joycequoos/consumer/edit/main/README.md) |

### 5. Configurações Avançadas, Sensores e Integrações

| # | Tópico | Link |
|---|--------|------|
| 17 | Entendendo Variáveis | [PDF](https://github.com/JosiTubaroski/Apache_Airflow_Princial/blob/main/img/2.1.Variaveis.pdf) |
| 18 | Utilizando Variáveis em DAGs | [Ver código](https://github.com/joycequoos/Variables/blob/main/README.md) |
| 19 | Fundamentos de Pools | [PDF](https://github.com/JosiTubaroski/Apache_Airflow_Princial/blob/main/img/3.1.Pools.pdf) |
| 20 | Testando Pools em DAGs | [Ver código](https://github.com/joycequoos/pools/blob/main/README.md) |
| 28 | Fundamentos do Sensor | [PDF](https://github.com/JosiTubaroski/Apache_Airflow_Princial/blob/main/img/8.1.Sensors.pdf) |
| 29 | Criando um sensor para uma API | [Ver código](https://github.com/JosiTubaroski/Apache_Airflow_Princial/blob/main/img/sensors.py) |
| 30 | Operando em banco de dados | [Ver código](https://github.com/JosiTubaroski/Apache_Airflow_Princial/blob/main/img/bancodedados.py) |
| 31 | Hooks | [PDF](https://github.com/JosiTubaroski/Apache_Airflow_Princial/blob/main/img/2.1.Hooks.pdf) |
| 32 | Hooks com banco de dados | [Ver código](https://github.com/JosiTubaroski/Apache_Airflow_Princial/blob/main/img/hooks.py) |

### 6. Infraestrutura, Configuração e Extensibilidade

| # | Tópico | Link |
|---|--------|------|
| 33 | Configurações | [PDF](https://github.com/JosiTubaroski/Apache_Airflow_Princial/blob/main/img/1.Configura%C3%A7%C3%B5es.pdf) |
| 34 | Executers | [PDF](https://github.com/JosiTubaroski/Apache_Airflow_Princial/blob/main/img/2.Executers.pdf) |
| 35 | Plugins | [PDF](https://github.com/JosiTubaroski/Apache_Airflow_Princial/blob/main/img/1.Criando%20Plugins.pdf) |
| 36 | Criando seu próprio Plugin | [Ver código](https://github.com/JosiTubaroski/Apache_Airflow_Princial/blob/main/img/big_data_operator.py) |
| 37 | Conceitos sobre o ecossistema Docker | [Ver anotações](https://github.com/JosiTubaroski/Docker_Compose/edit/main/README.md) |

---

## Por que isso importa

O Airflow é hoje uma peça central de qualquer stack moderna de dados: sem orquestração confiável, pipelines de ETL/ELT, modelos de machine learning e relatórios executivos ficam sujeitos a falhas silenciosas e dados desatualizados. Dominar desde os fundamentos (DAGs, Operators, Trigger Rules) até os recursos avançados (Datasets, Sensors, Hooks, Plugins) é o que permite migrar de scripts isolados para pipelines de produção — resilientes, monitoráveis e escaláveis.

### Próximos passos sugeridos
- Praticar a criação de uma DAG própria conectando a uma fonte de dados real (API, banco de dados ou arquivo).
- Explorar a integração do Airflow com ferramentas de nuvem (ex: BigQuery, S3, Databricks).
- Consultar o [Astronomer Registry](https://registry.astronomer.io/) para exemplos de operadores e integrações prontas.

## Contato

Sugestões, dúvidas ou colaborações são bem-vindas — abra uma *issue* ou entre em contato pelo perfil do GitHub.
