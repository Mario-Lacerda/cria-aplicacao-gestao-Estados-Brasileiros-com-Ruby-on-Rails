# Desafio Dio - Criando uma Aplicação de Gestão de Estados Brasileiros com Ruby On Rails



**projeto abrangente para criar uma aplicação de gestão de estados brasileiros com Ruby on Rails, com muitos códigos e sua aplicabilidade:**



Neste projeto, construiremos uma aplicação que permita gerenciar os estados brasileiros, incluindo sua criação, leitura, atualização e exclusão (CRUD).



### **Pré-requisitos**

- Ruby 2.6 ou superior
- Rails 6 ou superior
- Banco de dados MySQL ou PostgreSQL



criar uma **aplicação de gestão de estados brasileiros** utilizando **Ruby on Rails**. Neste tutorial, vou apresentar os passos para criar um projeto básico que lista os estados do Brasil. Você pode expandir esse projeto adicionando recursos como busca, filtros e páginas de detalhes para cada estado.



## 1. **Configuração Inicial**:



Antes de começar, certifique-se de ter o Ruby on Rails instalado em sua máquina. Se ainda não o fez, siga as instruções de instalação para o seu sistema operacional. Além disso, você precisará de um banco de dados (como MySQL ou PostgreSQL) para armazenar os dados dos estados brasileiros.



## 2. **Criando o Projeto Rails**:



Vamos começar criando um novo projeto Rails para a nossa aplicação de gestão de estados. Abra o terminal e execute o seguinte comando:

```bash
rails new GestaoEstados
```



Isso criará uma estrutura básica para o seu aplicativo, incluindo pastas para modelos, controladores, visualizações e muito mais.



## 3. **Modelagem de Dados**:



### 3.1. Modelo Estado:

Crie um modelo chamado “Estado” com os atributos necessários:

```bash
rails generate model Estado nome:string sigla:string
```



Isso criará um arquivo de migração para criar a tabela “estados” no banco de dados. Execute a migração com:

```bash
rails db:migrate
```



## 4. **Implementando as Funcionalidades**:



### 4.1. Criando Rotas e Controladores:

Crie rotas para os estados no arquivo `config/routes.rb`:

Ruby



```ruby
Rails.application.routes.draw do
  resources :estados
  root 'estados#index'
end
```



Código gerado por IA. Examine e use com cuidado. [Mais informações em perguntas frequentes](https://www.bing.com/new#faq).

Em seguida, crie o controlador para os estados:

```bash
rails generate controller Estados
```



### 4.2. Implementando as Views:

Crie as views para exibir os estados. Por exemplo, crie um arquivo `app/views/estados/index.html.erb` para listar todos os estados:

```erb
<h1>Estados Brasileiros</h1>
<ul>
  <% @estados.each do |estado| %>
    <li><%= estado.nome %> (<%= estado.sigla %>)</li>
  <% end %>
</ul>
```









### **Configuração**

1. Crie um novo aplicativo Rails:

plaintext



```plaintext
rails new estados_brasileiros
```



1. #### Adicione as seguintes gems ao Gemfile:

plaintext



```plaintext
gem 'mysql2' # Se estiver usando MySQL
# Ou
gem 'pg' # Se estiver usando PostgreSQL
```



1. #### Execute `bundle install` para instalar as gems.

   

2. #### Crie o banco de dados:

plaintext



```plaintext
rails db:create
```



### **Modelos**

Vamos criar um modelo `Estado` para armazenar os dados dos estados:

plaintext



```plaintext
rails generate model Estado nome:string sigla:string
```



### **Migrações**

Execute a migração para criar a tabela de estados:

plaintext



```plaintext
rails db:migrate
```



### **Controladores**

Vamos criar um controlador `EstadosController` para gerenciar os estados:

plaintext



```plaintext
rails generate controller Estados
```



### **Rotas**

Adicione as seguintes rotas ao arquivo `config/routes.rb`:

plaintext



```plaintext
Rails.application.routes.draw do
  resources :estados
  root to: "estados#index"
end
```



### **Views**



Crie as views para exibir os estados:



- ### `app/views/estados/index.html.erb`:

plaintext



```plaintext
<h1>Todos os Estados</h1>

<ul>
  <% @estados.each do |estado| %>
    <li><%= link_to estado.nome, estado_path(estado) %></li>
  <% end %>
</ul>
```



- ### `app/views/estados/show.html.erb`:

plaintext



```plaintext
<h1><%= @estado.nome %></h1>

<p>Sigla: <%= @estado.sigla %></p>
```



- ### `app/views/estados/new.html.erb`:

plaintext



```plaintext
<h1>Novo Estado</h1>

<%= form_with(model: @estado) do |form| %>
  <p>
    <%= form.label :nome %><br>
    <%= form.text_field :nome %>
  </p>

  <p>
    <%= form.label :sigla %><br>
    <%= form.text_field :sigla %>
  </p>

  <p>
    <%= form.submit %>
  </p>
<% end %>
```



- ### `app/views/estados/edit.html.erb`:

plaintext



```plaintext
<h1>Editando Estado</h1>

<%= form_with(model: @estado) do |form| %>
  <p>
    <%= form.label :nome %><br>
    <%= form.text_field :nome %>
  </p>

  <p>
    <%= form.label :sigla %><br>
    <%= form.text_field :sigla %>
  </p>

  <p>
    <%= form.submit %>
  </p>
<% end %>
```



### **Testes**

Execute os testes para verificar se o aplicativo está funcionando corretamente:

plaintext



```plaintext
rails test
```



## 5. **Conclusão**:

Com esses passos, você criou a estrutura básica para a sua aplicação de gestão de estados brasileiros utilizando Ruby on Rails. Agora você pode expandir seu projeto adicionando recursos e explorando tutoriais adicionais para aprofundar seus conhecimentos. 

Este é um projeto abrangente que demonstra como criar uma aplicação de gestão de estados brasileiros usando Ruby on Rails. Você pode expandir este projeto adicionando recursos como validações, pesquisa e muito mais.





