# Resiliência

## Aula 1 - Introdução a resiliência

  - adaptação de um sistema qdo uma falha acontecer
    - um plano b
	
  - minimiza risco de perda de dados e transações importantes
  
## Aula 2 - Proteger e ser protegido

  - mecanismos de autopreservação
  
  - sistema não pode ser egoísta realizando mais requests em um sistema falho
  
  - sistema lento no ar pode ser mais grave que um sistema fora (efeito dominó)
  
## Aula 3  - Health check

  - Checagem da saúde da aplicação
  
    - sinais vitais da app
	
  - sistema não está saudável -> chance de se recuperar
  
  - dependendo do sistema, o mesmo consegue se recuperar -> self healing ("auto cura")
  
  - Health check de qualidade
  
    - acessar url que retorna o html X média de tempo das últimas requisições / consulta banco
	
	- criar estratégia -> que dados que ao acessar vai retornar 200 (verificações se aquilo representa de fato um sistema saudável)
	
## Aula 4 - Rate limit

  - protege sistema no que foi projetado para suportar
  
    - necessário saber qual é o **limite** de requisiçoes que o sistema aguenta  
  
  - preferência programada por tipo de client 	
  
    - por preferência, por prioridade
	
	- sistemas críticos não ficam na mão
	
## Aula 5 - Circuit breaker

  - protege sistema **negando** as requisiçoes que recebe
  
  - circuito fechado -> requisições chegam normal
  
  - circuito aberto -> requisições não chegam -> erro instantâneo
  
  - circuito mieio aberto -> qdte de requisições limitadas para verificar se tem condições de voltar ao ar
  
## Aula 6 - API Gateway

  - requisições impróprias não devem chegar até o ststema
  
    - autenticação valida
	
  - implementa health check, rate limiting, etc
  
## Aula 7 - Service mesh (malha de serviços)

  - controlar o tráfego de rede
  
  - Istio
  
  - proxies do lado de cada sistema
  
  - monitorar comunicação entre sistemas

    - aplicar rate limit, circuit breaker, políticas de retry e etc diretamente na rede
	
  - mTLS (mutual TLS)
  
    - relação de autenticação entre sistemas por meio de proxys
  	
## Aula 8 - Comunicação assíncrona

  - evita perda de dados
    - se o sistema está fora não perde dados
	- servidor processa qdo o sistema estiver online
  
  - kafka
  
  - message broker / sistema de stream
  
  - entenda com profundidade o message broker utilizado
  
## Aula 9 - Garantias de entrega com Retry

  - políticas de retry -> retentativa deve ter alguma lógica
  
  - linear - sem backoff
  
  - exponential backoff - dá um tempo para o sistema responder
  
  - exponential backoff - **Jitter - pequeno ruído** no tempo da chamada, evita retentativas simultâneas
  
    - as retentativas acontecerão em momentos diferentes -> maior chance da requisição funcionar
	
## Aula 10 - Garantias de entrega com Kafka

  - broker
  
    - leader
	
	- follower
	
  - fire and forget	
  
    - dispara e esquece (torce para que a mensagem chegue)
	
	- às vezes precisa ter certeza que recebeu a mensagem
  	
  - Ack -1 ou Ack All
  
    - todos brockers recebem, a mensagem é replicada
	
	- retorna que recebeu e que a mensagem já está sincronizada com os outros brokers
	
	- se um broker caiu, os outros já receberam a mensagem
  
  - trade off garantia de entrega -> avaliar performance X segurança quanto a segurança dos dados
  
    - alta velocidade no envio de mensagens -> Ack 0 -> pode perder alguma coisa
	
	- trabalhar de forma moderada -> Ack 1 (confirmação do leader)
	
    - menos velocidade e mais garantia -> Ack All
  
## Aula 11 - Situações complexas e decisões de alto nível

  - resiliência da resiliência
  
    - se o message broker cair?
	
  - single point of failure
    - se por exemplo o Kafka cair, não perder a informação e ao retornar, ele retorne a enviar as mensagens
  
  - Mais resilência -> mais custo -> maior esforço -> decisão estratégica (c-level)
  
    - mais alto nível -> mais alto é o nível de decisão (dinheiro, mão de obra, especialidade)