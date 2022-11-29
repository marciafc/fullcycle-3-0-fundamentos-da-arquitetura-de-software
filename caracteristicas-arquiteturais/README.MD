# Características arquiteturais

## Aula 1 - Características arquiteturais

  - Operacionais
  
  - Estruturais
  
  - Cross-cutting
  
## Aula 2 - Características Operacionais

  - disponibilidade
  
    - nível SLA, SLO (goals, objetivos)
	
	- pensar em observabilidade
	
	- verificar incidentes
  
  - recuperação de desastres
  
    - sistema de missão crítica, definir processos, mitigação
	
	- multi região, multi cloud
	
  - performance
  
    - latência
	
	- capacidade de receber requisições (throughput)
	
  - recuperação (backup)
  
    - testar o backup (criar políticas, regras par testar)
	
	- manter backup em redes separadas: se acontecer ataque de ransomware os backups não serão criptografados juntos
	
  - confiabilidade e segurança
  
    - sistemas de missão crítica
	
  - robustes
  
    - garantir escalabilidade
	
	- capacidade da cloud não é infinita
	
  - escalabilidade
  
    - vertical (aumento recurso computacional na máq), horizontal (mais máquinas)
	
	  - horizontal: stateless, seguir os 12 fatores (Twelve Factors) no Heroku
	  
	  