# Módulo 4 - Arquitetura da AWS

## AWS Well Architected Framework
O Well-Architected Framework foi desenvolvido para ajudar os arquitetos de nuvem a criar uma infraestrutura com os mais altos níveis de segurança, performance, resiliência e eficiência possíveis para seus aplicativos. Baseado em cinco pilares, excelência operacional, segurança, confiabilidade, eficiência de performance e otimização de custos, o Framework fornece uma abordagem consistente para que clientes e parceiros avaliem arquiteturas e implementem designs que serão escalados ao longo do tempo.

### Segurança
O pilar da segurança inclui diz respeito sobre a habilidade de proteger a informação, sistemas e ativos enquanto entrega valor para o negócio através de avaliações de risco e estratégias de mitigação.  

#### Caracteristicas:
  * Identity and access management (IAM) --> quem acessa e como acessa
  * Controles de detecção (CloudWatch)
  * Proteção de infraestrutura (proteção contra acesso não intencional e não autorizado)
  * Proteção de dados -> Várias abordagens: classificação de dados, criptografia, backup, replicação e recuperação
  * Respota a incidentes -> Processo de resposta para responder e mitigar possíveis incidentes de segurança

#### Princípios de design:
* Implementar uma base sólida de identidade
* Habilitar rastreabilidade
* Aplicar segurança em todas as camadas
* Automatizar as melhores práticas de segurança
* Proteger os dados em trânsito e estáticos
* Se preparar para eventos de segurança/ataques


### Confiabilidade
O pilar de confiabilidade inclui a capacidade de um sistema se recuperar de interrupções de infraestrutura ou serviço, adquirir dinamicamente recursos de computação para atender à demanda e atenuar interrupções, como configurações incorretas ou problemas transitórios de rede.

#### Características
  * Recuperar problemas/falhas
  * Aplicar as melhores práticas nos:
    * fundamentos
    * gerenciamento de alterações
    * gerenciamento de falhas
  * Previsão, resposta e prevenção de falhas

#### Princípios de design:
* Testes de procedimentos de recuperação
* Recuperar-se automaticamente de uma falha
* Escale horizontalmente para aumentar a disponibilidade
agregada do sistema
* Pare de adivinhar a capacidade
* Gerenciar alterações na automação


### Eficiência de performance
O pilar de eficiência de desempenho inclui a capacidade de usar recursos de computação com eficiência para atender aos requisitos do sistema e manter essa eficiência à medida que a demanda muda e as tecnologias evoluem

#### Características
* Selecionar soluções personalizaveis
* Revisar para inovar continuamente
* Monitorar produtos da AWS
* Considerar as vantagens

#### Princípios de design
* Democratize tecnologias avançadas
* Seja global em minutos
* Use arquiteturas serveless
* Experimente mais frequentemente
* “Mechanical sympathy”

### Otimização de custos
O pilar de otimização de custos inclui a capacidade de evitar ou eliminar custos desnecessários ou recursos abaixo do ideal.

#### Característica
* Usar recursos ecnômicos
* Combinar oferta e demanda
* Autmentar a conscientização sobre despesas
* Otimizar ao longo do tempo

#### Princípios de Design
* Adotar um modelo de consumo
* Meça a eficiência geral
* Pare de gastar dinheiro em operações de data center
* Analisar e atribuir despesas
* Use serviços gerenciados para reduzir o custo de propriedade


### Excelência operacional
O pilar de excelência operacional inclui a capacidade de executar e monitorar sistemas para agregar valor aos negócios e melhorar continuamente os processos e procedimentos de suporte.

#### Características
* Gerenciar e automatizar alterações
* Responder a eventos
* Definir padrões

#### Princípios de design
* Usar Infra-as-code (IaC)
* Criar documentação
* Fazer frequentemente alterações pequenas e reversíveis
* Refinar procedimentos operacionais frequentemente
* Antecipar falhas
* Tirar aprendizados das falhas operacionais


## Arquitetura de referência - Tolerância a falhas e alta disponibildiade

### Tolerância a falhas
  * Capacidade de um sistema permanecer operacional
  * redundância integrada do componente de um aplicativo

  * Ferramentas tolerantes a falhas
      * Amazon Simple Queue Services
      * Amazon Simple Storage Services
      * Amazon Relational Database Service

### Alta disponibilidade

* Garante que:
  * Os sistemas estejam funcionando e acessíveis de um modo geral
  * O tempo de inatividade seja minizado
  * Haja necessidade mínima de intervenção humanda
  * investimento financeiro inicial mínimo

  * Alta disponibilidade:  Local x AWS
    * Tradicional (Local)
      * somente aplicativos críticos
      * caro
    * AWS
      * vários servidores
      * Zonas de disponibilidade
      * Regiões
      * Serviços tolerantes a falhas

  * Ferramentas de serviço de alta disponibilidade
    * Elastic Load Balancers (distribui o tráfego de entrada (cargas) / envia métricas pro cloudwatch / desencadeia e notifica)
    * Endereços IP elásticos (são endereços IP estáticos, falhas de mascará, continuará a acessar aplicativos se uma instância falhar)
    * Amazon Route 53 (roteamento simples, roteamento baseado em latência, verificações de integridade, failovers de DNS, roteamento por localização geográfica)
    * Auto Scaling (encerra e executa instâncias, cria novos recursos sob demanda)
    * Amazon CloudWatch (sistema de coleta de estatísticas distribuídas, criar métricas personalizadas)



## Referências
- [Amazon CloudWatch](https://aws.amazon.com/pt/cloudwatch/)
- [Amazon Well Archtected Framework](https://aws.amazon.com/pt/architecture/well-architected/)
- [Hospedagem na web](aws.amazon.com/websites/)
