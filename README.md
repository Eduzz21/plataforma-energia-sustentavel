# Plataforma de Gerenciamento de Energia Sustentável

A Plataforma de Gerenciamento de Energia Sustentável tem como objetivo otimizar o consumo de energia em residências e empresas, promovendo práticas sustentáveis. O sistema coleta dados de dispositivos IoT, como medidores inteligentes, para gerar relatórios de consumo e sugestões de melhorias.

---

## Descrição Geral

O sistema será uma Plataforma de Gerenciamento de Energia Sustentável que permitirá monitorar, analisar e otimizar o consumo de energia elétrica em residências e empresas. Ele se integrará a dispositivos IoT, como medidores inteligentes, para coletar dados em tempo real e gerar relatórios detalhados.

O objetivo principal é fornecer ferramentas que promovam o uso eficiente de energia, reduzam desperdícios e incentivem práticas sustentáveis.

**Características principais do sistema**:

- **Monitoramento em tempo real**: Captura dados de consumo energético de dispositivos IoT conectados.
- **Relatórios personalizados**: Apresenta informações claras e acionáveis para os usuários.
- **Sistema de recomendação**: Sugere melhorias com base nos padrões de consumo detectados.
- **Definição de metas**: Usuários podem configurar objetivos para reduzir o uso de energia.
- **Alertas automatizados**: Envia notificações quando o consumo ultrapassa limites definidos.
- **Gestão de dispositivos IoT**: Permite adicionar, configurar e monitorar dispositivos conectados.

---

## 1. Requisitos Funcionais e Não Funcionais

### Funcionais

1. **Monitoramento em tempo real**: O sistema deve ser capaz de coletar e exibir dados de consumo energético de dispositivos IoT conectados (medidores inteligentes, sensores, etc.), atualizando essas informações em tempo real.
2. **Relatórios personalizados**: O sistema deve gerar relatórios detalhados, permitindo que o usuário visualize o consumo de energia de diferentes dispositivos e períodos, com gráficos e recomendações baseadas nos dados.
3. **Sistema de recomendação**: O sistema deve sugerir ações para reduzir o consumo de energia com base no histórico de uso e no comportamento do usuário, como "diminuir o uso da iluminação durante a noite" ou "substituir aparelhos ineficientes".
4. **Definição de metas**: Os usuários devem poder definir metas para reduzir o consumo de energia em determinado período (por exemplo, reduzir 10% de consumo nos próximos três meses).
5. **Alertas automatizados**: O sistema deve enviar notificações para os usuários quando o consumo ultrapassar limites predeterminados, ou quando houver picos de consumo anormais.
6. **Gestão de dispositivos IoT**: O sistema deve permitir que o usuário adicione, configure e monitore dispositivos conectados de forma simples e intuitiva, além de integrar-se facilmente com novos dispositivos.

### Não Funcionais

1. **Escalabilidade**: O sistema deve ser escalável para suportar o crescimento de dados e usuários, incluindo a capacidade de processar dados de múltiplos dispositivos IoT simultaneamente.
2. **Desempenho**: A plataforma deve responder rapidamente a requisições em tempo real, minimizando a latência ao coletar e processar dados dos dispositivos IoT.
3. **Segurança**: O sistema deve garantir a segurança dos dados, especialmente informações pessoais dos usuários e dados sensíveis de consumo. Será necessário criptografar as comunicações e garantir a conformidade com as leis de proteção de dados (como a LGPD).
4. **Manutenibilidade**: A arquitetura deve ser modular e bem documentada, permitindo a fácil manutenção e expansão, caso novos dispositivos IoT ou funcionalidades precisem ser integrados no futuro.

---

## 2.2. Escolha da Arquitetura

A arquitetura de microserviços foi escolhida para a plataforma de gerenciamento de energia sustentável devido à sua escalabilidade, flexibilidade e facilidade de manutenção. Cada serviço independente permite que partes do sistema sejam escaladas conforme a demanda, sem precisar expandir toda a infraestrutura. Isso é crucial para integrar novos dispositivos IoT e lidar com o crescimento do número de usuários. Além disso, a arquitetura facilita a manutenção e evolução do sistema, pois atualizações podem ser feitas sem interromper o funcionamento geral. Também oferece segurança aprimorada, permitindo controles de acesso independentes para cada serviço. Em resumo, essa arquitetura atende bem às necessidades de escalabilidade, integração com IoT e serviços em nuvem, e garante um sistema seguro e fácil de evoluir.

---

## 3. Diagramas

### Diagrama de Componentes

O Diagrama de Componentes mostra como as partes principais do sistema estão conectadas. Nele, temos o Frontend, que é o que o usuário vê e usa para interagir com a plataforma. Ele se comunica com o Backend, que é a parte que processa e gerencia os dados. O Backend acessa os Dispositivos IoT, como medidores inteligentes, para pegar os dados de consumo em tempo real e também consulta o Banco de Dados para buscar o histórico de consumo. Se necessário, o Backend envia notificações ao Usuário e gera relatórios de consumo.

![Diagrama de Componentes](diagrama_de_componentes.png)

### Diagrama de Sequência

No Diagrama de Sequência, vemos como as ações acontecem em ordem. O Usuário começa acessando o Frontend, que manda uma requisição para o Backend. O Backend, por sua vez, pede os dados de consumo dos Dispositivos IoT e também verifica o histórico no Banco de Dados. Se o consumo ultrapassar o limite definido, o Backend envia um alerta, que é notificado ao Usuário. Este diagrama mostra claramente o passo a passo do processo de consulta e notificação.

![Diagrama de Sequência](diagrama_de_sequencia.png)

### Diagrama de Classes

O Diagrama de Classes ilustra as principais entidades do sistema e como elas se relacionam. O Usuário pode acessar o consumo de energia, visualizar relatórios e ser notificado sobre excessos. O Consumo é calculado com base nos dados dos Dispositivos IoT, e os relatórios são gerados com informações do histórico de consumo. Caso o consumo ultrapasse os limites definidos, uma Notificação é enviada ao Usuário.

![Diagrama de Classes](diagrama_de_classes.png)

Esses diagramas ajudam a entender como o sistema funciona, desde a interação do usuário até a coleta e o processamento dos dados, e como as notificações são enviadas quando necessário.

---

## 4. Detalhamento das Classes

### Classe Usuário

Essa classe é responsável por gerenciar as informações do usuário, como nome, e-mail e as metas que ele define para controlar o consumo de energia. Ela também envia alertas quando o consumo ultrapassa os limites definidos.

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

### Classe Consumo

A classe **Consumo** cuida do registro do consumo de energia. Ela recebe os dados de consumo e verifica se o valor registrado excede o limite da meta definida. Se isso acontecer, a classe envia um alerta.

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

### Classe DispositivoIoT

Como o sistema vai estar integrado com dispositivos de medição inteligente (como medidores de energia conectados via IoT), essa classe gerencia esses dispositivos. Ela é responsável por registrar o dispositivo e também medir o consumo de energia em tempo real.

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

### Classe Relatório

A classe **Relatório** tem como objetivo gerar o relatório detalhado do consumo de energia. Quando o usuário solicita o relatório, a classe calcula o total de energia consumida e compara com a meta definida. Caso o consumo tenha ultrapassado a meta, a classe também gera algumas recomendações para ajudar o usuário a reduzir o consumo no futuro.

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
        adicionarRecomendacao("Reduzir o uso de aparelhos de ar condicionado.")
      se this.consumo_total < usuario.metas_de_consumo:
        adicionarRecomendacao("Ótimo! Continue com o consumo consciente.")

---

## 5. Conclusão

A plataforma foi projetada para fornecer uma solução completa de gerenciamento de energia, com um foco em sustentabilidade e eficiência. Através do monitoramento em tempo real e relatórios detalhados, os usuários podem tomar decisões mais informadas sobre o uso de energia, implementar melhorias, e reduzir desperdícios. A arquitetura modular e a escalabilidade da solução garantem que o sistema possa evoluir conforme novas tecnologias e dispositivos IoT sejam incorporados ao ecossistema.
