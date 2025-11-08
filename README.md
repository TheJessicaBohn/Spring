# Spring

## Introdução ao Spring
- Coleção de frameworks que serve para fazer varias coisas;
- Ajuda na construção de aplicativos de forma mais eficiente e organizada;

## Pilares do Spring:
- **Inversão de Controle(IoC)**: Gerencia depêndencias e interações entre componentes;
- **Injeção de Dependência(DI)**: Mantém o código limpo e modular;
- **Programação Orientada a Aspectos(AOP)**: Organiza comportamentos comuns, mantendo o código principal limpo. Separa os componentes comum do código principal;

## Componentes do Spring:
- **Spring Boot**: Inicialização rápida de projetos;
- **Spring MVC**: Criação de aplicativos web;
- **Spring Data**: Acesso simplificado a banco de dados;
- **Spring Security**: Funcionalidades robustas de segurança;
- **Spring Batch**: Processamento de grandes volumes de dados;
- **Spring Cloud**: Ferramentas para sistemas distribuídos e microsserviços;
- **Spring Integration**: Soluções de integração empresarial;
- **Spring AMQP**: Supoete para mensageria assincrona;
- **Spring WebFlux**: progrmação reativa;
- **Spring AI**: Integração de inteligência artificial;

## REST:
- Padrão arquitetônico, que significa "Representational State Transfer", que define um conjunto de restrições e principios para contrução de um serviço web. Um gua para construir APIs de forma eficiente e escalável;
- A principal utilização do Sring Boot é para construir aplicações do tipo REST;
- **Vantagem**: Amplamente utilizado para criar APIs quer permitem a comunicação entre diferentes sistemas, pois ele retorna os dados de forma que outras linguagens possam ter acesso, e outras aplicações poderem consumir;
- Acessa os dados através do protocolo de internet HTTP ou HTTPS
<img width="916" height="425" alt="image" src="https://github.com/user-attachments/assets/5fd57354-88e7-401a-bc5a-bbb83bfeebd2" />

## API REST:
- **Principais Caracteríscas:
	- 1- Cliente-Servidor;
	- 2- Sem Estado: Cada pedido do cliente ou servidor, é independente, o servidor não gurda informações sobre pedidos anteriores, embora dê pra fazer algumas impelmentações...as requisições são feitas de forma isoladas
	``` **Exemplo**: Nosso projeto de dados clímaticos```
	- 3- Cacheável;
	- 4- Interface Uniforme: Exemplos: GET, POST, PUT, DELETE. Independente do cliente ele utiliza o HTTP;
	- 5- Sistema em camadas: Escalabilidade e gerenciamento da aplicação;
- **Vantagens das APIs REST**:
	- Simplicidade;
	- Escalabilidade;

## APIs RESTful com Spring Boot

- **RESTful**: Serviço web que segue as regras REST implementadas completamente:
	- 1- GET: Usado para ler dados.
	- 2- POST: Usado para criar novos dados.
	- 3- PUT: Usado para atualizar dados existentes.
	- 4- DELETE: Usado para excluir dados.
- Se sua API tiver as operações GET, POST, PUT e DELETE corretamente implementadas, seguindo as boas práticas do REST, você pode chamá-la de RESTful;

## Implementação do IoC:
- Injeção de depêndencia: Técnica onde um objeto recebe suas dependências de fora, ao ivés de criar por conta própria;
- Ao Ives do objeto criar as dependências o Spring fornece as dependências, injetando a dependência, além de controlar o cilco de vida dos objetos;
- O controle de objetos e o fluxo da aplicação são gerenciados por um container ou framework como no caso, o spring;
- O conceito de Inversão de Controle, é passar o controle de alguns objetos para o framework, e não precisará mais se preocupar mais com ele, pois o framework vai tomar conta disso;
- **Tipos de injeção**:
	- **Injeção por construtor**: As dependências são passadas através de um construtor da classe. Utiliza uma anotação do Spring para que o objeto seja injetado;
		- Como as dependências são passadas por parâ metro no construtor da classe, então quando você cria a instância da classe você fornece todas as depêndencias necessárias através do construtor;
		- Esse método é útil pois torna explicito as dependências da classe. Facilitando o entendimento e a manutenção do código;
		- Ainda posso usar a depedência em outra parte do código;
		- Existe ainda a **Injeção por contrutor implícita**: significa que se eu tiver APENAS UM construtor na classe, eu não preciso usar o ```@Autowired```, mas é uam boa prática;
	~~~Java
    	//outros imports
		import org.springframework.beans.factory.annotation.Autowired;

		public class MeuServico {
			private final Dependencia dependencia;
			
			@Autowired
			public MeuServico (Dependencia dependencia) { // dependência por parametro
				this.dependencia = dependencia;
			}

			public void executar() {
				dependencia.fazeralgo();
			}
		}
 	~~~
		
	- **Injeção por Setter**: É uma técnica onde as dependências de uma classe são injetadas através de métodos setter públicos, também conhecida como injeção de propriedade;
		- Após a criação da instância, o Spring chamará os métodos setters para fornecer as as depêndencias necessárias;
 		- Ele é útil quanso você quer permitir a substituição ou a modificação das depedências após a criação do objetoç
 		- Uma vez que eu definir um objeto injetado, ele não é para sempre, você pode fazer a substituição dessa dependência conforme a necessidade;
	~~~Java
    	//outros imports
		import org.springframework.beans.factory.annotation.Autowired;

		public class MeuServico {
			private Dependencia dependencia;
			
			@Autowired
			public void setDependencia (Dependencia dependencia) {
				this.dependencia = dependencia;
			}

			public void executar() {
				dependencia.fazeralgo();
			}
		}
 	~~~
 		
	- **Injeção por campo**: É uma técnica onde as dependências de uma classe são injetadas diretamente em seus campos através de anotações: ```@Autowired```;
		- Spring cuida de preencher esses campos quando ele cria a instância da classe, e isso faz com que seja requerido menos código;
 		- Ele torna as dependências menos explicitas;
 		- Como isso funciona: toda  variável membro, ou seja, a variável que  está fora do método, porém dentro da classe é inicializada automaticamente com null;

	~~~Java
    	//outros imports
		import org.springframework.beans.factory.annotation.Autowired;

		public class MeuServico {
			@Autowired
			private Dependencia dependencia; //new Dependencia()

			public void executar() {
				dependencia.fazeralgo();
			}
		}
 	~~~