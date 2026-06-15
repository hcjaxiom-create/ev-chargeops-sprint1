# EV ChargeOps — Sprint 01

## Enterprise Challenge 2026 — GoodWe / FIAP

## Equipe

Nome: Hugo Camisotti Junior  
RM: rm570978

---

## 1. Introdução

O projeto EV ChargeOps tem como objetivo transformar sessões de recarga de veículos elétricos em dados estruturados, permitindo controle de uso, cálculo de rateio justo, geração de faturas individuais e apoio à tomada de decisão por meio de inteligência artificial.

A solução é pensada para ambientes de recarga compartilhada, como condomínios residenciais, edifícios corporativos e campus universitários, onde diferentes usuários utilizam uma mesma infraestrutura de carregamento.

Nesta primeira sprint, o foco está na pesquisa e documentação da solução proposta. Não será desenvolvido um sistema funcional nesta etapa. O objetivo é compreender o problema, estudar o contexto técnico e regulatório, definir a arquitetura da solução, propor um modelo de rateio e documentar como a inteligência artificial poderá ser aplicada na plataforma.

---

## 2. Problema

Com o crescimento dos veículos elétricos, locais com carregadores compartilhados enfrentam desafios para controlar quem utilizou o carregador, quanto cada usuário consumiu, quanto deve ser cobrado de cada unidade e como organizar os dados das sessões de recarga.

Em muitos condomínios e empresas, a recarga pode gerar dúvidas sobre justiça no rateio, controle de uso, identificação dos usuários e transparência na cobrança. Quando os dados de recarga não são bem organizados, o gestor tem dificuldade para acompanhar consumo, custos, horários de maior demanda e possíveis falhas na operação.

O EV ChargeOps busca resolver esse problema ao organizar os dados das sessões de recarga e transformá-los em informações úteis para usuários e gestores.

---

## 3. Objetivo da Solução

O objetivo da solução é criar uma plataforma capaz de:

- Registrar sessões de recarga de veículos elétricos;
- Identificar usuário, unidade e veículo;
- Calcular o consumo individual em kWh;
- Aplicar um modelo de rateio justo;
- Gerar faturas individuais;
- Apresentar indicadores para o gestor;
- Utilizar inteligência artificial para previsão de consumo, detecção de anomalias e apoio à decisão.

---

## 4. Organização da Sprint 01

A Sprint 01 será organizada em três frentes de pesquisa:

1. Contexto e Problema;
2. Base Regulatória e Técnica;
3. Arquitetura e Inteligência Artificial.

Para cada frente, será desenvolvido o conteúdo obrigatório e uma opção de aprofundamento.

---

## 5. Opções de Aprofundamento Escolhidas

Para esta Sprint 01, foram escolhidas as seguintes opções de aprofundamento:

- Frente 1 — Contexto e Problema: Opção A — Análise de mercado;
- Frente 2 — Base Regulatória e Técnica: Opção C — Mapeamento de APIs complementares;
- Frente 3 — Arquitetura e IA: Opção C — Esquema da base de dados.

Essas escolhas foram feitas porque permitem documentar bem o problema, comparar soluções existentes, entender possíveis integrações técnicas e preparar a base para o desenvolvimento da Sprint 02.

Como o projeto está sendo desenvolvido individualmente em formato EAD, as opções escolhidas priorizam pesquisa documental, análise de soluções existentes, estudo de APIs e definição da estrutura de dados, sem depender de entrevistas presenciais ou desenvolvimento funcional nesta primeira etapa.

---

## 6. Frente 1 — Contexto e Problema

A recarga compartilhada de veículos elétricos acontece quando uma mesma infraestrutura de carregamento é utilizada por diferentes pessoas, como moradores de um condomínio, funcionários de uma empresa, visitantes de um edifício corporativo ou alunos de um campus universitário.

Esse tipo de infraestrutura se torna cada vez mais necessário com o crescimento dos veículos elétricos, mas também cria desafios operacionais para os gestores. Entre os principais desafios estão: identificar corretamente quem utilizou o carregador, registrar o tempo de uso, medir a energia consumida em kWh, calcular quanto cada usuário deve pagar e evitar cobranças injustas entre pessoas que usaram o sistema de formas diferentes.

Em uma sessão de recarga, o processo começa quando o veículo é conectado ao carregador. Em seguida, o sistema precisa identificar o usuário, autorizar o início da recarga, registrar o horário inicial, acompanhar a potência e a energia entregue ao veículo e, no final, registrar o horário de encerramento e o total consumido.

Esses dados podem ser capturados por meio do próprio carregador, cartões RFID, aplicativos, APIs ou sistemas conectados à internet.

Os principais dados gerados em uma sessão de recarga são:

- Identificação do usuário;
- Identificação da unidade ou apartamento;
- Data e horário de início;
- Data e horário de término;
- Tempo total da sessão;
- Energia consumida em kWh;
- Potência utilizada;
- Status da sessão;
- Possíveis falhas ou interrupções.

Esses dados são importantes porque permitem transformar o uso do carregador em informações organizadas para cobrança, gestão e tomada de decisão.

### 6.1 Modelos de negócio para recarga compartilhada

Existem diferentes formas de cobrança e operação para recarga compartilhada.

### Recarga gratuita

Nesse modelo, o custo da energia é pago pelo condomínio, empresa ou instituição. É simples para o usuário, mas pode ser injusto, pois pessoas que não utilizam o carregador também acabam pagando indiretamente pelo serviço.

### Cobrança por kWh

Nesse modelo, o usuário paga proporcionalmente à energia consumida. É um dos modelos mais justos, pois quem consome mais energia paga mais. Esse modelo exige medição confiável do consumo de cada sessão.

### Cobrança por tempo

Nesse modelo, o usuário paga pelo tempo em que o veículo permanece conectado ao carregador. Pode ajudar a evitar que o veículo fique ocupando a vaga após o carregamento, mas nem sempre reflete exatamente o consumo de energia.

### Assinatura mensal

Nesse modelo, o usuário paga um valor fixo por mês para ter direito ao uso do carregador. É simples de administrar, mas pode ser injusto quando alguns usuários utilizam muito mais do que outros.

### Rateio condominial

Nesse modelo, o custo total da energia é dividido entre moradores ou unidades. Pode ser feito de forma igual para todos ou proporcional ao consumo identificado. Para o EV ChargeOps, o modelo mais adequado é o rateio proporcional ao consumo individual em kWh.

---

## 7. Aprofundamento da Frente 1 — Análise de Mercado

Para aprofundar o entendimento do problema, foram analisadas soluções existentes relacionadas à recarga de veículos elétricos e gestão de carregadores compartilhados.

### 7.1 ChargePoint

A ChargePoint é uma plataforma internacional voltada para redes de carregamento de veículos elétricos. Ela permite localizar carregadores, iniciar sessões de recarga, acompanhar consumo e realizar pagamentos.

Principais funcionalidades:

- Localização de estações de recarga;
- Controle de sessões pelo aplicativo;
- Gestão de usuários;
- Relatórios de uso;
- Cobrança pela recarga.

Modelo de negócio:

A empresa atua com venda de equipamentos, software de gestão e serviços para operadores de infraestrutura de recarga.

Limitações:

Apesar de ser uma solução robusta, pode ser complexa e mais voltada para grandes redes de carregamento. Para condomínios menores, pode haver excesso de funcionalidades ou custos mais altos.

### 7.2 Wallbox

A Wallbox oferece carregadores inteligentes para residências, empresas e locais compartilhados. A plataforma permite monitorar o consumo, configurar usuários e controlar o carregamento por aplicativo.

Principais funcionalidades:

- Carregadores conectados;
- Controle por aplicativo;
- Monitoramento de energia;
- Configuração de permissões;
- Gestão de múltiplos usuários.

Modelo de negócio:

A empresa vende carregadores e oferece recursos digitais para controle e monitoramento.

Limitações:

A solução depende do ecossistema da própria marca. Em ambientes com carregadores de diferentes fabricantes, pode haver limitação de integração.

### 7.3 Neocharge

A Neocharge atua no Brasil com soluções para recarga de veículos elétricos, incluindo instalação de carregadores, gestão de recarga e soluções para condomínios e empresas.

Principais funcionalidades:

- Instalação de carregadores;
- Soluções para condomínios;
- Gestão de consumo;
- Apoio na cobrança;
- Suporte técnico.

Modelo de negócio:

A empresa trabalha com fornecimento de equipamentos, instalação e serviços relacionados à infraestrutura de recarga.

Limitações:

Por ser uma solução comercial pronta, pode limitar a personalização do modelo de rateio e da aplicação de inteligência artificial conforme as necessidades específicas de cada condomínio ou campus.

### 7.4 Análise própria

A análise dessas soluções mostra que já existem plataformas capazes de controlar recargas, usuários e consumo. Porém, o EV ChargeOps se diferencia por focar na transformação dos dados de sessão em inteligência operacional para ambientes compartilhados.

A proposta do EV ChargeOps não é apenas registrar a recarga, mas organizar os dados para gerar rateio justo, relatórios para o gestor, previsão de consumo, identificação de anomalias e apoio à tomada de decisão.

Dessa forma, a solução pode ser aplicada em condomínios, empresas e campus universitários que precisam de controle transparente, cobrança individualizada e melhor gestão da infraestrutura.

---

## 8. Frente 2 — Base Regulatória e Técnica

A segunda frente da pesquisa analisa os aspectos regulatórios e técnicos relacionados à operação de carregadores de veículos elétricos em infraestrutura compartilhada.

Essa etapa é importante porque uma solução de recarga não depende apenas de software. Ela também precisa respeitar normas do setor elétrico, utilizar equipamentos compatíveis e trabalhar com dados confiáveis vindos do carregador ou de plataformas integradas.

### 8.1 Resolução Normativa ANEEL nº 1.000/2021

A Resolução Normativa ANEEL nº 1.000/2021 consolida as regras de prestação do serviço público de distribuição de energia elétrica no Brasil. Para o contexto de recarga de veículos elétricos, ela é relevante porque trata da possibilidade de exploração comercial da recarga, da comunicação à distribuidora e da necessidade de equipamentos com protocolos abertos em situações de uso não exclusivamente privado.

No contexto do EV ChargeOps, a resolução é importante porque a solução proposta pode ser aplicada em ambientes onde diferentes usuários utilizam o mesmo carregador, como condomínios, empresas ou campus universitários.

A plataforma proposta não tem como objetivo atuar como distribuidora de energia, mas sim como uma camada de gestão, controle e rateio do consumo. Mesmo assim, é necessário que o projeto considere as regras aplicáveis para evitar uma operação irregular.

Pontos relevantes para o projeto:

- A recarga de veículos elétricos pode ocorrer em ambientes privados ou compartilhados;
- A cobrança precisa ser transparente e baseada em critérios claros;
- O gestor deve ter condições de demonstrar o consumo individual;
- O equipamento deve permitir integração e coleta confiável de dados;
- O uso de protocolos abertos facilita a interoperabilidade da solução.

### 8.2 Carregador GoodWe HCA G2

O carregador GoodWe HCA G2 é o equipamento considerado no desafio. Ele possui recursos de conectividade e identificação que podem ser utilizados pela plataforma EV ChargeOps.

As principais interfaces citadas no desafio são:

### RS-485

Interface de comunicação utilizada em ambientes industriais e equipamentos elétricos. Pode permitir troca de dados entre o carregador e outros sistemas locais, dependendo da configuração e do protocolo utilizado.

### LAN

Conexão por rede cabeada. Pode ser usada para comunicação mais estável com sistemas locais ou com a internet, permitindo envio de dados de status, consumo e eventos.

### Wi-Fi

Conexão sem fio. Permite conectar o carregador à rede do condomínio, empresa ou campus, facilitando a comunicação com plataformas em nuvem.

### Bluetooth

Pode ser utilizado para configurações locais, pareamento, manutenção ou interações próximas ao equipamento.

### RFID

Recurso muito importante para ambientes compartilhados. Com RFID, cada usuário pode ter um cartão ou tag para se identificar antes de iniciar uma sessão de recarga. Isso permite associar o consumo ao usuário correto.

### 8.3 Uso das interfaces na plataforma

No EV ChargeOps, essas interfaces podem ser usadas da seguinte forma:

- RFID: identificar o usuário que iniciou a recarga;
- LAN ou Wi-Fi: enviar dados do carregador para a plataforma;
- RS-485: permitir integração técnica local, quando disponível;
- Bluetooth: apoiar configuração e manutenção local;
- API ou portal em nuvem: consultar dados consolidados de sessões e consumo.

A combinação dessas tecnologias permite que a plataforma registre dados de forma confiável e organize as informações para cálculo de rateio, dashboards e análises com inteligência artificial.

### 8.4 API GoodWe SEMS Portal

A API GoodWe SEMS Portal pode ser utilizada como uma fonte de dados para a plataforma EV ChargeOps. A partir dela, a solução poderia consultar informações relacionadas ao carregador, como status, potência, energia entregue, histórico de eventos e dados de sessão, dependendo da disponibilidade dos endpoints.

Esses dados seriam importantes para alimentar o banco de dados da plataforma e permitir:

- Registro automático de sessões;
- Consulta do status do carregador;
- Medição de energia entregue em kWh;
- Histórico de uso;
- Identificação de falhas;
- Construção de indicadores para o gestor.

Mesmo que a Sprint 01 não exija implementação funcional, o estudo da API ajuda a definir como a plataforma poderá ser construída na Sprint 02.

---

## 9. Aprofundamento da Frente 2 — Mapeamento de APIs Complementares

Como aprofundamento da Frente 2, foram analisadas APIs externas que podem enriquecer a plataforma EV ChargeOps.

Essas APIs não substituem os dados do carregador, mas podem complementar a solução com informações sobre localização, infraestrutura, pontos de recarga e dados públicos.

### 9.1 Open Charge Map API

A Open Charge Map é uma plataforma colaborativa que disponibiliza dados sobre estações de recarga de veículos elétricos em vários países.

Possíveis usos no EV ChargeOps:

- Consultar pontos de recarga próximos;
- Comparar a infraestrutura local com outras regiões;
- Enriquecer mapas e dashboards;
- Apoiar análises sobre distribuição de carregadores;
- Criar referências externas para benchmarking.

Dados que podem ser utilizados:

- Nome da estação;
- Localização geográfica;
- Tipo de conector;
- Potência disponível;
- Status ou informações da estação;
- Operador responsável.

Aplicação no projeto:

No EV ChargeOps, a API da Open Charge Map poderia ser usada para comparar a infraestrutura do condomínio, empresa ou campus com a disponibilidade de pontos de recarga na região. Isso ajudaria o gestor a entender se sua estrutura está adequada à demanda local.

### 9.2 Google Places API — evChargeOptions

A Google Places API pode fornecer informações sobre locais e, em alguns casos, dados relacionados a opções de carregamento para veículos elétricos, por meio do campo evChargeOptions.

Possíveis usos no EV ChargeOps:

- Identificar locais com carregadores próximos;
- Mostrar pontos de recarga em mapas;
- Enriquecer a experiência do usuário;
- Apoiar análises de localização;
- Comparar infraestrutura interna e externa.

Dados que podem ser úteis:

- Nome do local;
- Endereço;
- Coordenadas geográficas;
- Opções de recarga;
- Informações de disponibilidade, quando existentes;
- Avaliações e dados do local.

Aplicação no projeto:

A integração com a Google Places API poderia permitir que o usuário visualize alternativas de recarga próximas quando o carregador compartilhado estiver ocupado ou indisponível.

### 9.3 ANEEL Open Data

A ANEEL disponibiliza dados públicos relacionados ao setor elétrico brasileiro. Esses dados podem ser utilizados para enriquecer análises regulatórias, tarifárias ou de infraestrutura.

Possíveis usos no EV ChargeOps:

- Apoiar estudos sobre energia elétrica;
- Consultar dados públicos do setor;
- Analisar informações de distribuição;
- Complementar a base regulatória;
- Apoiar comparações regionais.

Aplicação no projeto:

A plataforma poderia utilizar dados públicos da ANEEL para contextualizar tarifas, regiões de distribuição e aspectos relacionados à infraestrutura elétrica.

### 9.4 Análise própria

As APIs complementares ampliam a capacidade da plataforma, permitindo que o EV ChargeOps vá além do simples controle de sessões. Com dados externos, a solução pode gerar análises de localização, disponibilidade, comparação regional e apoio à tomada de decisão.

Para a Sprint 02, a prioridade será simular dados internos de sessões de recarga. As APIs externas poderão ser utilizadas como evolução da solução, caso haja tempo para implementação.

---

## 10. Frente 3 — Arquitetura e Inteligência Artificial

A terceira frente define como a solução será estruturada, como os dados irão fluir dentro da plataforma, como será feito o cálculo de rateio e qual será o papel da inteligência artificial.

A arquitetura do EV ChargeOps será dividida em quatro camadas principais:

1. Camada física;
2. Camada de conectividade;
3. Camada de aplicação;
4. Camada de apresentação.

### 10.1 Camada física

A camada física é composta pelo carregador GoodWe HCA G2 e pelos veículos elétricos conectados a ele.

Nessa camada ocorre a recarga em si. O veículo é conectado ao carregador, o usuário é identificado e a sessão é iniciada.

Dados gerados nessa camada:

- Início da sessão;
- Fim da sessão;
- Energia entregue;
- Potência utilizada;
- Status do carregador;
- Falhas ou interrupções.

### 10.2 Camada de conectividade

A camada de conectividade é responsável por transmitir os dados do carregador para a plataforma.

Ela pode utilizar:

- Wi-Fi;
- LAN;
- RS-485;
- Bluetooth;
- RFID;
- API GoodWe SEMS Portal.

Essa camada é essencial para garantir que os dados sejam coletados de forma confiável.

### 10.3 Camada de aplicação

A camada de aplicação é o núcleo do EV ChargeOps. Nela ficam o back-end, as regras de negócio, o banco de dados, o cálculo de rateio e os módulos de inteligência artificial.

Responsabilidades dessa camada:

- Receber dados das sessões;
- Validar informações;
- Armazenar dados;
- Calcular consumo;
- Calcular faturas;
- Detectar anomalias;
- Gerar previsões;
- Disponibilizar informações para dashboards e telas.

### 10.4 Camada de apresentação

A camada de apresentação é a interface utilizada pelos usuários e gestores.

Para o gestor, a plataforma deve apresentar:

- Total de energia consumida;
- Consumo por usuário;
- Consumo por unidade;
- Sessões realizadas;
- Faturas geradas;
- Alertas de anomalias;
- Horários de maior utilização.

Para o usuário, a plataforma deve apresentar:

- Histórico de recargas;
- Consumo individual;
- Valor a pagar;
- Status da sessão;
- Fatura do mês.

---

## 11. Fluxo dos Dados

O fluxo dos dados no EV ChargeOps seguirá as seguintes etapas:

1. O usuário se identifica no carregador, por RFID ou aplicativo;
2. O veículo é conectado ao carregador;
3. A sessão de recarga é iniciada;
4. O carregador registra horário, potência, energia entregue e status;
5. Os dados são enviados para a plataforma;
6. O back-end valida e organiza os dados;
7. A sessão é salva no banco de dados;
8. O sistema calcula o consumo individual;
9. O modelo de rateio calcula o valor da fatura;
10. A IA analisa padrões, prevê consumo e identifica anomalias;
11. O gestor visualiza indicadores no dashboard;
12. O usuário acessa sua fatura e histórico de uso.

---

## 12. Diagrama de Arquitetura

O diagrama abaixo representa a arquitetura proposta para a solução EV ChargeOps.

```mermaid
flowchart TD
    A[Veículo Elétrico] --> B[Carregador GoodWe HCA G2]
    C[Usuário / RFID / App] --> B
    B --> D[Conectividade: Wi-Fi, LAN, RS-485, Bluetooth]
    D --> E[API GoodWe SEMS Portal]
    E --> F[Back-end EV ChargeOps]
    F --> G[Banco de Dados]
    G --> H[Módulo de Rateio]
    G --> I[Módulo de Inteligência Artificial]
    H --> J[Fatura Individual]
    I --> K[Previsões, Alertas e Análises]
    J --> L[Dashboard do Gestor]
    K --> L
    J --> M[Interface do Usuário]
---

## 13. Modelo de Rateio Proposto

O modelo de rateio proposto para o EV ChargeOps será baseado principalmente no consumo individual de energia em kWh.

A fórmula principal será:

Valor da sessão = kWh consumido × tarifa de energia

Além disso, poderá ser adicionada uma taxa administrativa definida pelo condomínio, empresa ou campus.

Fórmula completa:

Valor final = kWh consumido × tarifa de energia + taxa administrativa

### 13.1 Exemplo de cálculo

Suponha que um usuário tenha consumido 50 kWh no mês.

Tarifa de energia: R$ 1,00 por kWh  
Taxa administrativa: R$ 10,00  

Cálculo:

50 × 1,00 + 10,00 = R$ 60,00

Valor final da fatura: R$ 60,00

### 13.2 Critérios utilizados

O modelo considera as seguintes variáveis:

- Usuário;
- Unidade ou apartamento;
- Veículo;
- Quantidade de kWh consumida;
- Tarifa de energia;
- Taxa administrativa;
- Data da sessão;
- Status da sessão.

### 13.3 Justificativa do modelo

O rateio por kWh consumido é considerado o modelo mais justo porque cada usuário paga proporcionalmente ao que realmente utilizou. Dessa forma, moradores ou usuários que não utilizaram o carregador não são cobrados pelo consumo de quem utilizou.

Esse modelo também facilita auditoria, transparência e geração de relatórios.

### 13.4 Casos excepcionais

### Usuário que não carregou no mês

Caso o usuário não tenha realizado nenhuma sessão de recarga, sua cobrança será R$ 0,00, exceto se o condomínio definir uma taxa fixa de manutenção.

### Sessão interrompida

Se uma sessão for interrompida, o sistema cobrará apenas a energia realmente entregue ao veículo até o momento da interrupção.

### Dois veículos da mesma unidade

Caso uma mesma unidade possua dois veículos, o consumo dos dois poderá ser somado na mesma fatura da unidade.

### Sessão sem identificação

Caso uma sessão seja registrada sem identificação correta do usuário, ela ficará pendente para validação do gestor.

### Veículo conectado após fim da recarga

Caso o veículo permaneça conectado após o término da recarga, a plataforma poderá registrar o tempo de ocupação da vaga. Em uma evolução futura, poderá ser criada uma regra de cobrança por ociosidade.

---

## 14. Papel da Inteligência Artificial na Solução

A inteligência artificial será utilizada como parte estrutural da solução, e não apenas como um recurso adicional. O objetivo da IA será transformar os dados das sessões de recarga em informações úteis para gestão, previsão e tomada de decisão.

### 14.1 Previsão de consumo

A IA poderá analisar o histórico de sessões e prever o consumo futuro de energia.

Técnica possível:

- Regressão;
- Modelos de séries temporais;
- Algoritmos de machine learning supervisionado.

Dados necessários:

- Histórico de sessões;
- kWh consumido;
- Horário de uso;
- Dia da semana;
- Usuário;
- Unidade;
- Tarifa de energia.

Impacto esperado:

- Apoiar o planejamento energético;
- Prever custo mensal;
- Ajudar o condomínio ou empresa a dimensionar a infraestrutura;
- Antecipar períodos de maior demanda.

### 14.2 Detecção de anomalias

A IA poderá identificar comportamentos fora do padrão.

Exemplos de anomalias:

- Consumo muito acima do histórico;
- Sessões muito longas;
- Carregamento iniciado e interrompido rapidamente;
- Usuário com padrão de uso incomum;
- Carregador com falhas recorrentes.

Técnicas possíveis:

- Detecção estatística de outliers;
- Isolation Forest;
- Comparação com média histórica;
- Regras inteligentes combinadas com machine learning.

Impacto esperado:

- Redução de falhas não percebidas;
- Mais segurança na cobrança;
- Melhor controle operacional;
- Identificação de uso indevido.

### 14.3 Agrupamento de perfis de uso

A IA também poderá agrupar usuários por comportamento.

Exemplos de perfis:

- Usuário frequente;
- Usuário eventual;
- Usuário de horário de pico;
- Usuário de carregamentos longos;
- Usuário de baixo consumo.

Técnica possível:

- Clustering, como K-Means.

Dados necessários:

- Frequência de uso;
- Consumo médio;
- Horário médio de recarga;
- Duração média das sessões.

Impacto esperado:

- Melhor entendimento dos usuários;
- Criação de regras mais justas;
- Apoio para expansão da infraestrutura;
- Identificação de padrões de demanda.

### 14.4 Assistente inteligente para o gestor

Em uma evolução da solução, poderá ser criado um assistente conversacional para responder perguntas do gestor.

Exemplos de perguntas:

- Qual unidade mais consumiu energia este mês?
- Quanto será cobrado do apartamento 52?
- Qual foi o horário de maior uso?
- Existe alguma sessão fora do padrão?
- Qual a previsão de consumo para o próximo mês?

Esse assistente poderia utilizar processamento de linguagem natural para facilitar a consulta aos dados da plataforma.

---

## 15. Aprofundamento da Frente 3 — Esquema da Base de Dados

Como aprofundamento da Frente 3, foi definido um esquema inicial de banco de dados para a plataforma EV ChargeOps.

O objetivo desse esquema é organizar as principais entidades do sistema e preparar a base para a implementação da Sprint 02.

### 15.1 Tabela: usuarios

| Campo | Tipo | Descrição |
|---|---|---|
| id_usuario | inteiro | Identificador único do usuário |
| nome | texto | Nome do usuário |
| email | texto | E-mail do usuário |
| telefone | texto | Telefone do usuário |
| id_unidade | inteiro | Unidade vinculada ao usuário |
| status | texto | Ativo ou inativo |

Exemplo:

| id_usuario | nome | email | telefone | id_unidade | status |
|---|---|---|---|---|---|
| 1 | João Silva | joao@email.com | 11999990000 | 101 | ativo |

### 15.2 Tabela: unidades

| Campo | Tipo | Descrição |
|---|---|---|
| id_unidade | inteiro | Identificador da unidade |
| bloco | texto | Bloco ou torre |
| numero | texto | Número da unidade |
| responsavel | texto | Responsável pela unidade |

Exemplo:

| id_unidade | bloco | numero | responsavel |
|---|---|---|---|
| 101 | A | 52 | João Silva |

### 15.3 Tabela: veiculos

| Campo | Tipo | Descrição |
|---|---|---|
| id_veiculo | inteiro | Identificador do veículo |
| id_usuario | inteiro | Usuário proprietário |
| modelo | texto | Modelo do veículo |
| placa | texto | Placa do veículo |
| tipo_conector | texto | Tipo de conector utilizado |

Exemplo:

| id_veiculo | id_usuario | modelo | placa | tipo_conector |
|---|---|---|---|---|
| 1 | 1 | BYD Dolphin | ABC1D23 | Tipo 2 |

### 15.4 Tabela: carregadores

| Campo | Tipo | Descrição |
|---|---|---|
| id_carregador | inteiro | Identificador do carregador |
| modelo | texto | Modelo do carregador |
| localizacao | texto | Local onde está instalado |
| status | texto | Disponível, em uso ou manutenção |

Exemplo:

| id_carregador | modelo | localizacao | status |
|---|---|---|---|
| 1 | GoodWe HCA G2 | Estacionamento L1 | disponível |

### 15.5 Tabela: sessoes_recarga

| Campo | Tipo | Descrição |
|---|---|---|
| id_sessao | inteiro | Identificador da sessão |
| id_usuario | inteiro | Usuário da sessão |
| id_unidade | inteiro | Unidade vinculada |
| id_veiculo | inteiro | Veículo carregado |
| id_carregador | inteiro | Carregador utilizado |
| data_inicio | data/hora | Início da sessão |
| data_fim | data/hora | Fim da sessão |
| kwh_consumido | decimal | Energia consumida |
| tempo_minutos | inteiro | Duração da sessão |
| status_sessao | texto | Finalizada, interrompida ou pendente |

Exemplo:

| id_sessao | id_usuario | id_unidade | id_veiculo | id_carregador | data_inicio | data_fim | kwh_consumido | tempo_minutos | status_sessao |
|---|---|---|---|---|---|---|---|---|---|
| 1 | 1 | 101 | 1 | 1 | 2026-06-10 18:00 | 2026-06-10 21:00 | 22.5 | 180 | finalizada |

### 15.6 Tabela: faturas

| Campo | Tipo | Descrição |
|---|---|---|
| id_fatura | inteiro | Identificador da fatura |
| id_unidade | inteiro | Unidade cobrada |
| mes_referencia | texto | Mês da cobrança |
| total_kwh | decimal | Total consumido |
| tarifa_kwh | decimal | Tarifa aplicada |
| taxa_administrativa | decimal | Taxa fixa, se existir |
| valor_total | decimal | Valor final da fatura |
| status_pagamento | texto | Pendente, pago ou vencido |

Exemplo:

| id_fatura | id_unidade | mes_referencia | total_kwh | tarifa_kwh | taxa_administrativa | valor_total | status_pagamento |
|---|---|---|---|---|---|---|---|
| 1 | 101 | 06/2026 | 50.0 | 1.00 | 10.00 | 60.00 | pendente |

### 15.7 Relacionamentos entre as tabelas

- Uma unidade pode ter vários usuários;
- Um usuário pode ter um ou mais veículos;
- Um carregador pode ter várias sessões;
- Uma sessão pertence a um usuário, uma unidade, um veículo e um carregador;
- Uma fatura pertence a uma unidade;
- Uma fatura pode consolidar várias sessões de recarga no mês.

---

## 16. Tecnologias Propostas para a Sprint 02

Para a Sprint 02, serão utilizadas tecnologias simples e adequadas para um protótipo funcional.

Tecnologias sugeridas:

- Python;
- Streamlit;
- SQLite;
- Pandas;
- Scikit-learn;
- GitHub.

### 16.1 Justificativa das tecnologias

### Python

Será utilizado por ser uma linguagem simples, flexível e adequada para manipulação de dados, criação de protótipos e aplicação de inteligência artificial.

### Streamlit

Será utilizado para criar uma interface web simples, permitindo visualizar sessões, faturas e indicadores sem a necessidade de desenvolver uma aplicação complexa.

### SQLite

Será utilizado como banco de dados local para armazenar usuários, unidades, veículos, sessões e faturas.

### Pandas

Será utilizado para manipulação e análise dos dados.

### Scikit-learn

Será utilizado para testes simples de inteligência artificial, como detecção de anomalias ou agrupamento de usuários.

### GitHub

Será utilizado para versionamento e entrega do projeto.

---

## 17. Plano para a Sprint 02

Na Sprint 02, será desenvolvido um protótipo funcional com base nas decisões documentadas nesta primeira sprint.

Ordem planejada de desenvolvimento:

1. Criar a estrutura do banco de dados;
2. Criar dados simulados de usuários, unidades, veículos e sessões;
3. Implementar o cálculo de consumo por usuário;
4. Implementar o cálculo de fatura por unidade;
5. Criar uma interface simples em Streamlit;
6. Criar tela de visualização para o gestor;
7. Criar tela de histórico para o usuário;
8. Implementar gráficos de consumo;
9. Criar um módulo inicial de IA para detectar anomalias;
10. Documentar o funcionamento do protótipo no GitHub.

### 17.1 Funcionalidades previstas

O protótipo da Sprint 02 deverá permitir:

- Cadastrar ou simular usuários;
- Cadastrar ou simular unidades;
- Registrar sessões de recarga;
- Calcular kWh consumido;
- Gerar fatura individual;
- Visualizar consumo mensal;
- Visualizar ranking de consumo por unidade;
- Identificar sessões fora do padrão;
- Apresentar um dashboard para o gestor.

### 17.2 Resultado esperado

Ao final da Sprint 02, espera-se entregar um protótipo capaz de demonstrar como dados de recarga podem ser organizados, analisados e utilizados para gerar cobrança justa e inteligência operacional.

---

## 18. Conclusão

A Sprint 01 permitiu compreender o problema da recarga compartilhada de veículos elétricos e propor uma solução estruturada para controle, rateio e análise dos dados.

O EV ChargeOps busca resolver um problema real de condomínios, empresas e campus universitários: como transformar sessões de recarga em dados confiáveis, cobrança justa e informações úteis para gestão.

A solução proposta utiliza o carregador GoodWe HCA G2 como base física, integra dados por conectividade e APIs, organiza as informações em banco de dados, aplica regras de rateio e utiliza inteligência artificial para gerar previsões, alertas e análises.

Para a próxima sprint, o foco será transformar essa documentação em um protótipo funcional, utilizando Python, Streamlit, SQLite, Pandas e recursos iniciais de inteligência artificial.

---

## 19. Fontes Consultadas

As fontes abaixo foram utilizadas como base para pesquisa e estruturação da proposta:

- ANEEL — Resolução Normativa nº 1.000/2021.
- ANEEL — Dados Abertos.
- GoodWe — SEMS Portal.
- GoodWe — Informações sobre carregadores e soluções de energia.
- Open Charge Map — Documentação da API.
- Google Developers — Google Places API e campo evChargeOptions.
- ABVE — Associação Brasileira do Veículo Elétrico.
- SENATRAN / DENATRAN — Dados de frota nacional.
- IBGE — Dados geográficos e populacionais.
- ChargePoint — Soluções de carregamento para veículos elétricos.
- Wallbox — Soluções de carregadores inteligentes.
- Neocharge — Soluções de recarga para condomínios e empresas.
- Kaggle — Electric Vehicle Charging Sessions Dataset.
- UCI Machine Learning Repository — Datasets de consumo energético.
