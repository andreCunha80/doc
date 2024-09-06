

## Sistema de controle de circulação de títulos da Biblioteca Senai Roberto Simonsen
![banner](https://logodownload.org/wp-content/uploads/2019/08/senai-logo.png)
Este sistema foi criado para controle de circulação de títulos da biblioteca.

### Visão Geral do Projeto
O projeto consiste na criação e integração Frontend/Backend de uma interface gráfica com um banco de dados de biblioteca. 
A interface gráfica foi desenvolvida para ser funcional e de navegação intuitiva. O menu de navegação possibilita que o usuário encontre rapidamente o link para iniciar a autenticação de usuário, o histórico de movimentação de títulos, turma e acervo da biblioteca.

### Ferramentas

### Html, Css e Javascript

HTML define a estrutura do seu conteúdo, CSS determina o estilo e o layout, e JavaScript torna o conteúdo interativo.
### Node.js
A principal característica do Node.js é sua arquitetura assíncrona e orientada por eventos.[8] O runtime do Node.js é single-thread — uma única thread (chamada de Event Loop) é responsável por executar o código Javascript, sem a necessidade de criar novas threads, o que torna o código mais simples de manter.[9] Chamadas que seriam bloqueantes, como entrada/saída, são realizadas de forma assíncrona usando a libuv.

### React
React. js é um framework JavaScript rápido, seguro e escalável. Ele fornece uma experiência fantástica para o usuário e o desenvolvedor.
#### Banco de Dados MySQL
Entre as principais características do Banco de Dados, destacam-se a capacidade de armazenar volumes moderados de dados, pela altíssima confiabilidade e facilidade no armazenamento e na recuperação de dados.

### Ambiente Virtual Python (venv)
O Ambiente Virtual Python é uma instância independente do Python que permite isolar as bibliotecas e dependências de um projeto específico. Cada projeto tem seu próprio ambiente isolado, permitindo a instalação e gerenciamento de versões específicas de bibliotecas e suas dependências. Isso garante que cada projeto tenha um ambiente consistente e estável, sem interferir em outros projetos ou no ambiente global do Python. O principal objetivo dos ambientes virtuais é criar um ambiente isolado para os projetos Python.

### Django
Para facilitar o processo de criação de soluções web, o Django framework abstrai a maioria dos processos árduos e repetitivos de configuração do ambiente de desenvolvimento, como gerenciamento de Banco de Dados, configuração de roteamento de URLs, configurações de autenticação e autorização, dentre outras.

### Características do Sistema

Contém uma interface gráfica e um banco de dados desenvolvido para gerenciar o controle de livros e materiais didáticos na biblioteca do SENAI. O sistema oferece funcionalidades como cadastro, consulta, exclusão, controle de estoque, organização por prateleiras e outras características essenciais para a administração eficiente dos recursos bibliotecários.

Tabelas Implementadas
1- armario

Armazenamento de informações sobre os armários da biblioteca.
2- divisao

Detalhes sobre as divisões dos armários.
3- estoque

Registro do estoque de materiais na biblioteca.
4- material didatico

Informações sobre os materiais didáticos disponíveis.
5- material didatico repografia

Dados específicos sobre materiais didáticos relacionados à reprografia.
6- material didatico turma

Relação entre o material didático e as turmas.
7- movimentacao

Registro das movimentações de materiais na biblioteca.
8- observacao

Observações gerais relacionadas ao banco de dados.
9- observacao material

Observações específicas sobre os materiais.
10- observacao repografia

Observações relacionadas à reprografia.
11- professor

Cadastro de informações sobre os professores.
12- remessa conserto

Detalhes das remessas de materiais para conserto.
13- repografia

Informações sobre os serviços de reprografia disponíveis.
14- solicitacao
Registro das solicitações realizadas na biblioteca.

### Pré-requisitos
- Sistema de gerenciamento de banco de dados MySQL.
- Python3 instalado.
- IDE recomendada: Visual Studio Code (ou outra IDE de sua preferência como PyCharm.).


### Configuração
Clone o repositório:
git clone xxx


### Uso
Este sistema fornece uma interface gráfica para gerenciar livros, materiais didáticos, categorias, movimentações de estoque e fornecedores na biblioteca do SENAI. Abaixo, você encontrará exemplos detalhados de como utilizar cada funcionalidade.


### Contato
Para qualquer dúvida ou suporte técnico, entre em contato através de:
- GitHub Issues
- LinkedIn: https://www.linkedin.com/in/

### Licença
Este projeto é licenciado sob a Licença MIT License.
### Autores
- Alex, André, Caio, Carol, Cícero, Diego, Gabriel, Geovane, Hugo, Vitor, Wendel e ?- Trabalho Inicial - SeuPerfilGitHub
- 
### Contato
Para qualquer dúvida ou suporte técnico, entre em contato através de:
- GitHub Issues
- LinkedIn



30.08.2024

Nesse momento a equipe de desenvolvimento backend está acertando detalhes de configuração no Workbench banco de dados MySql e configuração de ambiente virtual Python para a integração com o framework Django, enquanto o Frontend está definindo a estrutura de layout de interface e funcionalidades para a implementação junto ao banco de dados.

05.08.2024

Atualização project Biblioteca: tratado a questão de manipulação de formulário com o django, modificação do formulário com widgets avançado do django, criado um campo de categoria para que os docentes possa selecionar uma determinada categoria de livros somente para o seu usuário logado, criada uma class cadastro livro para herdar de  BasemodelForm do django,  def __init __self() implementado o javascript para gerenciar a interatividade do usuário quando clicar em categoria, livros, empréstimo  e etc..

06.09.2024

Atualização project Biblioteca: implementada mais medidas de segurança em cadastrar categoria de livros vinculando o usuario logado ao id do livro, para garantir que é mesmo que esta realizando ações e nova funcionalidade de empréstimos de livros adicionada, mais dois formulários criado com django.forms e um criado no braço mesmo em html, funcionalidades de adicionar docente e docentes ja contratados senai.












## Administracao-da-biblioteca-do-SENAI
![banner](https://github.com/NathanSilva4244/Administracao-da-biblioteca-do-SENAI/blob/main/biblioteca_banner.png)

Este repositório contém um banco de dados desenvolvido para gerenciar o controle de livros e materiais didáticos na biblioteca do SENAI. O sistema oferece funcionalidades como cadastro, consulta, exclusão, controle de estoque, organização por prateleiras e outras características essenciais para a administração eficiente dos recursos bibliotecários.


### Tabelas Implementadas
#### 1- armario
Armazenamento de informações sobre os armários da biblioteca.

#### 2- divisao
Detalhes sobre as divisões dos armários.

#### 3- estoque
Registro do estoque de materiais na biblioteca.

#### 4- material didatico
Informações sobre os materiais didáticos disponíveis.

#### 5- material didatico repografia
Dados específicos sobre materiais didáticos relacionados à reprografia.

#### 6- material didatico turma
Relação entre o material didático e as turmas.

#### 7- movimentacao
Registro das movimentações de materiais na biblioteca.

#### 8- observacao 
Observações gerais relacionadas ao banco de dados.

#### 9- observacao material 
Observações específicas sobre os materiais.

#### 10- observacao repografia 
Observações relacionadas à reprografia.

#### 11- professor 
Cadastro de informações sobre os professores.

#### 12- remessa conserto 
Detalhes das remessas de materiais para conserto.

#### 13- repografia
Informações sobre os serviços de reprografia disponíveis.

#### 14- solicitacao
Registro das solicitações realizadas na biblioteca.


### Pré-requisitos
- Sistema de gerenciamento de banco de dados MySQL.
- Python3 instalado.
- IDE recomendada: Visual Studio Code (ou outra IDE de sua preferência.).


### Configuração
Clone o repositório:
git clone xxx


### Uso
Este sistema fornece uma interface de linha de comando para gerenciar livros, materiais didáticos, categorias, movimentações de estoque e fornecedores na biblioteca do SENAI. Abaixo, você encontrará exemplos detalhados de como utilizar cada funcionalidade.


### Licença
Este projeto é licenciado sob a Licença MIT License.


### Autores
- Nathan Silva - NathanSilva4244


### Contato
Para qualquer dúvida ou suporte técnico, entre em contato através de:
- GitHub Issues
- LinkedIn: https://www.linkedin.com/in/


https://www.youtube.com/watch?v=7fEjG4VSXJc&t=89s
