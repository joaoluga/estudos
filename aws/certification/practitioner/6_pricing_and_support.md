# Módulo 6 - Pricing and Support

## Conceitos básicos da definição de preço
### Pricing

**Pay-as-you-go**: Só paga pelo o que você usar na AWS, pelo tempo que usar. A definição de preço com pagamento conforme o uso permite que você se adapte facilmente às necessidades empresariais dinâmicas sem sobrecarregar orçamentos, melhorando sua capacidade de resposta às mudanças.

**Reserved capacity**: Possibilidade de reduzir custos em até 75%. Porém, somente alguns serviços oferecem essa opção como o EC2 e RDS por exemplo.

Existem 3 opções:
1. All-UpFront: Tudo adiantado (AURI)
2. Partial-UpFront: Parcialmente adiantado (PURI)
3. No-UpFront: Nenhum adiantamento (NURI)

Quanto mais você pagar pela reserva das instâncias, maior o desconto.

## Detalhes de definição de preço
### Conceitos básicos de custos da AWS

Pague por:
  * Capacidade computacional
  * Armazenamento
  * Transferência de dados de saída (Agregada)

Não há cobrança para:
  * Transferência de dados de entrada
  * Nem para dados que são transferidos entre recursos da AWS na mesma região

### Definição de preço de serviços para ofertas da AWS
#### Amazon EC2
Cobrança apenas pela capacidade usadas.
* **Fatores de custos**
  * **Faturamento por segundo/hora**: geram cobranças somente quando estão em execução
  * **Configuração da instância**:
    * Capacidade física da instância
    * A definição de preço varia de acordo com:
      * Região da AWS
      * SO
      * Tipo de instância
      * Tamanho da instância
* **Tipos de compra**
  * Instâncias sob demanda
  * Instâncias reservadas
  * Instẫncias spot
* **Outras considerações**
  * Load-Balancing:
    * Usar o ELB vai gerar um custo adicional:
      * Horas de execução do load balancer
      * quantidade de dados processados pelo ELB (GBs)
* **Serviços disponíveis sem custo adicional**:
  * CloudWatch
  * Auto-Scaling
  * Elastic IP

#### Amazon S3
Cobrança apenas pelo tipo de armazenamento (padrão ou standard/acesso infrequente/S3-IA) e o número e tamanho dos objetos. Os fatores de custo são:
* Base de definição de preço em:
  * Solicitações/Requests
    * Número de solicitações
    * Tipo de solicitações - taxas diferentes para solicitações GET
  * Transferência de dados
    * Quantidade de dados transferidos para fora da região do Amazon S3


#### Amazon EBS
Os preços do amazon EBS vão váriar a partir dos tipos de volume selecionados, que são 3: a) Uso Geral (SSD); b) IOPS provisionados (SSD); c) Magnético. Os fatores de custo são:
* Volumes: todos os tipos cobrados pela quantidade provisionada por mês
* IOPS:
  * Uso geral (SSD): incluído no preço
  * Magnético: cobrado pelo número de solicitações
  * IOPS provisionados (SSD): cobrados pela quantidade provisionada em IOPS
* Snapshots: custo adicional por GB-mês de dados armazenados
* Transferência de dados:
  * Transferência de dados de entrada não tem cobrança
  * Faixas de cobrança para transferência de dados de saída

#### Amazon RDS
Fornece capacidade econômica e redimensionável enquanto gerencia tarefas demoradas de administração de bancos de dados. Os fatores de custo são:
* Faturamento por hora: os recursos incorrem em cobranças durante a execuão
* Características do banco de daos: modelo, tamanho e classe de memória afetam o custo
* Tipo de compra de banco de dados:
  * As instâncias de banco de dados sob demanda são cobradas por hora
  * Instâncias de banco de daods reservadas exigem pagamento adiantado para instâncias de banco de dados reservadas
  * Provisione várias instâncias de banco de daos para lidar com picos de carga
* Armazenamento provisionado:
  * Gratuito para armazenamento de backup de até 100% do armazenamento de banco de dados
  * Armazenamento de backup para instâncias de banco de dados encerradas cobrando a GB/mês
* Armazenamento adicional: armazenamento de backup além do armazenamento provisionado cobrado a GB/mês
* Tipo de implantação:
  * Cobranças de Armazenamento de e I/O
  * Única Zona de Disponibilidade
  * Múltiplas Zonas de Disponibilidade
* Transferência de daodos:
  * Não há cobrança pela transferência de dados de entrada
  * Cobranças em faixas para transferência de dados de saída


#### Amazon CloudFront
Web-service para entrega de conteúdo. A definição de preço vária entre regiões geográficas com base em: a) solicitações; b) transferência de dados para fora


## AWS Trusted Advisor
Oferece melhores práticas e verifica todos os recursos em sua conta para ver se eles estão de acordo com as melhores práticas da AWS em quatro categorias principais:
* Otimização de custos
* Performance
* Segurança
* Tolerância a falhas

* Adicional:
  * É integrado com o CloudWatch


## Planos do AWS Support
Force uma combinação única de ferramentas/especialização:
  * AWS Support
  * Planos do AWS Support

### AWS Support
Suporte é fornecido para: a) testar com a AWS; b) usar a AWS em produção; c) usar essencialmente para os negócios da AWS. Se um usuário quiser orientação proativa, existe um Gerente técnico de conta (TAM) que pode atendê-lo. Para ter acesso a melhores práticas de forma automatizada, a AWS oferece o AWS Trusted Advisor. E assistência à conta com o AWS Support Concierge. O Support Concierge será um especialista em faturamento e contas que fornecerá uma análise rápida e eficiente sobre o problema. Esse especialista aborda todas as dúvidas não ténicas de faturamento e contas.

### Planos de Suporte
O AWS Support oferece quatro planos de suporte:
* Basic Support
* Developer Support
* Business Support
* Enterprise SUpport


## Referências
- [Amazon Pricing](https://aws.amazon.com/pt/pricing/)
- [Amazon EC2](https://aws.amazon.com/pt/ec2/)
- [Amazon S3](https://aws.amazon.com/pt/s3/)
- [Amazon EBS](https://aws.amazon.com/pt/ebs/)
- [Amazon RDS](https://aws.amazon.com/pt/rds/)
- [Amazon CloudFront](https://aws.amazon.com/pt/cloudfront/)
- [Amazon Trusted Advisor](https://aws.amazon.com/pt/premiumsupport/technology/trusted-advisor/)
- [Amazon Support Plans](https://aws.amazon.com/pt/premiumsupport/plans/)
