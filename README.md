# Plataforma de Gerenciamento de Energia Sustentável

A Plataforma de Gerenciamento de Energia Sustentável tem como objetivo otimizar o consumo de energia em residências e empresas, promovendo práticas sustentáveis. O sistema coleta dados de dispositivos IoT, como medidores inteligentes, para gerar relatórios de consumo e sugestões de melhorias.

---

## 1. Descrição do Projeto

O sistema permite monitorar, analisar e otimizar o consumo de energia elétrica. Ele se integra com dispositivos IoT para capturar dados em tempo real e oferece ferramentas de recomendação, gestão de dispositivos e monitoramento de consumo. A plataforma foca em tornar o uso de energia mais eficiente e sustentável.

---

## 2. Justificativa de Escolha da Arquitetura

Optamos por uma arquitetura escalável e flexível, usando uma abordagem que permita a fácil integração com novos dispositivos IoT, enquanto atende a altos volumes de dados gerados pelos dispositivos. Utilizamos a abordagem de microserviços e a nuvem para garantir que a plataforma consiga escalar conforme a demanda e se manter disponível em qualquer momento.

---

## 3. Diagramas da Arquitetura

Aqui estão os diagramas que ilustram como o sistema foi estruturado, explicando as interações entre os componentes e o fluxo de dados:

### Diagrama de Componentes

Este diagrama mostra os principais módulos do sistema e como eles se interagem. Inclui a plataforma de monitoramento, o banco de dados, o sistema de recomendação e a interface do usuário.

![Diagrama de Componentes](diagrama_de_componentes.png)

### Diagrama de Sequência

Este diagrama ilustra como os diferentes componentes se comunicam durante um ciclo de monitoramento de energia. O fluxo de dados é mostrado, desde a coleta de dados dos dispositivos até a entrega das recomendações.

![Diagrama de Sequência](diagrama_de_sequencia.png)

### Diagrama de Classes

O diagrama de classes descreve as principais entidades do sistema, como o usuário, os dispositivos IoT e os dados de consumo, além das relações entre essas classes.

![Diagrama de Classes](diagrama_de_classes.png)

---

## 4. Detalhamento das Responsabilidades das Classes

De forma resumida, as classes principais do sistema são responsáveis por:

- **User**: Responsável pela configuração e monitoramento do perfil de consumo de energia. 
- **Device**: Representa os dispositivos IoT conectados à plataforma, como os medidores de energia.
- **EnergyConsumption**: Armazena os dados históricos de consumo de energia, calculando as médias e os picos de consumo.
- **RecommendationSystem**: Sistema responsável por sugerir melhorias baseadas no consumo de energia detectado.
- **AlertSystem**: Envia notificações sobre padrões de consumo anormais ou quando o usuário atinge suas metas.

---

## 5. Estratégia de Escalabilidade

A escalabilidade do sistema é dividida em dois tipos:

- **Escalabilidade Horizontal**: Ao usar uma infraestrutura em nuvem (como AWS ou Azure), o sistema pode aumentar automaticamente a quantidade de servidores ou containers quando a demanda cresce. Usamos Docker e Kubernetes para facilitar a criação e a gestão de novas instâncias conforme necessário.
- **Escalabilidade Vertical**: Melhoramos o desempenho dos servidores existentes, aumentando a capacidade de processamento e memória. Além disso, o banco de dados pode ser particionado (sharding) para distribuir os dados de forma mais eficiente entre os servidores.

---

## 6. Estratégia de Banco de Dados

Optamos por usar um banco de dados NoSQL (como MongoDB) para lidar com os dados em grande escala. A flexibilidade do modelo NoSQL permite que os dados de consumo de energia, além dos dispositivos IoT, sejam armazenados de forma eficiente, sem a necessidade de esquemas fixos.

---

## 7. Tecnologias Usadas

- **Frontend**: React para criar uma interface de usuário interativa e dinâmica.
- **Backend**: Node.js com Express para gerenciar a lógica de negócios e as APIs.
- **Banco de Dados**: MongoDB, para um gerenciamento eficiente de dados não estruturados.
- **IoT**: MQTT para comunicação em tempo real entre dispositivos e a plataforma.
- **Infraestrutura**: Docker e Kubernetes para gerenciar os containers e garantir a escalabilidade do sistema.
