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

  - Oculta o frame principal e exibe um novo frame com uma lista de todos os usuários cadastrados.
  - Cada usuário é exibido com seu nome e matrícula.
  - O botão "Voltar" retorna ao frame principal.

- `voltar`:

- Método para retornar a tela principal a partir de qualquer outra tela.

## Roadmap de Execução

### Inicialização do Programa

- O script é executado diretamente (if __name__ == "__main__":).

- Criação da tela Principal:

  - `root`: tk.Tk(): Cria uma instância da janela principal do Tkinter.
  - `app`: BibliotecaApp(root): Cria uma instância da classe BibliotecaApp, passando a janela principal (root) como argumento.
  - `root.mainloop()`: Inicia o loop principal da interface gráfica do Tkinter, aguardando interações do usuário.

### Inicialização da Interface Gráfica

- Construtor da Classe BibliotecaApp

  - `self.root = root`: Armazena a referência à janela principal.
  - `self.biblioteca = Biblioteca()`: Cria uma instância da classe Biblioteca, que gerencia livros e usuários.
  - `self.main_frame = tk.Frame(root)`: Cria um Frame principal que serve como container para outros widgets.
  - `self.main_frame.pack()`: Adiciona o Frame principal à janela.
    
### Criação dos Botões Principais
- Cadastrar Livro
  - `self.cadastro_livro_button = tk.Button(self.main_frame, text="Cadastrar Livro", command=self.cadastro_livro)`: Cria um botão para cadastro de livros, que chama o método cadastro_livro quando clicado.
  - `self.cadastro_livro_button.pack()`: Adiciona o botão ao main_frame.

- Cadastrar Usuário

  - `self.cadastro_usuario_button = tk.Button(self.main_frame, text="Cadastrar Usuário", command=self.cadastro_usuario)`: Cria um botão para cadastro de usuários, que chama o método cadastro_usuario quando clicado.
  - `self.cadastro_usuario_button.pack()`: Adiciona o botão ao main_frame.

- Visualizar Livros
  - `self.visualizar_livros_button = tk.Button(self.main_frame, text="Visualizar Livros", command=self.visualizar_livros)`: Cria um botão para visualizar livros, que chama o método visualizar_livros quando clicado.
  - `self.visualizar_livros_button.pack()`: Adiciona o botão ao main_frame.

- Visualizar Usuários
  - `self.visualizar_usuarios_button = tk.Button(self.main_frame, text="Visualizar Usuários", command=self.visualizar_usuarios)`: Cria um botão para visualizar usuários, que chama o método visualizar_usuarios quando clicado.
  - `self.visualizar_usuarios_button.pack()`: Adiciona o botão ao main_frame.

### Interações do Usuário e Manipulação de Dados

- Cadastro de Livros
  - Ação do Usuário
  - O usuário clica no botão "Cadastrar Livro".

- Método `cadastro_livro`:
  - `self.main_frame.pack_forget()`: Esconde o main_frame.
  - Cria uma novo tela para cadastro de livros (cadastro_livro_frame).
  - Adiciona campos de entrada (Título, Autor, ISBN) e botões (Salvar e Voltar) ao cadastro_livro_frame.

- Método `salvar_livro`:
  - Obtém os valores dos campos de entrada.
  - Cria uma instância de Livro com esses valores.
  - Adiciona o livro à biblioteca (self.biblioteca.adicionar_livro(novo_livro)).
  - Esconde o cadastro_livro_frame e exibe o main_frame.

- Método voltar:
  - Esconde o cadastro_livro_frame e exibe o main_frame.
  - Cadastro de Usuários

- Ação do Usuário
  - O usuário clica no botão "Cadastrar Usuário".
  - Método cadastro_usuario
  - self.main_frame.pack_forget(): Esconde o main_frame.
  - Cria um novo Frame para cadastro de usuários (cadastro_usuario_frame).
  - Adiciona campos de entrada (Nome, Matrícula) e botões (Salvar e Voltar) ao cadastro_usuario_frame.
  - Método salvar_usuario
  - Obtém os valores dos campos de entrada.
  - Cria uma instância de Usuario com esses valores.
  - Adiciona o usuário à biblioteca (self.biblioteca.adicionar_usuario(novo_usuario)).
  - Esconde o cadastro_usuario_frame e exibe o main_frame.

- Método voltar
  - Esconde o cadastro_usuario_frame e exibe o main_frame.
  - Visualização de Livros

- Ação do Usuário
  - O usuário clica no botão "Visualizar Livros".

- Método visualizar_livros
  - `self.main_frame.pack_forget()`: Esconde o main_frame.
  - Cria um novo Frame para visualização de livros (visualizar_livros_frame).
  - Adiciona labels para cada livro presente na biblioteca ao visualizar_livros_frame.
- Método voltar
  - Esconde o visualizar_livros_frame e exibe o main_frame.

- Visualização de Usuários

  - Ação do Usuário
  - O usuário clica no botão "Visualizar Usuários".

- Método `visualizar_usuarios` 
  - `self.main_frame.pack_forget()`: Esconde o main_frame.
  - Cria um novo Frame para visualização de usuários (visualizar_usuarios_frame).
  - Adiciona labels para cada usuário presente na biblioteca ao visualizar_usuarios_frame.

- Método voltar
  - Esconde o visualizar_usuarios_frame e exibe o main_frame.

### Encerramento
  - O loop principal do Tkinter (root.mainloop()) continua rodando até que o usuário feche a janela principal. A interface gráfica responde a ações do usuário, atualizando a tela conforme os métodos são chamados.

## Manual de Instalação e Uso

### Dependências

Para executar o programa, você precisará das seguintes dependências:

  - `tkinter`: Biblioteca para a criação da interface gráfica.
  - 
### Instalação
O tkinter geralmente já está incluído com a instalação padrão do Python. No entanto, caso precise instalar ou atualizar o tkinter, siga as instruções abaixo:

- Verifique se o tkinter já está instalado:

  - Abra um terminal ou prompt de comando e execute o seguinte comando para verificar se o tkinter está disponível:
    - python -m tkinter

### Instalação do tkinter no Windows e Linux:

- **Windows:** Normalmente não é necessário instalar separadamente. Certifique-se de que o Python foi instalado corretamente.
- **Ubuntu/Debian:**
    - sudo apt-get install python3-tk

### Inicialização
Para iniciar o programa, siga os passos abaixo:

- Salve o código fornecido em um arquivo chamado gerenciadorBiblioteca_app.py.

- Abra um terminal e navegue até o diretório onde o arquivo gerenciadorBiblioteca_app.py está localizado.

- Execute o programa com o seguinte comando:
    - python gerenciadorBiblioteca_app.py

### Uso
Aqui está um guia para utilizar o programa:

#### Tela Inicial:

- Após iniciar o programa, você verá uma tela inicial com quatro botões:

  - Cadastrar Livro
  - Cadastrar Usuário
  - Visualizar Livros
  - Visualizar Usuários

#### Cadastrar Livro:

- Clique no botão "Cadastrar Livro".
- Preencha os campos Título, Autor, e ISBN.
- Clique no botão "Salvar" para adicionar o livro à biblioteca.
- Clique em "Voltar" para retornar à tela inicial.

#### Cadastrar Usuário:

- Clique no botão "Cadastrar Usuário".
- Preencha os campos Nome e Matrícula.
- Clique no botão "Salvar" para adicionar o usuário à biblioteca.
- Clique em "Voltar" para retornar à tela inicial.

#### Visualizar Livros:

- Clique no botão "Visualizar Livros".
- Você verá uma lista de todos os livros cadastrados, com suas informações.
- Clique em "Voltar" para retornar à tela inicial.

#### Visualizar Usuários:

- Clique no botão "Visualizar Usuários".
- Você verá uma lista de todos os usuários cadastrados, com suas informações.
- Clique em "Voltar" para retornar à tela inicial.























