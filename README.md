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