# Módulo 1: Conceito de Nuvem
- O que é?
	- Fornecimento de **serviços de computação pela Internet**.
	- Habilita **recursos flexíveis** e economias de **escala**
- 3 Modelos de nuvem (O 4 não cai na prova)
	- **Nuvem privada** 
		- Ambiente 100% on-premise![[Pasted image 20240925144348.png]]
		- Datacenter da organização
		- As organizações são responsáveis pelas operações
		- Não fornece acesso aos usuários fora da organização
		- Comparação
			- Organizações têm controle total sobre recursos e segurança
			- Organizações são responsáveis pela manutenção e atualizações
	- **Nuvem pública**
		- Entrega de serviços a vários clientes
			- Azure, AWS etc.
		- Pertence ao provedor
		- Acessada via Internet
		- Comparação
			- Nenhuma **despesa de capital (CapEx)** para escalar verticalmente - pagar somente depois
			- Os aplicativos podem ser provisionados e desprovisionados rapidamente
			- As organizações pagam apenas pelo que utilizam (pay as you go)
	- **Nuvem Híbrida**
		- Pública e Privada
		- Combina nuvens públicas e privadas]
		- Comparação
			- As organizações determinam onde executar seus aplicativos (rede corporativa privada ou pública - nacional ou internacional)
			- Maior flexibilidade
	- *(Quarto modelo não cai na prova - Multicloud)* - AWS e Azure, por exemplo. Mais de uma nuvem pública.
	- CapEx vs OpEx (muito comum cair na prova!!!!!)
		- Despesas de capital (CapEx)
			- O gasto inical de dinheiro em infraestrutura física
				- Máquinas, cabeamento etc.
			- Despesas se reduzem com o tempo
		- Despesas operacionais (OpEx)
			- Gastar com produtos e serviços conforme necessário, pagamento conforme o uso
			- Modelo baseado em consumo

## Conceitos Iniciais de Cloud com Azure
### Benefícios da computação em nuvem
- Convencer o cliente
- Alta disponibilidade 
	- Se concentra em garantir disponibilidade máxima
	- "Service Level Agreement"
		- Agreement between service provider and customer
		- Azure SLA
		- Uptime and Downtime
		- 100% Uptime é difícil pois é necessário tempo de manutenção
		- SLA 99%, 99.9%, 99.95% são mais comuns
		- 99% - até 7.2 horas por semana fora do ar![[Pasted image 20240929134302.png]]
- Escalabilidade
	- Refere-se à capacidade de ajustar recursos para atender a demanda
	- Você só paga pelo que você usa
	- "Elasticidade"
		- "Eu não sei quanto preciso crescer"
		- Exemplo da black friday
			- Conforme mais visitas, os recursos poderão aumentar de maneira automática (ou manual)
- Confiabilidade e Previsibilidade e Segurança 
	- Resiliência
	- Confiabilidade
		- Design descentralizado
		- Sistema que se recupera de falhas
		- Escala global - mesmo que ocorra um evento catastrófico em uma região, há dezenas de outras
	- Previsibilidade
		- Permite que você avance com confiança
		- Desempenho
		- Microsoft Azure Well-Architected Framework
		- Mantém o jeito como as coisas funcionem
	- Segurança
		- Perda de informação...
		- Implementação não é responsabilidade da microsoft
		- Segurança de recursos
- Governança
	- Os padrões para gerir os recursos
	- Auditoria (quem fez o que, quem tem acesso ao que)
	- Gestão
	- Regras
	- Presença de nuvem atualizada, protegida e bem gerenciada
- Gerenciamento
	- Powershell, linhas de comando, website, APIs etc.
	- Por exemplo: escalar automaticamente a implantação de recursos com base na necessidade.

### Tipos de serviços na nuvem
- Iaas, PaaS e SaaS![[Pasted image 20240929135710.png]]
	- Não só da azure, geral pra nuvem
	- IaaS - Infraestrutura as a service
		- Mais utilizado
		- Servidores e armazenamento
		- Firewalls/Segurança de rede
		- Mais flexível - você configura e gerencia o hardware
	- PaaS - Plataform as a service
		- Sistemas operacionais
		- Ferramentas para desenvolvedores, análise de negócios de gerenciamento de database
		- Um ambiente para a criação, teste e implantação de aplicativos de software, sem focar no gerencimaneto da infraestrutura subjacente
		- Focado no desenvolvimento de aplicativos
	- SaaS - Software as a service
		- Aplicativos/Apps hospedados (microsoft teams, por exemplo)
		- Modelo de licenciamento determina (office 365, por exemplo)
		- Os usuários pagam pelo software em um modelo de assinatura
- Modelo de **responsabilidade compartilhada** (sempre cai na prova)![[Pasted image 20240929135939.png]]

# Módulo 2
- Componentes de arquitetura do Azure
	- Regiões
	- Assinaturas e grupos de recursos
## Componentes de arquitetura do Azure
- Vários servidores ao redor do mundo
	- Mais de 60 regiões em mais de 140 países
	- Backbone - rede que os datacenters sem comunicam
	- LGPD - conformidade - determinados dados não podem sair pra fora do Brasil
	- "Zonas de Disponibilidade" - datacenter![[Pasted image 20240930143519.png]]
		- Fornece proteção contra tempo de inatividade devido a falha do datacenter
		- Os dados são copiados entre os datacenters (redundância)
		- Conectados por fibra ótica
	- **Pares de regiões**![[Pasted image 20240930144100.png]]
		- Cada região possui uma região par - uma zona secundária caso a primeira dê problema
		- No mínimo 300 milhas de separação entre elas
		- A replicação é automática para *alguns serviços*
	- **Regições soberanas do Azure**
		- Regiões exclusivas que não estão disponíveis para clientes normais
		- China e EUA
			- Serviços Governamentais pros Eua - para área militar
				- Acessível somente para personal autorizado
			- Azure China
				- Operada pela 21Vianet
				- Os dados permanecem dentro da China
	- **Recursos do Azure**
		- Armazenamento, máquinas virtuais, redes virtuais, banco de dados etc.
		- Grupo de recursos - uma "caixa" que tudo que você criou está dentro
			- Possível migrar recursos para outro grupo de recursos
				- Mas não da pra renomear
			- Não há jeito certo de managear grupo de recursos, apenas o jeito certo que funciona pra minha empresa
	- Assinaturas do Azure
		- Assinatura do desenvolvimento, do teste, da produção
		- Uma conta pode ter diversas assinaturas, mas uma assinatura está associada a apenas uma conta
		- Pra cada assinatura tem uma fatura diferente
	- Grupos de gerenciamento![[Pasted image 20240930153420.png]]
		- Organização
		- Regras
		- Imagem: Duas regras padrões pra uma mesma assinatura![[Pasted image 20240930153613.png]]
		- Hierarquia ![[Pasted image 20240930153626.png]]
- Nem todos os recursos estão pra todas as regiões
- Certificação AZ-900 não requer laboratório (entrar no site)
- https://datacenters.microsoft.com/globe/explore/
## Computação e Rede
- Tipos de computação
	- ![[Pasted image 20240930161918.png]]
		- **Área de trabalho virtual** - ao invés da empresa disponibilizar um computador, ela pode habilitar uma área de trabalho virtual do azure
			- Ambiente personalizado
			- Reduz risco de recurso perdidos - pessoa demetida que não devolve o notebook
			- Multisessão - mesma área de trabalho que várias pessoas têm sua pastinha
		- Contêiners
			- Máquina virtual consome muitos recursos, contêineres consomem de uma forma mais silenciosa
			- Projeto pra ser dimensionado ou interrompido sempre que necessário
			- Docker é o mais popular
			- Não exige um sistema operacional
			- Instância de contêiner
				- Oferta de PaaS
			- Aplicativos de Contêneir
				- Oferta de PaaS também
				- Permite trabalho imediato, sem management
				- Pode balancear a carga e escalar
				- Falou de contêneir, falou de PaaS
			- AKS / Azure Kubernetes Server / Serviço de Kubernetes do Azure
				- "Orquestração" 
					- Contêiner são vários serviços, e as vezes fica um pouco desorganizado
					- Gerencia o ciclo de vida dos contêneires
		- Azure Functions![[Pasted image 20241001184239.png]]
			- Oferta de PaaS que dá suporte a operações de um computação sem servidor
			- Precisa de uma situação que aciona ela, com ou sem estado (solitação REST)
		- Máquinas Virtuais
			- Emulações de software de computadores físicos
				- Processador virtual, memória, armazenamento e rede
				- Infraestrutura as a Service
					- Responsabilidade compartilhada
			- Conjuntos de dimensionamento de VMs
				- Configurar para diversas funções (desenvolvimento, testes etc.)
			- Conjuntos de disponibilidade de VMs
				- ![[Pasted image 20240930162513.png]]
					- 6 máquinas, cada par num rack diferente
				- Se só tiver um rack, e alguém tropeçar um fio, meu servidor não está altamente disponível
				- Domínio de falha - rack
				- Domínio de atualização - cada linha de máquinas![[Pasted image 20240930163710.png]]
					- Se um pc estiver atualizando, o de baixo estará disponível
- Hospedagem de aplicativos
- Redes virtuais
- COMPARAÇÕES
	- Máquinas Virtuais
		- Windows ou Linux
		- Útil para migrações lift-and-shift para nuvem
			- Levar máquinas físicas para nuvem (Azure Migrate)
	- Área de trabalho Virtual
		- Experiência Windows em nuvem
		- Logon de vários usuários no mesmo computador
	- Contêineres
		- Microserviços, sistema leve
		- Projeto para escalabilidade por meio de orquestração (Kubernetes)
		- Aplicativos e serviços são empacotados em um contêneir
- Serviços de Aplicativos
	- Plataforma para criar, implantar e dimensionar aplicativos Web e APIs
	- Trabalha com .NET, .NET Core, Node.js, Java, Python ou php
	- Oferta de PaaS
- Rede Virtual do Azure (VNet)
	- Permite a comunicação entre os recursos dentro do Azure
	- Duas Vnets não falam entre si por padrão, para proteger contra ataques
- Gateway de VPN
	- Enviar tráfego criptografado entre uma rede virtual do Azure e uma local pela Internet Pública
	- ![[Pasted image 20241001190256.png]]
- Express Route
	- Alternativa de Gateway
	- Um cambeamento direto (conexão privada), ao invés de usar a internet pública
- DNS do Azure
	- Segurança
	- Resolvedor de nome
	- Permite usar nomes de domínio privados e totalmente personalizados em suas redes virtuais privadas
## Armazenamento no Azure
- Contas de Armazenamento / Storage Accounts
	- Precisa der um **nome globalmente exclusivo**
		- Nomear: sto + projeto + completar com qualquer coisas

- Redundância
	- ![[Pasted image 20241003093512.png]]
		- **LRS** - mesmo datacenter![[Pasted image 20241003094027.png]]
		- Quanto mais noves mais disponibilidade
		- **ZRS** - zona - 3 datacenters na mesma região![[Pasted image 20241003094036.png]]
		- **GRS** - redundância geográfica - modelo de cópia LRS duplicado
		- **GZRS** - cópias nos 3 datacenters em uma região e uma única vez em uma região par
			- Assíncrono - na região par tem um delay, mas na mesma região é síncrono
			- O dado na região par não é para consumir, é apenas de backup
- Blobs, files, filas e mensagens
	- **Blob** do Azure
		- Otimizado para armazenamento de quantidades massivas de dados **não estruturados**
			- Vídeo, texto, de tudo!!
			- Armazena de tudo
	- Disco do Azure
		- Discos paras máquinas virtuais, aplicativos e outros serviços
	- Fila do azure
		- Armazenamento de mensagens
		- Fornece armazenamento e recuperação para grandes quantidades de mensagens, cada uma com até 64 kb
		- Uma aplicação pode gerar mensagens
	- Files (Arquivos) do Azure
		- Se não for o primeiro, o segundo mais utilizado
		- "Pastinha na nuvem"
	- Tabelas do Azure
		- Opção de chave/atributo para o armazenamento de dados estruturados não relacionais
- Pontos de extermidade públicos do serviço de armazenamento
	- O endereço
	- ![[Pasted image 20241003102029.png]]
	- Caiu na prova: apontar o endereço de blob para aplicação
- Camadas de acesso de armazenamento do Azure
	- ![[Pasted image 20241003102449.png]]
	- Muda o custo
	- Frequente - cobra mais pelo repositório cobra pouquinho com cada acesso
	- Esporádico - cobra menos pelo repositório e mais para consulta
	- Frio - cobra menos ainda pelo repositório e mais para consulta
	-  Arquivo Morto - mais usado para o backup.
		- Repositório fica mais barato porque o azure separa os arquivos entre servidores, e dá mais trabalho para juntar tudo para consulta
- **Migrações para o azure**
	- Ambiente on-premise para computação em nuvem
	- Legacy
	- Azure data box
		- Serviço de migração física
		- Até **80 tb** de dados
		- ![[Pasted image 20241003103234.png]]
		- Amazon tem o snowmobile - 100 pb
		- Caso de uso: um cliente que é de uma localidade distante e que não faria sentido transferir estes dados pela internet.
			- Conectividade limitada ou sem conectividade
- Opções de gerenciamento de arquivos
	- AzCopy
		- Utilitário de linha de comando
		- Ajuda a copiar dados para os blobs
		- Não é uma via de mão dupla
	- Gerenciador de Armazenamento do Azure
		- Também faz uma cópia, mas tem interface gráfica
		- Compátivel com o Windows, MacOS e Linux
		- Utiliza o AzCopy por trás das cortinas
	- Sincronização de Arquivos do Azure
		- Sincronização **bidirecional**
		- Opção: os arquivos não utilizados há mais de 30 dias, mover pra nuvem
## Identidade, acesso e segurança
- Segurança é responsabilidade nossa (do usuário)
- Microsoft Entra ID
	- Antigamente (2023 pra trás) se chamava Azure Active Directory
	- Usuários deletados podem ser restorados por 30 dias
	- Família "Entra" de produtos tem a ver com segurança
	- Entra connect - conector entre ambiente on premise em nuvem
	- Responsabilidades
		- Autenticação
		- Logon único (SSO - Single Sign On) - uma aplicação de windows pode entrar automaticamente se usar a funcionalidade Entra ID (porque ela já está logado no windows)
	- Autenticação VS Autorização
		- Autenticação - identifica a pessoa, mostra credenciais. "Autentiquei, logo existo"
		- Autorização - nível de acesso
		- Uma pessoa pode autenticar (mostrar as credenciais) mas não ser autorizada a fazer nada
		- A ideia é que as pessoas tenham o menos de autorização possível
	- Autenticação multifator
		- Algo que você sabe (login e senha)
		- Algo que você possui (celular)
		- Algo que você é
	- Autenticação B2B
		- Login com google e etc
		- ![[Pasted image 20241006112724.png]]
	- B2C
		- ![[Pasted image 20241006112919.png]]
	- Acesso condicional
		- Variáveis
			- Associação de usuário ou grupo
			- Local do IP
			- Dispositivo
			- Aplicativo
			- Detecção de risco
		- Controle de acesos baseado em função (RBAC)
			- Herdável
- Microsoft Domain Service
- Microsoft Defender para Nuvem
	- Nativo de nuvem
	- Monitoramento que fornece proteção contra ameaças nos datacentes dos Azure (também faz de outros clouds, como AWS)
	- 30 dias grátis
		- Tem como pagar apenas paras camadas que fazem sentido
	- Recursos
		- Recomendações
		- Detectar e bloquear malware
		- Just-in-time para portas (liberação)
- Confiança Zero
	- Não confie em ninguém e desconfie de todos
	- Pressupõe sempre o pior cenário
	- Smpre presumir que algo foi violado
	- ![[Pasted image 20241006113632.png]]
	- 
- Modelo de defesa em profundidade
	- Camadas de segurança

# Módulo 3 - Gerenciamento e Governança
## Gerenciamento de custos
- Marcas ou tags
	- Não sou obrigatórias nem herdáveis
	- Consistem em um par nome-valor.
	- Ajuda a reunir informações de cobrança (na fatura)
	- Dá pra criar uma policy exigindo a criação de tag
- Fatores que afetam os custos
	- Tipo de recurso
	- Consumo (Pay as you go OU pré pago)
	- Manutenção
	- Área geográfica
	- Tráfego de rede (pelas regiões)
	- Assinatura (tipo e configuração)
- Azure Marketplace
	- Aplicações de outra marca
	- Quando adicionado um recurso não nativo do azure, não procurar o suporte da microsoft - mas sim do fabricante
- Calcuradora de preços
	- Apenas uma estimativa, não um valor exato. Porque há muitas variáveis
	- Região, camada, cobrança, suporte, ofertas
	- Calculadora de custo total de Propriedade (TCO)
		- Estimular a economia de custos na migração pro azure
		- Desmistificar o azure pra uma empresa
