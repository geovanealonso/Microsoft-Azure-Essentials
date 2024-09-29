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
 

## Benefícios da computação em nuvem
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

# Conceitos Iniciais de Cloud com Azure
## Localizando serviços por categoria
- 
