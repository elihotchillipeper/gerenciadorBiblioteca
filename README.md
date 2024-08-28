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
 
#### `BibliotecaApp`
É a classe da interface gráfica do App da bibliioteca.

- **Atributos:**
  - `root`: Raiz da interface gráfica.
  - `biblioteca`: Instância da classe `Biblioteca`.























  
