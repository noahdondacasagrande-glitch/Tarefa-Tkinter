oi professora, só queria destacar que o trabalho foi feito usando IA, porque, namoral, dois dias para aprender uma extensão inteira de Python é complicado,

prompts: Estou fazendo um trabalho de programação, preciso que tome como base a ideia de que a parte 2 de pesquisa já foi feita, estará no arquivo docs, e quero que crie informações inexistentes para os pontos 7, 7.1 e 7.2.O comando para o exercício estará nas imagens, se não conseguir ler ou identificar alguma parte me informe e irei tirar as fotos novamente, e utilizar o arquivo do draw.io para fazer o design da página.Faça todo o código utilizando python com auxílio do Tkinter.

Tasky - Gerenciador de Tarefas Estudantil

Visão Geral O Tasky é um gerenciador de tarefas desenvolvido em Python com a biblioteca Tkinter, projetado para ajudar estudantes a organizarem compromissos de estudo com facilidade, mantendo o armazenamento dos dados em arquivo local.

Objetivo Permitir o cadastro, consulta, edição e exclusão de tarefas (contendo texto, data e hora) com garantia de persistência após o fechamento do aplicativo.

Público-Alvo Estudantes que necessitam gerenciar seus prazos e compromissos acadêmicos.

Funcionalidades Principais

    Cadastro de tarefas em janela dedicada com validação de campos.
    Exibição de tarefas em cartões dinâmicos, ordenados por data e hora.
    Pesquisa por texto ou data.
    Filtros por situação: Todas, Pendentes e Concluídas.
    Edição da tarefa selecionada.
    Exclusão com caixa de confirmação.
    Resumo com contadores de total, pendentes e concluídas.
    Persistência contínua em formato JSON.
    Confirmação de encerramento do programa.

Requisitos do Sistema

    Python 3.8 ou superior
    Tkinter (integrado por padrão nas instalações do Windows e macOS)
    Nenhuma biblioteca externa necessária

Instalação

    Baixe e extraia a pasta do projeto.
    Não é necessário instalar dependências adicionais via gerenciador de pacotes.

Execução Acesse a pasta do projeto e execute:

python main.py

Em alguns ambientes, utilize:

python3 main.py

Instruções de Uso

    Clique no botão "Nova tarefa" localizado no menu lateral.
    Digite a descrição (máximo de 100 caracteres), a data (DD/MM/AAAA) e a hora (HH:MM).
    Salve clicando em "Salvar" ou pressionando Enter.
    Para editar, clique no card desejado na lista (ficará com borda em destaque) e selecione "Editar tarefa".
    Para excluir, selecione o card, clique em "Excluir tarefa" e confirme.
    A busca por palavras ou datas pode ser feita diretamente no campo "Pesquisar" no topo.
    Alterne entre os filtros "Concluídas", "Pendentes" e "Todas" para ajustar a visualização.

Teclas de Atalho

    Enter: Salva a tarefa (na janela de formulário)
    Esc: Fecha a janela sem salvar

Estrutura do Projeto e Descrição dos Arquivos

projeto tkinter/ main.py Ponto de entrada da aplicação interface.py Construção das janelas, cards, formulários e tratamento de eventos visuais dados.py Módulo responsável pela leitura e gravação no arquivo de dados validacoes.py Regras de validação para texto, data e horário dados/ Diretório de armazenamento (contém o arquivo tarefas.json) evidências/ Capturas de tela referentes aos testes do sistema README.md Documentação completa do projeto

Descrição Técnica dos Módulos

    main.py (Ponto de Entrada) Arquivo encarregado de inicializar a aplicação, instanciar a janela principal do Tkinter e disparar o loop principal de eventos (mainloop), garantindo que a interface permaneça ativa e responsiva.
    interface.py (Interface Gráfica e Eventos) Responsável por estruturar a interface do usuário e gerenciar os widgets e componentes gráficos:

    Uso de Widgets do Tkinter e ttk: Label (rótulos), Entry (campos de entrada), Button (botões de ação), Frame (contêineres de organização) e messagebox (caixas modais para avisos e confirmações).
    Gerenciamento de Layout: Utilização do gerenciador grid para disposição bidimensional e organização modular dos elementos.
    Programação Orientada a Eventos: Conexão de ações do usuário (cliques e teclas) a funções callback (Event Listeners).

    dados.py (Persistência de Dados) Módulo que lida com a leitura e gravação das tarefas no diretório dados/tarefas.json a cada adição, alteração ou exclusão.

Exemplo de estrutura em tarefas.json:

[ { "texto": "Estudar para a prova de Matemática", "data": "30/09/2026", "hora": "14:30", "concluída": false } ]

    validacoes.py (Regras e Validação de Entradas) Concentra as checagens necessárias para manter a integridade dos dados:

    Texto: Campo obrigatório, limitando a entrada entre 1 e 100 caracteres.
    Data: Checagem no formato DD/MM/AAAA utilizando datetime.stream() para garantir que a data existe no calendário.
    Hora: Validação no formato HH:MM (intervalo entre 00:00 e 23:59).
    Intercepção de Teclado: Uso de regras de validação para checar caracteres digitados em tempo real.

Limitações do Sistema

    Aplicação desktop local de janela única e sem controle de acesso por login.
    Ausência de sistema de notificações ou alarmes sonoros.
    Caso o arquivo tarefas.json seja corrompido, a aplicação inicializará com a lista vazia.
    Armazenamento restrito ao computador local (sem sincronização em nuvem).

Testes do Sistema O plano de testes, resultados e histórico de correções encontram-se documentados na seção de relatórios do projeto. As evidências em imagem estão salvas no diretório evidências/.

Pesquisa Orientada sobre Tkinter (Relatório Acadêmico)

Equipe: Noah Donda Casagrande e Enrique Kolbe. Divisão de responsabilidades: Pesquisa e programação.

2.1 Questões de Pesquisa

    O que é Tkinter e qual é sua relação com Python e Tcl/Tk? O Tkinter é uma biblioteca do Python que orienta a criação de interfaces gráficas através do Tcl e Tk, ambas originalmente criadas para a construção de interfaces gráficas multiplataforma.
    O que caracteriza uma aplicação orientada a eventos? Explique o papel do mainloop. Ela é caracterizada pela estruturação do fluxo do software de acordo com agentes internos ou externos (eventos). O mainloop entra em cena ao fazer o programa permanecer continuamente ativo aguardando um evento, funcionando como um loop contínuo (while True).
    O que são widgets? Descreva a finalidade dos principais componentes. Os widgets são os componentes gráficos da interface.

    Label: exibe um rótulo de texto ou imagem.
    Entry: exibe uma linha de texto e permite a edição pelo usuário.
    Button: exibe texto/imagem e executa um comando quando pressionado.
    Frame: contêiner usado para agrupar e organizar outros widgets.
    Text: especifica uma sequência de texto multilinhas para exibição.
    Checkbutton: utilizado para controlar uma variável booleana (ativado/desativado).
    Radiobutton: utilizado em grupo para controlar uma única variável compartilhada.
    Combobox: combina uma caixa de texto com uma lista suspensa de opções.
    Treeview: exibe uma coleção hierárquica ou tabular de itens.
    Listbox: exibe uma caixa com seleções possíveis em formato de texto.

    Compare os gerenciadores de geometria pack, grid e place.

    pack: organiza elementos em linhas ou colunas consecutivas. Exemplo: botao1 = tk.Button(janela, text="Botão 1") botao1.pack() botao2 = tk.Button(janela, text="Botão 2") botao2.pack()
    grid: organiza os componentes em uma estrutura bidimensional de linhas e colunas. Exemplo: rótulo.grid(row=0, column=0) botão.grid(row=1, column=0)
    Place: define posições absolutas por coordenadas (x, y). Exemplo: rótulo.place(x=50, y=50)

Incompatibilidade: Não se deve misturar pack e grid dentro do mesmo contêiner, pois isso causa um conflito de redimensionamento infinito e gera erro na execução do programa.

    O que são callbacks e como eventos podem chamar funções? Callbacks são funções passadas como argumentos para outras funções a fim de serem executadas posteriormente. O mecanismo que conecta um evento a uma função callback é denominado Event Listener (ouvinte de evento). O fluxo ocorre em três passos:

    Seleção: escolha do elemento a ser monitorado.
    Escuta: definição do tipo de evento monitorado (ex.: clique ou tecla).
    Execução: fornecimento da função callback que deve rodar quando o evento for disparado.

    Variáveis de Controle no Tkinter

    StringVar: armazena e gerencia cadeias de texto. nome_usuario = tk.StringVar()
    IntVar: armazena e gerencia números inteiros. idade _usuario = tk.IntVar()
    DoubleVar: armazena e gerencia números de ponto flutuante. preco_produto = tk.DoubleVar()
    BooleanVar: armazena e gerencia valores booleanos. aceitou_termos = tk.BooleanVar()

    Validação de Campos

    O uso de validation="key" intercepta as teclas no momento da digitação, verificando a entrada e bloqueando automaticamente caracteres não aceitos.
    Processamento de formulários: utiliza-se .strip() para verificar campos obrigatórios, datetime.strptime() para validação de datas e estruturas condicionais para verificação de limites.
    Exemplo prático: checa-se se cada caractere é um dígito (.isdigit()) ou espaço de remoção. No envio do formulário, a conversão de datas via datetime.strptime() em um bloco try...except trata exceções como ValueError se a data for inválida (ex.: 31/02/2026).

    Uso de messagebox, filedialog e ttk

    messagebox: janelas modais utilizadas para retornar avisos e respostas do usuário, bloqueando a tela até que haja uma ação do botão.
    filedialog: caixa pré-fabricada para navegação e seleção de arquivos no sistema de arquivos.
    ttk: módulo estendido do Tkinter que possibilita a utilização de widgets com visual mais moderno. from tkinter import ttk

    Formas de Persistência (JSON, CSV e SQLite)

    JSON: armazena dados em texto estruturado em chave e valor, sendo ideal para configurações e listas de dicionários.
    CSV: organiza os dados em tabelas separadas por vírgulas, sendo indicado para relatórios exportáveis.
    SQLite: banco de dados relacional completo mantido em um único arquivo (.db), permitindo consultas SQL complexas.

    Usabilidade e Acessibilidade em Interfaces Desktop

    Contraste e Legibilidade: uso de textos escuros em fundos claros e tamanhos de fonte adequados.
    Navegação por Teclado: suporte à alternância de campos via tecla Tab e acionamento por Entre/Espaço.
    Feedback ao Usuário: alertas de confirmação para ações destrutivas e indicação clara de erros de validação.
    Organização: agrupamento de componentes relacionados dentro de Frames para clareza visual.
    Aplicação: definição do foco inicial do cursor no primeiro campo com o método .focus().

    Vantagens e Limitações do Tkinter

    Vantagens: biblioteca nativa do Python (sem necessidade de instalação de terceiros), leveza e sintaxe simples.
    Limitações: visual padrão mais antigo se comparado a interfaces modernas e ausência de componentes nativos avançados para animações.
    Solução de contorno: utilização do módulo ttk para integrar elementos com suporte aos temas do sistema operacional.

    Distribuição e Execução em Outro Computador

    Empacotamento: uso do PyInstaller via terminal para compilar o código Python e suas dependências em um único arquivo executável standalone.
    Dependências: o envio do código-fonte exige o Python no computador de destino; o envio do executável gerado pelo PyInstaller dispensa a instalação do interpretador no cliente.
    Cuidados: utilização de caminhos relativos de arquivos e realização da compilação diretamente no sistema operacional final.

Contribuição https://hub.asimov.academy/blog/o-que-e-tkinter/

https://zup.com.br/blog/programacao-orientada-a-eventos/

https://docs.python.org/3/library/tkinter.ttk.html

https://developer.mozilla.org/pt-BR/docs/Glossary/Callback_function

https://docs.python.org/pt-br/3/library/tkinter.messagebox.html#module-tkinter.messagebox

https://www.hashtagtreinamentos.com/tkinter-no-python?conversion=base-py-go-post&gad_source=1&gad_campaignid=15353425825&gbraid=0AAAAADLlh88WPTJ5js2T8YRzzvBWNQydp&gclid=Cj0KCQjwlNPVBhCMARIsAPZ5RqiL_YqDVYyYjs4FqmmbdZ4-Mo03RaADGRXD5_JF-1Msa-jZXA5NvjcaAsThEALw_wcB
