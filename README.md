# Entendendo a Importância da Modelagem e Segurança na Construção de APIs

![image](https://github.com/aterra1977/dio-api-security/assets/33560622/0975bd7a-0cf0-48f4-9998-681cf8e09c04)

# Referências Iniciais:
https://swagger.io/specification/

https://www.postman.com/
- Exemplo de acesso ao POSTMAN: 
![image](https://github.com/aterra1977/dio-api-security/assets/33560622/09d8da83-98f6-4683-b037-6806bb83aa8f)

- Modelagem usando RESTfull
- Usando Contratos em API:
	- APIGEE:
		- Treinamento: https://cloud.google.com/training/api-management?hl=pt-br 
		- https://cloud.google.com/apigee/docs/api-platform/get-started/what-apigee?hl=pt-br
![image](https://github.com/aterra1977/dio-api-security/assets/33560622/bb3b21a2-192d-4e2d-bbac-c909bee8fcef)

		- Como a imagem mostra, a Apigee consiste nos seguintes componentes principais:
			- Serviços da Apigee: as APIs usadas para criar, gerenciar e implantar os proxies de API.
			- Ambiente de execução da Apigee: um conjunto de serviços de ambiente de execução em contêineres em um cluster do Kubernetes mantido pelo Google. Todo o tráfego da API passa e é processado por esses serviços.
			- Além disso, a Apigee usa outros componentes, incluindo:
				- Serviços do GCP: fornece funções de gerenciamento de identidade, geração de registros, análise, métricas e gerenciamento de projeto.
				- Serviços de back-end: usados pelos apps para fornecer acesso de ambiente de execução aos dados dos proxies de API.
			- Para explicações mais detalhadas, consulte Componentes da Apigee.
- Disponibilizo o contrato em SWAGGER / OpenAPI: é uma SPEC
	- Voltados para HTTP (https://www.rfc-editor.org/rfc/rfc9110.html) :
		- Códigos de status HTTP: https://www.iana.org/assignments/http-status-codes/http-status-codes.xhtml 
			- O primeiro dígito do código de status define a classe de resposta.
			  Os dois últimos dígitos não têm qualquer função de categorização. Há cinco valores para o primeiro dígito:
				- 1xx (Informativo): A solicitação foi recebida, continuando o processo;
				- 2xx (Bem-sucedido): A solicitação foi recebida com sucesso, compreendido e aceito;
				- 3xx (Redirecionamento): Outras ações precisam ser tomadas para completar o pedido;
				- 4xx (Erro do cliente): A solicitação contém sintaxe incorreta ou não pode ser realizada;
				- 5xx (Erro do Servidor): O servidor não conseguiu cumprir uma tarefa aparentemente solicitação válida.
				- Saiba mais: https://datatracker.ietf.org/doc/html/rfc7231#section-6 
			- Códigos de status definidos como armazenáveis ​​em cache por padrão (por exemplo, 200, 203, 204, 206, 300, 301, 404, 405, 410, 414 e 501 nesta especificação) pode ser reutilizado por um cache com heurística expiração, a menos que indicado de outra forma pela definição do método ou controles de cache explícitos [ RFC7234 ]; todos os outros códigos de status não são armazenável em cache por padrão.
			- Os termos "upstream" e "downstream" são usados ​​para descrever requisitos direcionais em relação ao fluxo de mensagens: todas as mensagens fluem de upstream para downstream. Os termos "entrada" e "saída" são usados ​​para descrever requisitos direcionais em relação à rota de solicitação: entrada significa "em direção ao servidor de origem", enquanto saída significa "em direção ao agente do usuário".
	- O Swagger Editor é um editor de código aberto para projetar, definir e documentar APIs RESTful na especificação Swagger. O código-fonte do Editor Swagger pode ser encontrado no GitHub.
		- GitHub:  https://github.com/swagger-api/swagger-editor
		- https://swagger.io/docs/open-source-tools/swagger-editor/ 
			- Versão Web: https://editor.swagger.io/?_ga=2.14356016.606175209.1697638034-1180389432.1697638027 
-  Gateway de API -> proxy reverso:
	- Um "gateway" (também conhecido como "proxy reverso") é um intermediário que atua como um servidor de origem para a conexão de saída, mas traduz as solicitações recebidas e as encaminha para outro servidor ou servidores. Os gateways são frequentemente usados ​​para encapsular serviços de informações herdados ou não confiáveis, para melhorar o desempenho do servidor por meio de cache de "acelerador" e para permitir o particionamento ou balanceamento de carga de serviços HTTP em várias máquinas.
- API Manager ou Gestão de API:
	- Opensource: https://www.apiman.io/ 
- Exemplo de modelagem de API:
![image](https://github.com/aterra1977/dio-api-security/assets/33560622/4be3546a-8ab3-48c5-87eb-9d9ebf53e918)


# Segurança de API:
- Baseada na OWASP: https://owasp.org/
	- https://owasp.org/Top10/pt_BR/
	- https://owasp.org/www-chapter-rio-de-janeiro/
		- https://www.meetup.com/pt-BR/owasp-rio-de-janeiro/
		- https://www.linkedin.com/company/owasprj/about/
		- https://www.youtube.com/channel/UCwqpYWTFF5dDbLaXJKsqU6w/featured
		- OWASP API SECURITY em Português: https://play.google.com/books/reader?id=ezFxEAAAQBAJ&pg=GBS.PP1&hl=pt 
- apisecurity.io: é constantemente atualizado com as principais vulnerabilidades.

# Certificações gratuitas:
	- https://apiacademy.co/api-certification/
		- Designer de API
		- Arquiteto de segurança de APIs
		- Gerente de Produto API
- https://oauth.io/
- https://apiacademy.co/wp-content/uploads/2020/01/OReilly-eBook-Securing-Microservice-APIs-Sustainable-and-Scalable-Access-Control.pdf
  
# 5 pilares:
	- Visibilidade:
		- quem consome, para quê utiliza, quando utiliza, com quem troca informações.
		- O responsável pelo vazamento é que disponibilizou o dado pela API (LGPD).
	- Controle de Acesso
	- Gerenciamento de Tráfego
	- Proteção de Ameaças
	- Segurança quanto à confidencialidade e integridade das APIs
- Envolve RFC, Protocolos
	- RFC (https://www.rfc-editor.org/) :
		- Os Request for Comments (RFC) são documentos usados pela comunidade online há mais de 40 anos para definir os padrões da web e compartilhar informações técnicas. Atualmente, os RFCs são gerenciados pela IETF (Internet Engineering Task Force). Saiba mais: https://pt.wikipedia.org/wiki/Request_for_Comments

# Temos 3 riscos a serem considerados:
	- Estrutura: tamanho de mensagem, resursos de timestamp, mensagem não formatada
	- Formato: xml, json, mark-up
	- Semântica: whitelist, blacklist, validação de schema
- SLA: Acordo de Nível de Serviço
	- Importante considerar horário, limites e monitorar para identificar possíveis ataques.

# Especificação de APIs com OpenAPIs (https://www.openapis.org/)
	- A Especificação OpenAPI (OAS) fornece um meio consistente para transportar informações em cada estágio do ciclo de vida da API. É uma linguagem de especificação para APIs HTTP que define estrutura e sintaxe de uma forma que não está vinculada à linguagem de programação na qual a API é criada. As especificações da API são normalmente escritas em YAML ou JSON, permitindo fácil compartilhamento e consumo da especificação. #analisederequisitos 
	- https://spec.openapis.org/oas/latest.html#especifica-o-openapi

 
> Desafio do curso: https://web.dio.me/lab/entendendo-a-importancia-da-modelagem-e-seguranca-na-construcao-de-apis/learning/fd7a4e4e-b071-4109-b797-bd1f159496f6 
 #seguranca #arquitetura #dio-api-security
