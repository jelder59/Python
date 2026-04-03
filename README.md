# 1. Função para receber as informações e fazer os cálculos.
def calcular_aumento(codigo, salario_atual):
    
    # 2. Estrutura de decisão (if/elif/else)
    if codigo == 1:
        cargo = "Escriturário"
        percentual = 0.50  
    elif codigo == 2:
        cargo = "Secretário"
        percentual = 0.35  
    elif codigo == 3:
        cargo = "Caixa"
        percentual = 0.20  
    elif codigo == 4:
        cargo = "Gerente"
        percentual = 0.10  
    elif codigo == 5:
        cargo = "Diretor"
        percentual = 0.00  
    else:
        print(f"\nAtenção! O código {codigo} é inválido. Digite um número de 1 a 5.")
        return # Para a execução caso o código esteja errado

    # 3. Cálculo
    aumento = salario_atual * percentual
    novo_salario = salario_atual + aumento

    # 4. Imprimir o cálculo
    print("\n---------------------------------------")
    print(f"Cargo selecionado: {cargo}")
    print(f"Salário anterior: R$ {salario_atual:.2f}")
    
    if percentual > 0:
        print(f"Valor do aumento: R$ {aumento:.2f} ({int(percentual * 100)}%)")
    else:
        print("Valor do aumento: Sem aumento para este cargo.")
        
    print(f"Novo salário:     R$ {novo_salario:.2f}")
    print("---------------------------------------\n")


print("\n--- BEM VINDO AO SISTEMA DE CÁLCULO DE AUMENTO ---")

while True: # Laço infinito (até "N")
    print("") 
    codigo_digitado = int(input("Digite o código do cargo (1 a 5): "))
    salario_digitado = float(input("Digite o salário atual: R$ "))

    calcular_aumento(codigo_digitado, salario_digitado)
    
    continuar = input("Deseja realizar um novo cálculo? [S/N]: ").upper() # O '.upper()' garante o 's' minúsculo ou 'S' maiúsculo
    
    if continuar != 'S':
        print("\nSaindo do sistema. Até a próxima! 🚀")
        break # para sair do while True
