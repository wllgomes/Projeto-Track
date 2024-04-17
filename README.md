# Arquitetura e Monitoramento

  # Arquitetura
  
  A solução proposta consiste na implementação de uma arquitetura de alta disponibilidade e segurança, estruturada segundo práticas de FinOps, para otimização do uso de recursos financeiros em ambientes de cloud.

  Para assegurar a alta disponibilidade, a arquitetura emprega duas Zonas de Disponibilidade, A e B. A Zona A é primária, recebendo todo o tráfego de entrada inicialmente, a Zona B é configurada como stand-by, recebendo trafego   automaticamente em caso de falha da Zona A. Ambas as zonas estão configuradas dentro do mesmo grupo de segurança associado ao Elastic Load Balancer (ELB), garantindo uma transição do tráfego entre as zonas sem interrupções perceptíveis para o usuário final.

A combinação do Amazon CloudFront e do Amazon S3 é utilizada para melhorar o desempenho e a segurança da aplicação, essa integração permite a entrega de conteúdo com baixa latência e altas taxas de transferência, ao mesmo tempo que reforça a proteção contra ataques DDoS e outras ameaças de segurança. 
Adicionalmente, essa configuração favorece uma gestão de custos mais eficiente, reduzindo o gasto com transferência de dados ao aproveitar a cache de borda do CloudFront.

O gerenciamento de DNS é realizado por meio do Amazon Route 53, que é configurado para registrar um domínio e rotear o tráfego de forma eficiente para as distribuições do CloudFront, proporcionando maior resiliência e disponibilidade.

Em termos de segurança, a aplicação incorpora o AWS WAF (Web Application Firewall), que permite a monitorização detalhada e o controle das solicitações HTTP e HTTPS dirigidas aos recursos, como o próprio CloudFront. 
O AWS WAF é fundamental para mitigar vulnerabilidades, bloqueando tráfego malicioso e personalizando regras de segurança conforme as necessidades específicas da aplicação.


# Monitoramento
