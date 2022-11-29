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
	  
## Aula 3 - Características Estruturais

  - configurável: ser simples cambiar a aplicação
  
  - extensibilidade: preparada para crescer (aspectos de apps terceiros, como gateways)
  
    - camada anticorrupção (separa aplicação com camadas finas com o mundo externo)
  
  - ser simples para instalar
  
    - padronizar ambientes - containers!
	
	- ser simples configuração
	
  - reutilização de componentes
  
  - internacionalização
  
    - backend: moeda e gateway, conversão
	
	- frontend: tela pode desconfigurar, aspectos culturais podem ser diferentes
	
  - fácil manutenção
  
    - SOLID
	
	- camadas, adaptadores, interfaces
	
	- ter testes é fundamental
	
  - portabilidade (trabalhar com diversos banco de dados)
  
    - menor impacto ao trocar de BD
	
	- trocar Elastic para Datadog, é fácil?
	
	- pensar em trabalhar com opentelemetry
	
  - fácil suporte
  
    - logs (centralização e padrão de geração de logs), debugging
	
	- benchmarks internos
	
	- tipos de spam, observabilidade, métricas
	
	- sustentação, identificar o que está acontecendo se há algum problema (de forma proativa e não reativa)
	
## Aula 4 - Características cross cutting

  - acessibilidade
  
    - público que vai acessar (frontend), leitores de tela
	
  - retenção e recuperação de dados (tempo que serão mantidos)
  
    - storage tem custo
	
	- dados quentes (banco de dados) X dados que não usa o tempo todo (compactar em storage mais baratos)
	
  - autenticação e autorização
  
    - identity provider (provedor de Identidade)
	
	- API gateway
	
  - legal
  
    - compliance do país
	
  - privacidade
  
    - lgpd
	
  - segurança
  
    - preocupação desde a borda, web firewall, regras e mecanismos para identificar robôs
	
	- usar padrões abertos
	
	- banco de dados separado da app 
	
	- backups em outra rede da que está a app
	
  - usabilidade
  
    - não é só frontend
	
	- melhor experiência para o cliente
	
	- organização da API (ter documentação, ser simples, possuir padrões como Open API, contrato estar claro, ter README)