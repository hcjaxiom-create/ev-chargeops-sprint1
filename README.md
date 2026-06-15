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

## 6. Frente 1 — Contexto e Problema

A recarga compartilhada de veículos elétricos acontece quando uma mesma infraestrutura de carregamento é utilizada por diferentes pessoas, como moradores de um condomínio, funcionários de uma empresa, visitantes de um edifício corporativo ou alunos de um campus universitário.

Esse tipo de infraestrutura se torna cada vez mais necessário com o crescimento dos veículos elétricos, mas também cria desafios operacionais para os gestores. Entre os principais desafios estão: identificar corretamente quem utilizou o carregador, registrar o tempo de uso, medir a energia consumida em kWh, calcular quanto cada usuário deve pagar e evitar cobranças injustas entre pessoas que usaram o sistema de formas diferentes.

Em uma sessão de recarga, o processo começa quando o veículo é conectado ao carregador. Em seguida, o sistema precisa identificar o usuário, autorizar o início da recarga, registrar o horário inicial, acompanhar a potência e a energia entregue ao veículo e, no final, registrar o horário de encerramento e o total consumido. Esses dados podem ser capturados por meio do próprio carregador, de cartões RFID, de aplicativos, de APIs ou de sistemas conectados à internet.

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

Existem diferentes formas de cobrança e operação para recarga compartilhada. Os principais modelos são:

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
