### Histórico de Revisões

| Versão | Descrição     | Autor   |
|:------:|:-------------:|:-------:|
|  1.0   | Políticas| Thiago Ribeiro|

-----
  
[1. Introdução](#1-introdução)  
[2. Políticas](#2-políticas)  

-----

## 1. Introdução

<p align="justify">Este documento tem como objetivo padronizar e explicitar as políticas de contribuição a serem seguidas pela equipe durante o desenvolvimento do projeto.</p>

## 2. Políticas

### 2.1 Política de Contribuição na _Wiki_
<p align="justify">Com o intuito de manter a rastreabilidade e controle das alterações feitas na <i>Wiki</i> do projeto, o usuário que for adicionar ou modificar algum conteúdo deverá incluir uma pequena mensagem, no campo adequado, explicando a alteração feita. Esta mensagem deve estar em inglês com o verbo no gerúndio e o ponto final ao fim da frase.</p>

Exemplo:
* “<i><b>Adding policy guide.</b></i>”

### 2.2 Política de _Commits_

<p align="justify">Os <i>commits</i> devem ser atômicos, representando uma funcionalidade ou parte dela. A mensagem deve descrever o que foi produzido, de forma sucinta. Além disso, o <i>commit</i> deve ser iniciado com uma <i>hash</i> acompanhado do número, que representa a <i>issue</i> a qual esse <i>commit</i> pertence. Assim como a mensagem para contribuir na <i>wiki</i>, o <i>commit</i> deverá ser em inglês atendendo o seguinte padrão. <b>< #Número da <i>issue</i> - Texto com a primeira letra da frase maiúscula, verbo no gerúndio, terminando com o ponto final. ></b> .</p>

Exemplo:
* “<i><b>#2 - Adding user model.</b></i>”
* "<i><b>#17 - Creating user tests.</b></i>"

### 2.3 Política de _Branches_

<p align="justify">Haverá apenas um repositório com uma <i>branch</i> principal (<i>master</i>) e uma <i>branch</i> auxiliar de desenvolvimento (devel). Será necessária a criação de <i>branches</i> auxiliares para o desenvolvimento de cada história de usuário ou história técnica, essas serão ramificações da <i>devel</i>. Após o término da funcionalidade, os desenvolvedores responsáveis deverão mesclar o conteúdo da <i>branch</i> auxiliar na qual a funcionalidade foi desenvolvida com a <i>branch</i> auxiliar de desenvolvimento (<i>devel</i>). Essa tarefa deve ser realizada com o comando <i>merge</i>. A funcionalidade deverá ser integrada a <i>master</i> através do <i>pull request</i>, onde o qualidade do código será analisada.</p>

As <i>branches</i> auxiliares deverão ser criadas a partir do padrão a seguir: <b>US<Número da <i>User story</i>>-<Descrição> ou TS<Número da <i>Technical story</i>>-<Descrição></b>. Onde US representa as histórias de usuário e TS histórias técnicas. 

Exemplos: 
* “<b>US01-<i>Login</i></b>”
* "<b><i>US07-FilterCompany</i></b>"

### 2.4 Política de Aprovação do Código
<p align="justify">O código será aprovado caso seja funcional e siga todas as especificações da folha de estilo com a aplicação das técnicas de programação, tais como: identação, presença de <i>loggings</i>, comentários, ou seja, o uso de programação defensiva. Além disso o código deverá conter uma cobertura de testes mínima determinada pelo time, assim como, satisfazer todos os requisitos das ferramentas de análise de código. O <i>Scrum Master</i> da <i>sprint</i> em questão deverá revisar o código presente em cada <i>pull request</i>. Caso não obedeça às regras e não seja explicado o não uso de uma das especificações estabelecidas acima o <b><i>Scrum Master</i> deverá recusar o <i>pull request</i></b> a <i>branch master</i> e voltar a <i>branch devel</i> para a última versão estável.</p>
