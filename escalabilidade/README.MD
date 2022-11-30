# Escalabilidade

## Aula 1 - Escalabilidade

  - capacidade dos sistemas suportarem o aumento (ou a redução) dos workloads ->  incrementando (ou reduzindo) o custo em menor ou igual proporção
  
    - Elemar JR, arquiteturadesoftware.online
	
	- Workload -> carga de trabalho
	
  - Escalabilidade x performance	
  
    - Escalabilidade: possibilidade de aumentar / diminuir o throughput, aumentando ou reduzindo a capacidade computacional
	
	- Performance: reduzir a latência + aumentar o throughput
	
  - Escalando sw
  
    - escala vertical: aumentar recurso computacional - (mais memória, mais CPU, mais disco)
	
	  - limite de hardware
	  
	  - tudo concentrado em um único local (risco da máq cair -> 100% do sistema fica fora)
	
	- escala horizontal: aumentar a qtde de máquinas, proxy reverso ou load balancer na frente
	
	  - não requer a melhor máq
	  
	  - se uma máq cair -> não ficam todas fora do ar
	  
## Aula 2 - Escalando aplicações

  - descentralização: tirar o que está focado em uma máq, por em outro local e permitir que esssa máq possa ser criada / removida sem perda de infos, podendo assim aumentar o throughput
  
    - disco efêmero (tudo pode ser apagado qdo necessário)
	  - não mantém estado
	
	- servidor de aplicação X servidor de assets
	  - aplicação é stateless
	
	- cache centralizado
	
	- sessões centralizadas (servidor de cache)
	
	- upload / gravação de arquivos
	
	
## Aula 3 - Escalando banco de dados

  - aumentar recurso computacional (mais memória, mais CPU, etc...)
  
  - distribuir responsabilidades (escrita X leitura)
  
    - banco de dados para leitura e outro para escrita
	
  - shards de forma horizontal	
  
    - leitura tão grandes -> várias máquinas só de leitura
	
	- mudar o formato do banco
	
	- criar partições no banco
	
  - serverless
  
    - deixa a cargo do Cloud Provider
	
	- serverless não é somente lambda functions da AWS
	  - S3 Serverless
	  - DynamoDB

  - otimização de queries e índices
  
    - tenha sistema de APM para entender as queries, gargalos
	
	- faça explain nas queries
	
	- trabalhe com índices
	
	- CQRS (Command Query Responsability Segregation)
	
## Aula 4 - Proxy reverso

  - "Um proxy reverso é um servidor que fica na frente dos servidores web e encaminha as solicitações do cliente (por exemplo, navegador web) para esses servidores web. 
  
  - Os proxy reversos normalmente são implementados para ajudar a aumentar a segurança, o desempenho e a confiabilidade." [O que é um proxy reverso? - cloudflare](https://www.cloudflare.com/pt-br/learning/cdn/glossary/reverse-proxy/#:~:text=Um%20proxy%20reverso%20%C3%A9%20um,o%20desempenho%20e%20a%20confiabilidade.)
  
  - [proxy de encaminhamento Vs proxy reverso](https://www.cloudflare.com/pt-br/learning/cdn/glossary/reverse-proxy/#:~:text=Um%20proxy%20reverso%20%C3%A9%20um,o%20desempenho%20e%20a%20confiabilidade.)
    - Qual é a diferença do proxy reverso?
	
  -	 Nginx
  
  - HAProxy (HA - High Availability)
  
  - Traefik