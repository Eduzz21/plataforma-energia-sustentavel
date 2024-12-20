# **Descrição Geral**  
O sistema será uma **Plataforma de Gerenciamento de Energia Sustentável**, integrando dispositivos IoT, como medidores inteligentes, para monitorar, analisar e otimizar o consumo de energia elétrica em residências e empresas.  

O principal objetivo é oferecer ferramentas práticas para promover o uso eficiente de energia, reduzir desperdícios e incentivar práticas sustentáveis.  

---

## **Características Principais do Sistema**  

### 1. **Monitoramento em Tempo Real**  
- Captura e apresenta dados de consumo energético diretamente dos dispositivos IoT conectados.  

### 2. **Relatórios Personalizados**  
- Gera relatórios detalhados com visualizações claras, como gráficos e tabelas, permitindo:  
  - Comparação de consumo em diferentes períodos.  
  - Identificação de padrões e picos de uso.  
  - Informações acionáveis para reduzir desperdícios.  

### 3. **Sistema de Recomendação**  
- Sugere melhorias com base em dados históricos e padrões detectados no consumo energético.  

### 4. **Definição de Metas**  
- Permite aos usuários configurarem objetivos de redução de consumo e acompanhar o progresso.  

### 5. **Alertas Automatizados**  
- Envia notificações em tempo real, alertando sobre consumo excessivo ou desvios de metas configuradas.  

### 6. **Gestão de Dispositivos IoT**  
- Facilita a adição, configuração e monitoramento dos dispositivos conectados na plataforma.  


# Requisitos Funcionais e Não Funcionais

---

## Funcionais

### 1. Monitoramento em Tempo Real
O sistema precisa ser capaz de coletar e mostrar os dados de consumo de energia de dispositivos IoT conectados, como medidores inteligentes e sensores. Esses dados precisam ser atualizados em tempo real, então o usuário vai ver o consumo de energia à medida que ele acontece.

### 2. Relatórios Personalizados
O sistema vai gerar relatórios detalhados, onde o usuário pode ver o consumo de energia de diferentes dispositivos e em diferentes períodos (diário, semanal, mensal). Além disso, o sistema deve gerar gráficos para ajudar na visualização desses dados e ainda dar recomendações sobre o que pode ser feito para melhorar o consumo.

### 3. Sistema de Recomendação
Com base no histórico de consumo, o sistema vai sugerir algumas ações para ajudar a reduzir o consumo de energia. Exemplos de recomendações: "diminuir o uso de iluminação durante a noite" ou "trocar aparelhos antigos por mais eficientes".

### 4. Definição de Metas
O sistema vai permitir que o usuário defina metas, como, por exemplo, reduzir 10% do consumo nos próximos três meses. O sistema vai acompanhar essas metas e mostrar se o usuário está conseguindo alcançá-las.

### 5. Alertas Automatizados
Quando o consumo de energia ultrapassar certos limites ou se houver picos de consumo inesperados, o sistema vai mandar um alerta para o usuário. Isso ajuda a evitar desperdício de energia.

### 6. Gestão de Dispositivos IoT
O usuário vai poder adicionar, configurar e monitorar os dispositivos IoT conectados de uma forma simples e fácil. O sistema também precisa ser compatível com novos dispositivos que possam aparecer no futuro.

---

## Não Funcionais

### 1. Escalabilidade
O sistema precisa ser escalável, ou seja, ele precisa conseguir lidar com o aumento de usuários e de dados sem perder a performance. Isso é importante porque a quantidade de dispositivos IoT vai crescer com o tempo.

### 2. Desempenho
O sistema precisa ser rápido. Quando o usuário pedir informações ou gerar relatórios, o sistema deve responder de forma rápida e sem demora. Isso é crucial para garantir uma boa experiência para o usuário.

### 3. Segurança
A segurança dos dados é muito importante. O sistema vai lidar com informações pessoais dos usuários e dados sensíveis de consumo. Por isso, as comunicações precisam ser criptografadas e o sistema deve seguir as leis de proteção de dados, como a LGPD.

### 4. Manutenibilidade
A arquitetura do sistema precisa ser bem estruturada e modular para facilitar manutenções e futuras atualizações. Se no futuro forem necessários novos dispositivos ou funcionalidades, o sistema deve ser fácil de expandir sem causar problemas.

## 2.2. Escolha da Arquitetura

A arquitetura de **microservices** foi escolhida para o sistema de gerenciamento de energia sustentável porque ela oferece várias vantagens, como **escalabilidade**, **flexibilidade** e **facilidade de manutenção**.

### Escalabilidade
Cada microservice funciona de forma independente, o que significa que podemos **escalar partes específicas** do sistema quando a demanda aumenta, sem precisar expandir todo o sistema de uma vez. Isso é super importante porque com o tempo o número de dispositivos IoT vai crescer e a quantidade de usuários também. Assim, podemos ajustar o sistema sem sobrecarregar tudo.

### Flexibilidade
Como os microservices são serviços pequenos e independentes, eles **podem ser atualizados ou modificados** sem afetar todo o sistema. Se precisarmos adicionar novas funcionalidades ou integrar novos dispositivos IoT, podemos fazer isso com mais facilidade.

### Manutenção
A arquitetura de microservices também facilita a **manutenção** do sistema, pois cada serviço é isolado. Se algo der errado com um serviço, não vai afetar os outros, e as atualizações podem ser feitas de forma mais rápida e sem interrupções. Isso torna o sistema mais confiável a longo prazo.

### Segurança
Além disso, cada microservice pode ter seus próprios **controles de acesso**, o que aumenta a **segurança**. Isso ajuda a proteger os dados dos usuários e as informações de consumo de energia, já que diferentes partes do sistema podem ter diferentes níveis de acesso.

### Resumo
Em resumo, a arquitetura de microservices atende às necessidades do sistema por ser escalável, flexível e segura. Ela facilita a integração com novos dispositivos IoT e garante que o sistema possa evoluir ao longo do tempo sem causar grandes problemas ou interrupções.

## 3. Diagramas

### Diagrama de Componentes
O **Diagrama de Componentes** mostra como as partes principais do sistema estão conectadas. Ele inclui os seguintes componentes:

- **Frontend**: É a interface do usuário, ou seja, o que as pessoas veem e interagem ao usar a plataforma. O Frontend envia as solicitações para o Backend.
- **Backend**: É o "cérebro" do sistema, onde os dados são processados e gerenciados. O Backend se comunica com os dispositivos IoT, como os medidores inteligentes, para pegar os dados de consumo em tempo real. Ele também acessa o **Banco de Dados** para recuperar o histórico de consumo do usuário.
- **Dispositivos IoT**: São os medidores inteligentes e outros sensores conectados que fornecem os dados de consumo energético em tempo real.
- **Banco de Dados**: Armazena o histórico de consumo e outros dados importantes, como as configurações dos dispositivos e as metas do usuário.
- **Notificações**: Caso o consumo ultrapasse um limite definido, o Backend envia uma notificação para o **Usuário**.

Esse diagrama ajuda a visualizar como cada parte do sistema se conecta e trabalha em conjunto.

### Diagrama de Sequência
O **Diagrama de Sequência** descreve o passo a passo de como as ações acontecem no sistema, em ordem cronológica. O processo é o seguinte:

1. O **Usuário** acessa o **Frontend**, que é a interface que ele utiliza para interagir com o sistema.
2. O **Frontend** envia uma requisição para o **Backend** para buscar dados de consumo.
3. O **Backend** então consulta os **Dispositivos IoT** para obter os dados em tempo real de consumo de energia.
4. Em seguida, o **Backend** verifica o **Banco de Dados** para consultar o histórico de consumo.
5. Se o consumo ultrapassar o limite definido pelo usuário, o **Backend** envia uma **notificação** para o **Usuário**.
   
Esse diagrama deixa claro como as ações se conectam, desde o momento em que o usuário faz uma solicitação até o envio de alertas.

### Diagrama de Classes
O **Diagrama de Classes** ilustra as principais **entidades** do sistema e como elas se relacionam. As classes principais são:

- **Usuário**: O usuário do sistema, que pode acessar seus dados de consumo, visualizar relatórios e receber notificações quando o consumo ultrapassar os limites.
- **Consumo**: Representa os dados de consumo de energia, calculados com base nas leituras dos **Dispositivos IoT**.
- **Relatório**: Gera relatórios com base no histórico de consumo do usuário, para ajudá-lo a entender seus padrões de uso de energia.
- **Notificação**: Envia alertas ao **Usuário** caso o consumo ultrapasse os limites definidos por ele.

Essas classes estão interligadas de forma que cada uma desempenha um papel específico na gestão e processamento dos dados.

### Conclusão
Esses três diagramas — **Componentes**, **Sequência** e **Classes** — fornecem uma visão detalhada e clara de como o sistema funciona. Eles mostram desde a interação do usuário com o sistema até como os dados são coletados e processados, incluindo como as notificações são enviadas quando necessário.

### 1. Classe Usuário
```plaintext

Classe Usuário: Essa classe é bem importante porque ela gerencia todas as informações do usuário, como nome, e-mail e as metas que ele define para controlar o consumo de energia. Além disso, ela também é responsável por enviar alertas para o usuário quando o consumo ultrapassa os limites definidos.

Classe Usuario:
  Atributos:
    nome
    email
    metas_de_consumo
    alertas

  Métodos:
    função cadastrarUsuario(nome, email):
      this.nome = nome
      this.email = email
      criarNotificação("Bem-vindo ao sistema de gerenciamento de energia!")

    função configurarMeta(consumo_ideal):
      this.metas_de_consumo = consumo_ideal

    função receberAlerta(mensagem):
      this.alertas.adicionar(mensagem)

    função visualizarRelatorio():
      retorne Relatorio.gerarRelatorio(this.nome, this.metas_de_consumo)
No pseudocódigo, temos uma função que cadastra o usuário, configurando seu nome e e-mail. Depois, ele pode configurar uma meta de consumo para controlar quanto quer gastar de energia, e, se o consumo ultrapassar esse limite, ele recebe uma notificação. A função visualizarRelatorio gera um relatório personalizado para o usuário com base no consumo e nas metas que ele definiu.


Classe Consumo: Essa classe cuida do registro do consumo de energia. Ela recebe os dados de consumo do usuário e verifica se o valor registrado excede o limite da meta definida. Se isso acontecer, a classe envia um alerta.

Classe Consumo:
  Atributos:
    usuario
    data
    consumo_kWh

  Métodos:
    função registrarConsumo(usuario, consumo):
      this.usuario = usuario
      this.data = obterDataAtual()
      this.consumo_kWh = consumo
      verificarLimiteConsumo(usuario)

    função calcularConsumoTotal():
      retorne this.consumo_kWh

    função verificarLimiteConsumo(usuario):
      se this.consumo_kWh > usuario.metas_de_consumo:
        usuario.receberAlerta("Limite de consumo excedido!")
        
        Aqui, temos funções que registram o consumo e calcular o consumo total que o usuário fez em determinado período. A função verificarLimiteConsumo serve para garantir que o usuário seja notificado caso ultrapasse o limite estipulado por ele.

Classe DispositivoIoT: Como o sistema vai estar integrado com dispositivos de medição inteligente (como medidores de energia conectados via IoT), essa classe gerencia esses dispositivos. Ela é responsável por registrar o dispositivo e também por medir o consumo de energia em tempo real.

Classe DispositivoIoT:
  Atributos:
    id_dispositivo
    tipo
    consumo_atual

  Métodos:
    função registrarDispositivo(id, tipo):
      this.id_dispositivo = id
      this.tipo = tipo
      this.consumo_atual = 0

    função medirConsumo(consumo):
      this.consumo_atual = consumo
      retornar this.consumo_atual

O método medirConsumo simula a captura de dados do medidor, que são usados pelo sistema para calcular o consumo atual de energia do usuário. Esses dados são essenciais para o processo de monitoramento em tempo real do consumo energético, e ajudam a gerar relatórios mais precisos e personalizados.

Classe Relatório: A classe Relatório tem como objetivo gerar o relatório detalhado do consumo de energia. Quando o usuário solicita o relatório, a classe calcula o total de energia consumida e compara com a meta definida. Caso o consumo tenha ultrapassado a meta, a classe também gera algumas recomendações para ajudar o usuário a reduzir o consumo no futuro.

Classe Relatorio:
  Atributos:
    usuario
    consumo_total
    recomendacoes

  Métodos:
    função gerarRelatorio(usuario, consumo_total):
      this.usuario = usuario
      this.consumo_total = consumo_total
      calcularRecomendacoes()
      retornar "Relatório gerado com sucesso!"

    função calcularRecomendacoes():
      se this.consumo_total > usuario.metas_de_consumo:
        this.recomendacoes.adicionar("Reduzir o uso de energia à noite.")
      senão:
        this.recomendacoes.adicionar("Continue com seu bom uso de energia!")

O método gerarRelatorio cria esse relatório de forma automática, e a função calcularRecomendacoes analisa o consumo e dá sugestões de como o usuário pode melhorar sua eficiência energética.    



Classe Notificação: A classe Notificação envia alertas para os usuários sobre o seu consumo de energia. Quando o consumo ultrapassa o limite ou há algo importante a ser comunicado, essa classe se encarrega de notificar o usuário através do aplicativo ou via mensagens.

Classe Notificacao:
  Atributos:
    usuario
    mensagem

  Métodos:
    função enviarNotificacao(usuario, mensagem):
      this.usuario = usuario
      this.mensagem = mensagem
      exibirNotificacaoNoApp(usuario, mensagem)

    função exibirNotificacaoNoApp(usuario, mensagem):
      mostrarNaTela(usuario.nome, mensagem)

A função enviarNotificacao pega a mensagem e a envia ao usuário, e o método exibirNotificacaoNoApp mostra essa notificação diretamente na tela do celular ou computador do usuário.


# Estratégia de Escalabilidade para a Plataforma

Para garantir que a nossa plataforma consiga crescer e se adaptar conforme mais gente começa a usar, precisamos de uma estratégia de escalabilidade bem pensada. Isso envolve basicamente duas coisas: adicionar mais servidores (escalabilidade horizontal) ou melhorar o que já temos (escalabilidade vertical). Além disso, vamos usar cache para deixar tudo mais rápido e eficiente.

## 1. Escalabilidade Horizontal

Escalabilidade horizontal é quando a gente adiciona mais servidores ou containers para lidar com o aumento de usuários e dispositivos IoT. Como estamos usando cloud computing, a plataforma pode crescer automaticamente. Isso quer dizer que, conforme a demanda aumenta, podemos colocar mais instâncias de servidores em funcionamento, sem precisar mexer em todo o sistema manualmente. Com **Docker** e **Kubernetes**, conseguimos fazer isso de forma bem tranquila.

Com essa abordagem, o sistema consegue se adaptar conforme o número de pessoas aumenta sem que a performance sofra.

### Vantagens da Escalabilidade Horizontal:
- **Escalabilidade automática:** a plataforma cresce automaticamente quando a demanda aumenta.
- **Alta disponibilidade:** com mais servidores, a plataforma fica mais resiliente a falhas.
- **Gerenciamento eficiente:** Kubernetes ajuda a controlar o tráfego entre os servidores, sem a necessidade de intervir manualmente.

## 2. Escalabilidade Vertical

Agora, a escalabilidade vertical é quando a gente melhora o que já temos, ou seja, ao invés de adicionar mais servidores, a gente aumenta a capacidade dos servidores existentes, como aumentar a memória ou o poder de processamento. Isso também melhora o desempenho sem precisar mexer na infraestrutura como um todo.

No banco de dados, a escalabilidade vertical pode ser feita através do **sharding**, que divide o banco de dados em partes menores e distribui elas entre vários servidores. Isso ajuda a melhorar o desempenho sem precisar aumentar fisicamente o número de servidores.

### Vantagens da Escalabilidade Vertical:
- **Melhoria do desempenho individual:** ao melhorar os servidores já existentes, conseguimos lidar com mais usuários ou dispositivos.
- **Menos complexidade:** não precisamos gerenciar múltiplos servidores como na escalabilidade horizontal.
- **Uso mais eficiente dos recursos:** conseguimos otimizar o que já temos.

## 3. Uso de Cache

O uso de cache é super importante para deixar tudo mais rápido. Basicamente, em vez de buscar as mesmas informações no banco de dados o tempo todo, a gente guarda dados temporários em um local mais rápido, como a memória (RAM). Isso ajuda a diminuir a carga nos servidores e melhora o tempo de resposta do sistema, tornando a experiência do usuário muito mais ágil.

Com isso, ao acessar dados que são frequentemente requisitados, conseguimos buscar de maneira mais rápida, sem precisar ir ao banco de dados toda vez.

### Vantagens do Uso de Cache:
- **Reduz a carga no banco de dados:** ao guardar os dados em cache, o banco de dados não fica sobrecarregado.
- **Melhora a velocidade de resposta:** os dados podem ser acessados bem mais rápido.
- **Melhora a experiência do usuário:** com tempos de resposta mais rápidos, a navegação fica mais fluida.

## Considerações Finais

Juntando a **escalabilidade horizontal**, a **escalabilidade vertical** e o **uso de cache**, conseguimos uma plataforma que cresce de forma eficiente e sem perder a qualidade do serviço.

- A **escalabilidade horizontal** ajuda a plataforma a crescer conforme mais usuários entram, sem precisar parar tudo.
- A **escalabilidade vertical** melhora o desempenho dos servidores já existentes, sem adicionar mais servidores.
- O **uso de cache** deixa o sistema mais rápido, evitando que a plataforma fique lenta com tantas consultas ao banco de dados.

Essa estratégia é essencial para garantir que a plataforma cresça sem perder desempenho e continue a entregar uma boa experiência para os usuários.
