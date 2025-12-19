## 🎓 Sistema Acadêmico Colaborativo
- Este repositório contém a infraestrutura backend de um sistema de gestão acadêmica que permite a visualização e atualização de notas e perfis de utilizadores.

## 🛠️ Tecnologias e Ferramentas
- **Linguagem:** Python 3

- **Framework Web:** Flask

- **Segurança:** Flask-CORS para gestão de acessos cross-origin

- **Base de Dados:** Hospedado de forma local em ```data.json```

## 📱 Funcionalidades da Interface
- **Autenticação Simples:** Sistema de login baseado no email e password definidos no ```data.json```.

- **Painel do Professor:** Interface para visualizar a lista de todos os alunos e editar as notas AVA 1, AVA 2 e AVA 3.

- **Painel do Estudante:** Visualização individual de notas e informações da turma (ex: Turma A ou B).

- **Sincronização em Tempo Real:** Comunicação via JSON com o servidor Flask para garantir que os dados estão atualizados.

## 📋 Funcionalidades do Servidor
- **Gestão de Perfis:** Distinção entre utilizadores via tokens (Professor/Estudante).

- **Gestão de Notas:** Armazenamento de notas (AVA 1, AVA 2, AVA 3).

- **Normalização de Dados:** O servidor garante que todos os registros possuam a estrutura de notas correta ao carregar o arquivo.

## 🔌 API Endpoints
| Método | Endpoint | Descrição |
| :--- | :--- | :--- |
| **GET** | `/students` | Retorna a lista completa de utilizadores. |
| **POST** | `/students/update` | Atualiza ou cria um utilizador baseado no email. |

## 📂 Estrutura de Dados
O sistema utiliza um modelo de dados baseado em JSON com os seguintes campos principais:

- ```name```: Nome do utilizador.

- ```email```: Identificador único (usado para login/atualização).

- ```password```: Senha de acesso.

- ```token```: Identificador de nível de acesso (1 para Professor, 2 para Aluno).

- ```school_grades```: Objeto contendo as notas das avaliações.

## 🛠️ Requisitos de Configuração
Para que o cliente comunique corretamente com o servidor:

- **Endereço do Servidor:** O cliente deve apontar para http://localhost:5000 (ou o IP da máquina onde o servidor Flask está sendo executado).

- **CORS:** O servidor já está configurado para aceitar pedidos de origens diferentes via flask_cors, permitindo o desenvolvimento local da interface.

## 🖥️ Como Executar (Server)
**Pré-requisitos**
- Python 3 instalado.
- Pip (gestor de pacotes).

**Instalação**
- Instale as dependências necessárias:

```bash
pip install -r requirements.txt
```

- Certifique-se de que o arquivo ```data.json``` está na mesma pasta que o ```server.py```.

**Iniciar o Servidor**
- Execute o comando:

```bash
python server.py
```
O servidor ficará disponível em ```http://localhost:5000```.

## 🧑‍💻 Como Executar (Client)
**Pré-requisitos**
- Python 3 instalado.
- Pip (gestor de pacotes).

**Instalação**
- Instale as dependências:

```bash
pip install -r requirements.txt
```

**Iniciar o Sistema**
- Execute o comando:

```bash
python login_window_ui.py
```

**Realize o login utilizando uma das contas de teste:**
 - Professor: ```professor@brispace.com``` | Senha: ```ensino```
 - Estudante: ```estudante1@brispace.com``` | Senha: ```aluno1```
