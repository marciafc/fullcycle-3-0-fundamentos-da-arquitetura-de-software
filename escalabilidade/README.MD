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
	
	

