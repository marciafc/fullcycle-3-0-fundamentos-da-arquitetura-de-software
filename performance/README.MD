# Performance

## Aula 1 - Perspectivas para arquitetar um software

  - performance
  
    - métricas
  
  - escalabilidade
  
  - resiliência
  
    - todo software nasceu para falhar, ter bugs
	
## Aula 2 - Métricas para medir a performance

  - latência (response time, tempo de resposta) -> DIMINUIR
  
    - medida em milisegundos geralmente
  
    - tempo de processamento, rede e chamadas externas afetam
  
  - throughput -> AUMENTAR
  
    - qtde de requisições
	
	- diretamente elacionado a latência
  
  - software performático != software escalável    
  
## Aula 3 - Checklist para aumento de performance

  - Principais motivos de baixa performance
  
    - processamento ineficiente (algoritmos, por exemplo)
	
	- recursos computacionais limitados (hardware de baixa qualidade, por exemplo)
	
	- estar trabalhando de forma bloqueante
	
	- acesso serial a recursos (requisição uma atrás da outra)
	
  - Principais formas para aumentar a eficiência
  
    - otimizar lógica do sw (queries, algoritmos, overhead de frameworks)
	
    - escala da capacidade computacional: cpu, disco (muito I/O), memória (swap), rede (não suporta a chegada de todas requisições)
	
	- concorrência e paralelismo -> threads simultâneas
	
	- BDs -> tipos de bancos, schema
	
	  - explain, índice, ferramenta de APM para avaliar tempo que os acessos ao banco estão consumindo
	  
    - caching: disco, memória
	
## Aula 4 - Escala concorrência e paralelismo

  - capacidade computacional: escala **vertical** x **horizontal**
  
    - escala vertical -> aumentar capacidade computacional
  
    - escala horizontal -> aumentar capacidade de máquinas (uso de load balancer na frente) 
  
  - concorrência X paralelismo
  
    - concorrência: **lidar** com muitas coisas ao mesmo tempo
	
	- paralelismo: **fazer** muitas coisas ao mesmo tempo
	
## Aula 5 - Caching

  - cache na borda (edge computing) -> Cloudflare
  
  - dados estáticos -> imagens, css -> barato, melhor experiência
  
  - páginas web
  
  - funções internas
  
    - evitar reprocessamento de algoritmos pesados
	
	- acesso a BD (é custoso)
	
  - objetos
	
  - caching: **exclusivo** X **compartilhado**
  
    - exclusivo: 
	  - baixa latência, é local, duplicado entre nós, outras máquinas não se beneficiam daquele cache
	  - problemas referente a sessões
	
	- compartilhado:
	  - maior latência, cache central (todos precisam acessar), não há duplicação, todas máq se beneficiam do cache
	  - sessões compartilhadas
	  - banco de dados externo -> todos acessam o mesmo bd (MySQL, Redis, Memcache)
	  
## Aula 6 - Caching vs Edge Computing

  - Edge Computing -> cache mais perto do usuário (isso evita que as requisições trafeguem mais pela internet)
  
    - CDN (Content Delivery Network)
	  - CDN da Akamai
	
	- evita que tudo chegue no servidor
	  - evita o request até o Cloud Provider / Infra
	
	- economiza custo, usuário com melhor experiência
	
	- internet / rede não são ilimitadas
	
	- cachear arquivos estáticos (imagens, css, html estático) na edge -> mais barato ou gratuito
	  - Cloudflare
	  
    - Cloudflare worker: usuário baixa do lugar mais próximo, roda muito mais rápido, processa somente o JS que é chamado e cacheado no computador
	  - cada deploy de uma nova versão -> espalha em todos os datacenters dela -> gasta menos banda na hora de chegar, preço mais acessível
	  
    - Vercel - Next JS	  
	  - Vercel tem iniciativa de Edge computing
	  
    - Akamai