# Módulo 2 - Serviços Principais

## EC2 - Elastic Compute Cloud
É um web service que disponibiliza capacidade computacional segura e redimensionável na nuvem. Ele foi projetado para facilitar a computação em nuvem na escala da web para os desenvolvedores. Servicdor de aplicatos / web / bancos de dados / jogos e-mail / mídia / catáçogo / arquivos / etc. Paga somente o tempo que está ativa.

### Como criar (no console da AWS)
* Faça login no console da AWS
* Escolha região
* Assistente execução da EC2 (Launch Instanc )
* Escolher Amazon Machine Image (AMI): Refere-se ao OS da máquina
* Escolher o tipo de Instância
* Configurações técnicas (número de instancias, network)
* Escolher o tamanho de disco (Add storage)
* Adicionar tags
* Adicionar Security group (Firewall Rules)

## EBS - Elastic Block Store
Os volumes EBS podem ser usados como uma unidade de armazenamento para sua instância EC2. Paga conforme o uso.

### Caracteristicas
  * Escolha entre tipos de HDD e SSD
  * Armazenamento em bloco persistente e personalizável para instâncias do EC2
  * Replicado na mesma zona de disponilidade
  * Backup usando snapshots
  * Volumes elásticos
  * Criptografia Fácil e transparente

### Como criar (no console da AWS)
  * Acessar EC2
  * Acessar Elastic Block Store (barra da esquerda) --> Volumes
  * Create Volume
  * Escolher região (Precisa criar a nova instância de EBS na mesma região que seu EC2)
  * Escolher o Volume Type (SSD, Magnetic, etc)
  * Tamanho
  * Create volume
  * Clicar em Attach Volume (se voce quiser integrar esse voluma com alguma EC2)

## S3
Serviço de armazenamento de objetos que oferece escalabilidade líder do setor, disponibilidade de dados, segurança e performance

### Características
  * Serviço gerenciado de armazenamento na nuvem
  * Armazene um número praticamente ilimitado de objetos
  * Acesse a qualquer momento, de qualquer lugar
  * Controle avançados de segurança
  * Aguenta alto volume de chamadas
  * Bucket: onde se guarda os dados
    * Quando você armazena algo dentro do bucket você precisa passar uma chave (key), que é uma string que vai te ajudar a recuperar o objeto posteriormente

###  Use Cases
  * amarzenamento de ativos de aplicativos
  * hospedagem na web de sites estáticos
  * recuperação de desastres e Backup
  * área de preparação para big data

## Amazon Virtual Private Cloud (VPC)
Uma rede vritual privada na Nuvem AWS (usa os mesmos conceitos que as redes locais). Permite controle completo de configuração de rede (capacide de isolar e expor recursos dentro da VPC). Oferece várias camadas de controles de segurança (capacidade de permitir e negar tráfego interno e específico da Internet)
  * Outros produtos da AWS implantam a VPC (serviços de segurança inerente a rede)

### Features:
  * Criação com base na alta disponibilidades das regiões e zonas de disponibilidades (AZ) da AWS
    * Amazon VPC reside em uma região
    * Várias VPCS por contas
  * Sub-redes
    * Usadas para dividir a Amazon VPC
    * Podem se comunicar entre si
    * Permite que a Amazon VPC abranja várias AZs
    * Públicas/Privadas
  * Tabelas de Rotas
    * Controlar o tráfego que sai das sub-redes
  * Gateway de internet (IGW)
    * Permite acesso à internet por meio da Amazon VPC
  * NAT Gateway
    * Permite que recursos de sub-rede privada acessem a Internet
  * Listas de controle de acesso de rede (NACL)
    * Controlar o acesso a sub-redes, sem estado

  * Security Groups
    * Agem como firewalls integrados
    * Controlam a acessibilidade a instâncias
    * provisionam firewalls virtuais
    * Controla o acesso à instancias por meio de regras


## Referências:
- [Amazon EC2](https://aws.amazon.com/pt/ec2)
- [Amazon EBS](https://aws.amazon.com/pt/ebs/)
- [Amazon S3](https://aws.amazon.com/pt/s3/)
- [Amazon VPC](https://aws.amazon.com/pt/vpc/)
