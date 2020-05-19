# Módulo 5 - Segurança

## Introdução

* Mantenha dados seguros:
  * Infra resiliente
  * Alta Segurança
  * Proteções fortes

* Melhoria contínua
  * Inovação rápida
  * Serviços de segurança em constante evolução

* Pague pelo que precisar
  * Serviços avançados de Segurança
  * Resolva riscos emergentes em tempo real
  * Atendimento às necessidade a um custo operacional mais baixo

* Recursos voltados para governança
  * Supervisão adicional
  * controle de segurança
  * automação centralizada

* Herde controles de segurança
* Ponha em camadas os seus controles

## Ferramentas
* Firewalls integrados
* criptografia em trânsito
* conexções privadas/dedicadas
* mitigação de negação de serviço distribuída (DDoS)

* Ferramentas de implantação
* Ferramentas de inventário e configuração
* Ferramentas de definição e gerenciamento de modelos
### Caractéristicas
* Critografia de dados
  * Recursos de criptografia
  * Opções de gerenciamento de chaves
    * AWS KMS
  * Opções de armazenamento de chaves criptográficas baseadas em hardware
    * AWS CloudHSM

* Controle e gerenciamento de acesso
  * Identifu and Access Management (IAM)
  * Multi-factor Authentication (MFA)
  * Integração e federação com diretórios corporativos
  * Amazon Congnito
  * AWS SSO

* Monitoramento e registros em log
  * Visibilidade detalhada das chamadas de API
  * Agregação de logs e opções
  * Notificação de alerta

## Modelo de Responsabilidade Compartilhada
* A AWS acredita que a segurança é definida em uma pilha, onde o usuário terá sua parcela de responsabilidade enquanto a AWS terá outra parcela de responsabilidade
* Pilha de segurança:
  6. User Data <-- Usuário
  5. Application <-- Usuário
  4. Guest OS <-- Usuário (a AWS não consegue ver essa informação)
  3. Hypervisor <-- Zen based Hypervisor
  2. Network <-- AWS (https://aws.amazon.com/compliance)
  1. Physical <-- AWS

## Identity and Access Management

* User --> Credenciais (user/login, key/secret) --> método de autenticação nominal (pra máquina/application ou usuário)
* Group --> Conjunto de usuários (users)
* Role --> Role não são suas permissões --> Role é um método de autenticação --> São 'temporárias'
* Policy Docs --> Arquivo JSON onde as permissões estão alocadas. Elas podem pertencer a um User, Group ou Role

* Explicit Deny: Substitui qualquer instrução de permissão aplicada nos Policy DOCs apontando pra alguem (Ex: Ninguem pode deletar instâncias de RDS)

* Cloud Trail: Registro de tudo que é feito na AWS pelos usuários/grupos/roles

## Amazon Inspector
* Avalia aplicatvos para:
  * Vulbenrabilidades
  * desvios das melhores práticas
* Produz em relatório detalhado com:
  * Descobertas de seguranças
  * Etapas priorizadas para correção

* É importante lembrar que a AWS não garante que seguir todas as recomendações do AWS Inspector vá resolver todos os problemas de segurança. Porque tem muita coisa que depende da configuração que o usuário fez.

* Regras integradas
  * Inclui uma base de conhecimento com centenas de regras que são mapeadas para:
    * Padrões comuns de segurança e conformidade
    * definições de vulnerabilidade
  * Atualizadas regularmente pleos pesquisadores de segurança da AWS

## AWS Shield
* Serviço gerenciado de proteção contra DDOS que protege aplicativos na AWS

* DoS x DDoS:
  * Negação de serviço (DoS): tentativa deliberada de tornar seu site ou aplicativo indisponivel para os usuários (fonte de ataque unica)
  * Ataques distribuídos de negação de serviço: Váris origens são usadas para o destino, camadas de infraestrutura e aplicativos podem ser afetadas

* Ataque na camada de Aplicativos DDoS
  * O hacker tenta derrubar o site usando a forma que um site se comunica com outro site. Ou seja, pela camada de aplicação
  * As camadas de aplicação normalmente não tem um volume muito grande tráfego, então um ataque com poucas requisiçoes nessa camada ja pode comprometer o funcionamento do site
  * Os clientes usam firewalls de aplicativos web (ou WAFs) para bloquear essas solicitações

* Desafios de mitigação de DDoS
  * Configuração e implementação complexas
  * Limitações de largura de banda
  * Intervenção manuial
  * Demorada
  * Cara

### Característica
* Duas opções de proteção no Shield
* Standard: Proteções automaticas disponiveis para todos os clientes da AWS sem custo adicional
  * Proteção automática (qualquer recurso em qualquer região)
  * Detecção rápida (sempre ativa)
  * mitigação de ataques em linha (técnicas de mitigação integradas automatizadas, evita o impacto da latência)
  * autoendimento (não há necessidade de envolver o AWS support)

* Advanced: Serviço pago para níveis mais altos de proteção, recursos e beneficios
  * Suporte especializado
  * Mitigação avanças de ataques
  * Visibilidade e notificação de ataques
  * Monitoramento sempre ativo (Route 53, CloudFront, ELB, Elastic IP)
  * Detecção aprimorada
  * Proteção contra custo de DDoS

### Beneficios:
* Economico
* Integração e implantação sem interrupções
* Proteção personalizável


## Segurança e Conformidade (Compliance)
* Responsabilidade compartilhada e controle (responsabilidades da AWS + responsabilidade do usuário)
* Recursos de compliances:
  * certificações/declarações
  * suporte jurídico/normativo
  * alinhamentos/estruturas

* Programa de conformidade e gerenciamento de riscos da AWS
  * Ajuda os clientes a:
    * Documentar uma estrutura completa de controle e governança
    * Implantar soluções que atendam a vários padrões especificos do setor

* A abordagem de compliance da AWS inclui 3 recursos:
  * Gerenciamento de riscos
    * A AWS regularmente varre a infra de todo mundo pra procurar por falhas e avisar os clientes
  * Controle de acesso ao ambiente
    * Inclui políticas, processos e atividades de controle apra proteger a entrega de ofertas de produtos da AWS
    * Oferece suporte à eficácia operacional da estrutura de controle da AWS
    * Integra controles específicos da nuvem
    * Aplica as melhores práticas do setor
  * Segurança da informação
    * Projeto par aproteger
      * Confidencialidade
      * Integridade
      * Disponibilidade
    * Publica o whitepaper de segurança

  * Os programas de compliance de segurança da AWS ajudam os clientes a:
    * compreender controles robustos implementados
    * estabelecer e operar em um ambiente de controle de segurança da AWS


## Referências
- [AWS Segurança na Nuvem](https://aws.amazon.com/pt/security/)
- [Modelo de Responsabilidade Compartilhada](https://aws.amazon.com/pt/compliance/shared-responsibility-model/)
- [Identity and Access Management](https://aws.amazon.com/pt/iam/)
- [Amazon Inspector](https://aws.amazon.com/pt/inspector/)
- [AWS Shield](https://aws.amazon.com/pt/shield/)
- [Amazon Compliance](https://aws.amazon.com/pt/compliance/)
