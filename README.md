📘 Gerenciador de Clientes — Documentação Técnica para Iniciantes
🧾 Visão Geral
Gerenciador de Clientes é uma aplicação desktop desenvolvida em Python 3 com interface gráfica utilizando Tkinter e persistência de dados via SQLite. O projeto foi criado com fins educacionais para auxiliar iniciantes no aprendizado de programação Python, integração com banco de dados, manipulação de interface gráfica e boas práticas de desenvolvimento modular.

🧩 Funcionalidades
A aplicação permite:

➕ Adicionar novos clientes;

📋 Visualizar clientes cadastrados em formato de tabela;

🔍 Buscar clientes por nome, sobrenome, email ou CPF;

✏️ Atualizar informações de clientes existentes;

❌ Deletar registros do banco de dados.

Todos os dados são armazenados localmente no arquivo clientes.db utilizando SQLite.

🗂️ Estrutura do Projeto

plaintext

gerenciador_clientes/

 Gui.py           # Interface gráfica (Tkinter)
 
 Backend.py       # Lógica de banco de dados (SQLite)
 
 application.py   # Arquivo principal (inicialização do app)
 
 clientes.db      # (Gerado automaticamente) Base de dados SQLite

🔹 Gui.py

Define a classe Gui responsável pela construção da interface gráfica com Tkinter.

Contém os campos de entrada, botões e a tabela (Treeview).

Usa ttk, messagebox, treeview e métodos da classe Backend para realizar as operações.

🔹 Backend.py

Define a classe Backend, responsável pela interação com o banco de dados SQLite.

Contém métodos como:

initDB()

insert()

view()

update()

delete()

search()

🔹 application.py

Arquivo principal que:

Inicializa o banco de dados;

Instancia a interface gráfica (Gui);

Inicia o loop da aplicação (mainloop()).

🛠️ Pré-requisitos

Requisito	Descrição
Python	Versão 3.8 ou superior. Baixar
Tkinter	Incluído por padrão no Python (pode exigir python3-tk no Linux).
SQLite	Integrado ao Python via o módulo sqlite3.
PyInstaller	(Opcional) Para gerar executável .exe.

▶️ Como Executar a Aplicação

1. Clone ou crie os arquivos
Salve os arquivos Gui.py, Backend.py e application.py em uma mesma pasta (ex: gerenciador_clientes/).

2. Verifique se o Python está instalado
No terminal:

python --version

3. Execute a aplicação

cd caminho/para/gerenciador_clientes
python application.py
Uma janela será aberta com a interface do Gerenciador de Clientes.

🖱️ Como Usar
 
Interface

Campos de entrada: Nome, Sobrenome, Email, CPF

Botões:

Adicionar: salva novo cliente no banco

Atualizar: atualiza cliente selecionado

Deletar: remove cliente da base

Buscar: realiza busca com base nos campos preenchidos

Limpar: limpa os campos de entrada

Tabela (Treeview): Exibe todos os clientes cadastrados

📦 Gerando um Executável com PyInstaller
1. Instale o PyInstaller


pip install pyinstaller

2. Gere o executável

cd caminho/para/gerenciador_clientes
pyinstaller --onefile --noconsole application.py
Isso criará um executável dentro da pasta dist/.

3. Executando

./dist/application.exe
A aplicação funcionará sem a necessidade de abrir o terminal.

🧱 Estrutura do Banco de Dados

O arquivo clientes.db contém a tabela clientes com os seguintes campos:

Campo	Tipo	Descrição
id	INTEGER	Chave primária (auto incrementável)
nome	TEXT	Nome do cliente
sobrenome	TEXT	Sobrenome do cliente
email	TEXT	Email do cliente
cpf	TEXT	CPF do cliente

A criação da tabela é automática na primeira execução via Backend.initDB().

❗ Dicas de Solução de Problemas
🐍 Erro: No module named tkinter
No Linux, instale o suporte ao Tkinter:


sudo apt install python3-tk
🧾 Tabela não aparece / não atualiza
Verifique se o arquivo clientes.db está na mesma pasta da aplicação.

Confirme se os registros estão sendo inseridos corretamente (campos obrigatórios).

📘 O Que Você Aprende com Este Projeto
Tópico	O que é aprendido
Python	Classes, módulos, métodos, estrutura de código
SQLite	CRUD com SQL, conexões, uso de queries parametrizadas
Tkinter	Interface gráfica, eventos, widgets (botões, labels, entradas)
Arquitetura	Separação entre interface e lógica de banco de dados
PyInstaller	Geração de executável para distribuição

🚀 Próximos Passos (Sugestões de Melhoria)
✅ Validação de CPF com verificação de formato e dígito verificador.

📤 Exportação de dados para .csv.

🔄 Botão "Recarregar" para mostrar todos os dados após uma busca.

🎨 Melhorias visuais: ícones, temas, responsividade, menus.

