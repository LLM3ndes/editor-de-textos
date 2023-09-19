#Editor de textos
def menu():
    print("1. Novo arquivo")
    print("2. Abrir arquivo")
    print("3. Editar arquivo")
    print("4. Salvar arquivo")
    print("5. Sair")

def criar_arquivo():
    nome_arquivo = input("Digite o nome do arquivo: ")
    try:
        with open(nome_arquivo, 'w') as arquivo:
            print(f"Arquivo '{nome_arquivo}' criado com sucesso.")
    except Exception as e:
        print(f"Erro ao criar o arquivo: {e}")

def abrir_arquivo():
    nome_arquivo = input("Digite o nome do arquivo: ")
    try:
        with open(nome_arquivo, 'r') as arquivo:
            conteudo = arquivo.read()
            print("\nConteúdo do arquivo:")
            print(conteudo)
    except FileNotFoundError:
        print(f"Arquivo '{nome_arquivo}' não encontrado.")
    except Exception as e:
        print(f"Erro ao abrir o arquivo: {e}")

def editar_arquivo():
    nome_arquivo = input("Digite o nome do arquivo: ")
    try:
        with open(nome_arquivo, 'r') as arquivo:
            conteudo = arquivo.read()
        
        print("\nConteúdo atual do arquivo:")
        print(conteudo)

        novo_conteudo = input("\nDigite o novo conteúdo do arquivo:\n")
        with open(nome_arquivo, 'w') as arquivo:
            arquivo.write(novo_conteudo)
            print("Arquivo editado com sucesso.")
    except FileNotFoundError:
        print(f"Arquivo '{nome_arquivo}' não encontrado.")
    except Exception as e:
        print(f"Erro ao editar o arquivo: {e}")

def salvar_arquivo():
    nome_arquivo = input("Digite o nome do arquivo: ")
    conteudo = input("Digite o conteúdo a ser salvo: ")
    try:
        with open(nome_arquivo, 'w') as arquivo:
            arquivo.write(conteudo)
            print("Arquivo salvo com sucesso.")
    except Exception as e:
        print(f"Erro ao salvar o arquivo: {e}")

while True:
    menu()
    opcao = input("Escolha uma opção: ")
    
    if opcao == '1':
        criar_arquivo()
    elif opcao == '2':
        abrir_arquivo()
    elif opcao == '3':
        editar_arquivo()
    elif opcao == '4':
        salvar_arquivo()
    elif opcao == '5':
        print("Saindo do editor de texto.")
        break
    else:
        print("Opção inválida. Tente novamente.")


