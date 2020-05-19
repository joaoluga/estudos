# Módulo 3 - Serviços Integrados

## Elastic Load Balancer
O Elastic Load Balancing distribui automaticamente o tráfego de entrada de aplicativos entre diversos destinos, como instâncias do Amazon EC2, contêineres, endereços IP e funções Lambda. O serviço pode lidar com a carga variável de tráfego dos aplicativos em uma única zona de disponibilidade ou em diversas zonas de disponibilidade.

### Características
* Application Load Balancer:
  * O segunto tipo Load Balancer introduzido como parte do serviço Elastic Load Balancer
  * Tem as mesmas features do Classic Load Balancer
  * Features extras:
    * protocolos de solicitação adicionais compatíveis (HTTP, HTTPS, HTTP/2 e web sockects)
    * métricas e logs de acesso
    * verificações de integridade
    * cloudwatch
  * ipv6 native support
  * portas dinâmicas
  * baseado em caminho e host (roteamento)

### Quando usar
* Capacidade de usar containers para hospedar seus microserviços e rotear para esses aplicativos de um unico LB
* Pode rotear requests diferentes para a mesma instância porém diferencia o caminho com base na porta (pode criar regras para onde esse tráfego vai ser distribuído)

### Conceitos:
  * ouvintes: processo que verifica solicitações de conexão, usando o protocolo e a porta que você configurar (quem armazena a regra)
  * destino: um destino é a uma destinação para o tráfego com base nas regras do ouvinte estabelecidas
  * grupo de destino: roteia soliticatações para um ou mais destinos registrados usando o protocolo e o número da porta especificade


## Infraestrutura da global da AWS

### Regiões AWS (Regions)
Áreas geográficas que tem uma ou mais zonas de disponibilidade (é importante escolher uma região especifica por conta de custos, latência e/ou requisitos normativos). Nem todos os serviços da AWS são disponíveis em todas as localidades.

### Zonas de disponilidade (Availability Zones)
São um conjunto de Data Centers (fisicamente isoladas mas conectadas por internet de baixa latência). São tolerantes a falhas (Se uma zona cai, as outras continuam a se comunicar de forma independente).

### Pontos de Presença (Edge Locations)
Infraestruturas da AWS enxutas, que rodam alguns poucos serviços com o objetivo de melhorar a experiência dos usuários
Route53, CloudFront, por exemplo


## Auto-Scaling
O Auto Scaling ajuda a garantir que você tenha o número correto de instâncias do EC2 disponíveis para processas a carga dos aplicativos. É essencial monitorar a performance das suas instâncias com o Cloudwatch, mas o Cloudwatch não adiciona ou remove instâncias. O auto scaling faz isso. É ideal para cenários de demanda de recursos flutuante

### Perguntas críticas:
Como posso garantir que minha carga de trabalho tenha recursos suficientes do EC2 para atender a requisitos flutuantes de performance?
  * R: Escalabilidade. Expandir ou reduzir escala. Você pode definir isso através do uso da instâcia, horário, dia, etc.
  * Como posso automatizar o provisionamento de recursos do EC2 para que ocorra sob demanda?
    * R: Automação

### O que é necessário para utilizar o Auto-Scaling?
  * Configuração de execução
    * AMI - Amazon Image
    * Tipo de instância
    * Grupo de segurança
    * Funções
  * Grupo de Auto Scaling (Auto-Scaling Group)
    * VPC e sub-redes
    * Load balancer
    * Minímo de instâncias
    * Máximo de instâncias
    * Capacidade desejada
  * Política de Auto-Scaling
    * Programado (dia especifico)
    * Sob demanda (condição de performance especifica)
    * Política de expansão
    * Política de redução
  * Como o auto-scaling é disparado: CloudWatch


## Amazon Route 53
  * É uma sistema de dominio ou DNS que é projetado para rotear usuários finais para endpoints
  * DNS é uma tradução do IP do servidor
  * Os serviços de privacidade também são opção com Amaozon Route 53 permitindo ocultar parcial ou totalmente suas infoemações de banco de dados
  * Zonas hospedadas: conterá conjuntos de registros que são as conversões de DNS que vocÊ deseja executar para um dominio especifico
  * Pode registrar EC2, load balancers, serviço local no seu proprio datacenter

  * Os serviços do Route53 vão além de somente de criar um DNS, também ferece várias outras estratégias de resolução, todas elas usando uma rede global de servidores de DNS em todo o mundo. Isso ajuda a reduzir a distância entre sua resolução de DNS e seus clientes. Então quando eles fazem tentam acessar seu serviço, a chamada é automaticamente roteada para o servidor de DNS mais próximo que reside em uma das muitas AWS Edge Location

### Resumo:
  * Registro de dominio
  * DNS global e altamente disponivel
  * Nomes DNS publicos e privados
  * vários algoritmos de roteamento
  * Tanto IPV4 quando IPV6
  * Integrados a outros serviços de numve AWS


## Amazon Relational Databases
Facilita a configuração, a operação e a escalabilidade de bancos de dados relacionais na nuvem.

* Com o RDS você gerencia somente a otimização de aplicativos
* A AWS gerencia para você no RDS:
  * Instalação e patches do SO
  * Instalação e patches de software de banco de dados
  * Backups de banco de dados
  * Alta disponibilidade
  * Escala
  * Energização e organização em racks
  * Manutenção do servidor
* Altamente escalável
* Alta performance
* Fácil de administrar
* Disponível e durável
* Seguro e compativel

## AWS Lambda
O AWS Lambda permite que você execute código sem provisionar ou gerenciar servidores. Você paga apenas pelo tempo de computação consumido.

  * Serviço da AWS que permite executar códigos sem provisonar ou gerenciar servidores
  * Computação sem servidor totalmente gerenciada
  * Execução orientada a eventos
  * Medição de frações de segundos
  * Várias linguágens compatíveis
  * Escalabilidade contínua
  * Paga somente o tempo que usar
  * AWS Code Pipeline e AWS Code Deploy são serviços integrados que ajudam a fazer o deploy do código


## Amazon Beanstalk
Você pode implantar e gerenciar rapidamente aplicativos na Nuvem AWS sem se preocupar com a infraestrutura que executa esses aplicativos.

  * Plataform as a Service (PaaS)
  * Permite a implantação rápida de seus aplicativos
  * Reduz a complixadade do gerenciamento da sua plataforma
  * Mantém o controle em suas mãos
    * Escolha seu tipo de instancia
    * Escolha seu banco de dados
    * Defina e ajuste o Auto Scaling
    * Atualize seu aplicativo
    * Acesse arquivos de log do servidor
    * Habilite HTTPS no load balancer
  * Oferece suporte a uma grande variedade de plataformas
  * Implementação fácil
    * Seu Código
    * Serviço de aplicativo
    * Serviço HTTP
    * Sistema operacional
    * Interpretador da linguagem
    * Host


## Amazon Simple Notification Service (SNS)
É um serviço de envio de mensagens de publicação/assinatura totalmente gerenciado, altamente disponível, seguro e durável que permite o desacoplamento de microsserviços, sistemas distribuídos e aplicativos sem servidor.

  * Serviço de mensagens e comunicações móveis de publicação/assinatura flexível e totalmente gerenciado
  * Coordena a entrega de mensagens para endpoints e clientes assinantes
  * Fácil de configurar, operar e enviar comunicações confiáveis
  * Desacople e ajuste a escala de microserviços, sistemas distribuídos e aplicativos serverless


## AWS CloudWatch
Amazon CloudWatch monitora seus recursos da AWS e os aplicativos que você executa em tempo real

  * Features:
    * Coleta e monitora métricas
    * Coleta e monitora logs
    * Define alertas
      * Reaja automaticamente a alterações
  * Executa uma ou mais ações
  * Ação que pode ser tomada:
    * Uma ação do Amazon EC2 (interromper, encerrar, reinicializar ou recuperar uma instância do Amazon EC2)
    * Uma ação de Auto Scaling (reduzir ou expandir um grupo de Auto Scaling)
    * Uma notificação enviada para um tópico do Amazon SNS
  * As métricas podem ser armazenadas de forma durável no CloudWatch com CloudWatch Logs


## AWS CloudFront
  * Infraestrutura global da AWS
  * Rede global de mais de 80 locais e mais de 10 pontos de presença de caches regionais para entrega de conteúdo.
  * Os pontos de presença estão espalhados pelo mundo tudo e essas localizações não param de aumentar
  * Entrega conteúdo permitindo que os usuários interajam com suas aplicações em baixa latência
  * Portanto, o CloudFront é uma rede de entrega de conteúdo (CDN)
  * Forte integração com os principais produtos da AWS
  * Economico
  * Facil de usar

## AWS Cloud Formation
  * É um 'terraform' da AWS
  * Simplifica a tarefa de criar de forma repetida previsiível grupos de recursos relacionados que pontencializam seus aplicativos
  * Serviço totalmente gerenciado
  * Criar, atualizar e excluir recursos em pilhas
  * Recursos a serem provisionados
    * arquivo de texto
    * formato JSON ou YAML
    * Ambiente de autodocumentação
  * É um terraform da AWS
  * requisitos
    * permissões
    * modelo

## Referências
- (Amazon ELB)[https://aws.amazon.com/pt/elasticloadbalancing/]
- (AWS Global Infrastructure)[aws.amazon.com/about-aws/global-infrasctructure]
- (Amazon Auto-Scaling)[https://aws.amazon.com/pt/autoscaling/]
- (Amazon RDS)[https://aws.amazon.com/pt/rds/]
- (Amazon Beanstalk)[https://docs.aws.amazon.com/elastic-beanstalk/index.html]
- (Amazon Lambda)[https://aws.amazon.com/pt/lambda/]
- (Amazon SNS)[https://aws.amazon.com/pt/sns/]
- (Amazon CloudWatch)[https://aws.amazon.com/pt/cloudwatch/]
- (Amazon CloudFront)[https://aws.amazon.com/pt/cloudfront/]
- (Amazon CloudFormation)[https://aws.amazon.com/pt/cloudformation/]
