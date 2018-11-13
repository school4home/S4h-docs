# Plano de Gerenciamento de Configuração de Software

## Plano de Gerenciamento de Configuração de Software

### Histórico de Revisão

| Data | Versão | Responsável | Mudança realizada |
| :--- | :--- | :--- | :--- |
| **16/03/17** | 0.1 | Caio Nunes, Gustavo Braz | Criação do Documento de Configuração de Software |

### 1 Introdução

O Plano de Gerência de Configuração do School4Home apresenta todas as tarefas do Gerenciamento de configuração e mudanças no projeto, para garantir a sua integridade e manter o domínio das mudanças ocorridas durante o desenvolvimento. Neste documento detalha-se toda a infraestrutura utilizada nesse projeto. São definidos itens como: uma padronização para os documentos, uma ferramenta de controle da instalação da aplicação, preparo do ambiente de desenvolvimento de forma otimizada, integração ferramenta de controle de testes e por fim relatar os resultados da implantação da gerência de configuração de software. Para isso, devem ser seguidas diretrizes apresentadas em tópicos pelo plano de gerência.

#### 1.1 Resultados esperados

Com a implantação deste plano espera-se diminuir as ocorrências de problemas na configuração da aplicação em outros ambientes, além de garantir maior qualidade no desenvolvimento de testes da aplicação, assegurando que as entregas de software aceitas estejam no nível aceitável definido pela equipe de gerência.

#### 1.4 Definições, Acrônimos e Abreviações

| Termo | Significado |
| :--- | :--- |
| _Baseline_ | Conjunto de itens de configuração que conseguiram um estado comprovado de estabilidade. |
| GCS | Gerência de Configuração de _Software_ |
| CR | Solicitação de Mudança \(_Change Request_\) |

### 2 Organização

#### 2.1 Identificação dos documentos

Todos os artefatos produzidos devem manter o nome seguindo o título do artefato sem abreviação. Ex:`Plano de Gerência de Configuração`. Os únicos artefatos que podem ter abreviação são as `Histórias de Usuário`. Neste caso, o nome do artefato deverá ser: `US<Número> - <Nome da história>`.

#### 2.2 Versão dos Artefatos

O versionamento dos artefatos será feito por tabela de Histórico de Versão no próprio documento. Os artefatos podem ser desenvolvidos na ferramenta Google Drive, ou diretamente no Gitbook.

#### 2.3 _Baseline_ do Projeto

A baseline será gerada a cada fim de sprint do projeto, tendo assim um incremento no número da versão do sistema `1.0`, no caso de atualizações e correções de erros em versões passadas, deve-se utilizar o código da versão anterior sendo que o dígito após o "ponto" deve ser acrescido um `1.1`.

#### 2.4 _Branches_

Essa seção determina as políticas de _branches_ utilizada no processo.

* Haverão duas _branches_ principais, a **master** e a **development**;
* A master manterá a versão entregável do projeto;
* A _development_ será utilizada para a equipe de gestão avaliar os _commits_ e coletar as métricas;
* O incremento à master, ocorrerá através de _pull request_ advindo da _branch development_ e será de responsabilidade exclusiva da equipe de gestão;
* O incremento à _development_ ocorrerá através de _pull request_ advindo das _branches_ de desenvolvimento, onde a aceitação ou recusa do _pull request_ será de responsabilidade da equipe de gestão;
* Só poderão ser criadas _branches_ de desenvolvimento apenas se forem relacionadas a casos de usos à serem implementados ou para mudanças no sistema;
* O nome das _branches_ de desenvolvimento devem seguir o modelo `us<número da história de usuário em dois dígitos>_<nome da história de usuário>.` Obs.: Se o nome do caso de uso/mudanças no sistema conter espaços, estes devem ser substituídos por `underline` e todas as letras devem ser minúsculas.

### 4. Commits

#### 4.1 Comentário do _commit_

Os nomes dos commits devem ser relevantes ao conteúdo inserido ou retirado do repositório. Devem ser inscritos em língua Inglesa e conteúdo significativo, suficiente para identificação do que e onde houve alteração de código.

> Exemplo: `git commit -m "Added first list of mailing lists in manage subscriptions"`

#### 4.2 Política de Commits

Quando houver pareamento em um _commit_ deve-se usar:

> Exemplo: `git commit --author user_name`

Em que o _user\_name_ é o nome do usuário com o qual está pareando.

> Exemplo: `git commit --author vinisilvacar`

O commit deverá estar associado diretamente a um membro da equipe. No caso de pareamento, o commit deve possuir a assinatura de ambos. O _commit_ deverá ter uma descrição para indicar o que foi solucionado.

Outra forma de editar um _commit_ seria o uso do comando:

> Exemplo: `git commit -s`

Este comando abrirá o editor de texto e deverá seguir o seguinte padrão: O título para o commit, o nome da tarefa em desenvolvimento, uma breve descrição para o que foi feito naquele commit e o `Signed-off-by: "Nome do Usuario" example@email.com` mesmo se o commit foi dado apenas por uma pessoa. Ao fazer pareamento ou dojo deve haver o Signed-off-by com todos os contribuidores.

![Editor de Texto com comando -s](https://raw.githubusercontent.com/wiki/fga-gpp-mds/2017.1-SIGS/images/comandoGitCommitS.png)

#### 4.3 Solicitação de Mudanças

Deve seguir o tópico 4.1 e no conteúdo do _commit_ e deve haver o código da _issue_ gerado pelo Github.

> Exemplo: `git commit -m "issue #X Added first list of mailing lists in manage subscriptions"`

### 5. Ferramentas

A tabela abaixo descreve as ferramentas que serão utilizadas no desenvolvimento do projeto School4Home.

| Ferramenta | Descrição |  |
| :--- | :--- | :--- |
| Travis CI | Integração Contínua |  |
| Git | Controle de Versão |  |
| Github | Serviço Web Hosting Compartilhado |  |
| Python | Linguagem de Desenvolvimento | 3.6.1 |
| Django | Framework de Desenvolvimento Web para Python |  |

#### 6.1 TravisCI

O Travis CI proporciona um ambiente de build padrão e um conjunto padrão de etapas para cada linguagem de programação. É possível personalizar qualquer passo neste processo através do arquivo ''.travis.yml''. O Travis CI usa o arquivo .travis.yml na raiz do repositório para tomar conhecimento sobre o projeto e como a build deve ser executada. O travis.yml pode ser escrito de forma minimalista ou detalhado. Alguns exemplos de que tipo de informação o arquivo .travis.yml pode ter:

* Que linguagem de programação o projeto usa;
* Quais comandos ou scripts devem ser executados antes de cada compilação \(por exemplo, para instalar ou clonar as dependências do projeto\);
* Qual comando é usado para executar o conjunto de testes.

**6.1.1 Motivação**

As principais motivações para a escolha do Travis CI foram:

* Ele é gratuito para repositórios públicos;
* Ser um serviço de Integração Contínua na nuvem que pode ser conectado a repositórios no GitHub;
* Notifica o usuário \(por e-mail\) sobre resultados da build;
* Vasta documentação;
* Rápida curva de aprendizado.

### 

