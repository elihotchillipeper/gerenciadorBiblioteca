# Sistema de Gerenciamento de Biblioteca

Este programa é um sistema para gerenciar livros e usuários de uma biblioteca. Ele permite o cadatsro e visualização de livros e usuários usando programação orientada a objetos em Python e o pacote de interface padrão do Python `tkinter`.

## Estrutura do Programa

### Classes

#### `ItemBiblioteca`
Classe base que representa um item básico na biblioteca.

- **Atributos:**
  - `titulo`: Título do livro.

#### `Livro`
Subclasse da classe **ItemBiblioteca** que representa um livro.

- **Atributos:**
  - `autor`: O autor do livro.
  - `isbn`: O ISBN do livro.
 
#### `Usuario`
Subclasse da classe **ItemBiblioteca** que representa um usuário.

- **Atributos:**
  - `nome`: O nome do usuário.
  - `matricula`: O número de matricula.

#### `Biblioteca`
Classe que armazena os livros e usuários, inicialmente as listas estão vazias.

- **Atributos:**
  - `livros`: Lista de objetos do tipo `Livro`.
  - `usuarios`: Lista de objetos  do tipo `Usuario`.

- **Métodos:**
  - `adicionar_livro(livro)`: Adiciona um livro à lista.
  - `adicionar_usuario(usuario)`: Adiciona um usuário à lista.
 
#### `GerenciadorDePedidos`
Classe que gerencia as solicitações dos livros.

- **Atributos:**
  - `biblioteca`: Guarda informações da biblioteca.
  - `pedidos`: Lista de pedidos.
 
- **Métodos:**
  - `solicitar_livro(usuario, livro)`: Adiciona um pedido a lista.


 
## Funcionalidades

### 1. Definição das Classes

  - `ItemBiblioteca`: Classe base para itens na biblioteca.

  - `Livro`: Herda de ItemBiblioteca. Adiciona os atributos autor e isbn para representar um livro.

  - `Usuario`: Herda de ItemBiblioteca. Adiciona os atributos matricula para representar um usuário.

  - `Biblioteca`: Contém listas para armazenar livros e usuários. Métodos para adicionar livros e usuários à biblioteca.

  - `GerenciadorDePedidos`: Lida com a solicitação de livros pelos usuários. Mantém uma lista de pedidos e verifica se o livro está disponível na biblioteca antes de adicionar um pedido.



### 2. Interface Gráfica

A interface gráfica é gerenciada pela classe BibliotecaApp, que configura a tela principal e os botões para navegação e cadastro. A navegação é realizada através da troca de telas.

#### Componentes da Interface Gráfica:

  - `__init__`: Configura a interface inicial com um frame principal (main_frame) e botões para navegar para diferentes partes da aplicação.

- `cadastro_livro`:
  - Oculta a tela principal e exibe uma nova para o cadastro de livros.
  - Permite que o usuário insira o título, autor e ISBN do livro.
  - O botão "Salvar" cria um novo objeto Livro, adiciona-o à biblioteca e retorna a tela principal.
  - O botão "Voltar" retorna ao frame principal sem salvar.

- `cadastro_usuario`:

  - Oculta a tela principal e exibe uma nova para o cadastro de usuários.
  - Permite que o usuário insira o nome e a matrícula.
  - O botão "Salvar" cria um novo objeto Usuario, adiciona-o à biblioteca e retorna a tela principal.
  - O botão "Voltar" retorna a tela principal sem salvar.

- `visualizar_livros`:

  - Oculta o frame principal e exibe um novo frame com uma lista de todos os livros cadastrados.
  - Cada livro é exibido com seu título, autor e ISBN.
  - O botão "Voltar" retorna ao frame principal.

- `visualizar_usuarios`:

Oculta o frame principal e exibe um novo frame com uma lista de todos os usuários cadastrados.
Cada usuário é exibido com seu nome e matrícula.
O botão "Voltar" retorna ao frame principal.
voltar:

Método auxiliar para retornar ao frame principal a partir de qualquer tela secundária.














  
