# AtividadeDepuracao
# Constantes:

const int PORT = 8080 #porta de entrada do servidor

const String CSV = “data_tasks.csv” #CSV

const int MAX = 5000 #limite máximo

# Variáveis:

vetor String ids = String[MAX] #limite máximo de ids

vetor String titulos = String[MAX] #limite máximo de titulos

vetor String descrs = String[MAX] #limite máximo de descrs

vetor int status = int[MAX] #limite máximo de status

vetor long criados = long[MAX] #limite máximo de criados

int n = 0;

# Fluxo de código

psvm → carregar( ); → Cria um objeto server → define contexto para “/” como um objeto de RootHandler → define um contexto para “/api/tasks” como um objeto de ApiTasksHandler → define o executor como “null” ou padrão → imprime o caminho do servido no console → inicia o servidor

## carregar( );

1. n = 0;
2. Path p = CSV #O caminho p recebe o CSV(”data_tasks.csv”)
3. se não forem encontrados arquivos existentes no caminho p retorna vazio.
4. le os textos de um fluxo de entrada armazenando em um buffer br
5. cria uma variavel Line para armazenar as linhas
6. le linha por linha até encontrar uma linha com valor null(ou seja quando as linhas acabarem)
7. se a linha está vazia ou a linha começa com “id;” continua
8. criar um vetor String a
9. divide a linha em partes e armazena essas partes no vetor a
10. se a linha não tiver ao menos 5 partes ela é descartada
11. se já tiver carregado a quantidade máxima, para o carregamento da página
12. ids, titulos, descrs, status e criados recebem os valores do CSV
13. n++ (incrementa o contador de registros)
14. se ocorrer algum erro de leitura imprime no console

em resumo esse método serve para carregar arquivos salvos no CSV

## RootHandler( );

1. Define que o método usado será o metodo GET
2. converte dados do HTML em UTF-8
3. Define que o navegador vai interpretar o arquivo em HTML UTF-8

## ApiTasksHandler( );

1. Identifica o método HTTP e a rota acessada
2. dependendo do métodoe do caminho, executado os dados armazenados nas arrays de lista de tarefas

# Avaliação do projeto:
é um projeto que abre um servidor local e chama um HTML CSS JavaScript para criar um task manager interativo que consegue salvar CSV da lista do usuário para que ele consiga abrir mais tarde, o código é bem extenso e não possui divisão de classes, o que eu proponho para a melhora desse sistema é trabalhar nele de forma orientada a objetos.
