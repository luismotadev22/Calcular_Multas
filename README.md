# Função para calcular multa quando circula na localidade
def calcular_multa_localidade(vel):
    # Se a velocidade for menor que 50 km/h, não há multa
    if vel < 50:
        return 0
    # Se a velocidade for maior ou igual a 120 km/h, multa é 320€
    elif vel >= 120:
        return 320
    # Se a velocidade for maior ou igual a 90 km/h, multa é 120€
    elif vel >= 90:
        return 120
    # Caso contrário (acima de 50 até 89), multa é 60€
    else:
        return 60

# Função para calcular multa fora da localidade
def calcular_multa_fora_localidade(vel):
    # Se for abaixo de 50, não há multa
    if vel < 50:
        return 0
    # Se for 120 ou mais, multa é 120€
    elif vel >= 120:
        return 120
    # Se for acima de 90, multa é 60€
    elif vel > 90:
        return 60
    # Caso contrário, não há multa
    else:
        return 0

# Função para calcular multa na autoestrada
def calcular_multa_autoestrada(vel):
    # Se for abaixo de 50, não há multa
    if vel < 50:
        return 0
    # Se for acima de 175, multa é 360€
    elif vel > 175:
        return 360
    # Se for acima de 150, multa é 120€
    elif vel > 150:
        return 120
    # Se for acima de 120, multa é 60€
    elif vel > 120:
        return 60
    # Caso contrário, não há multa
    else:
        return 0

# Função principal que controla o programa
def main():
    while True:  # Loop para permitir várias verificações até o utilizador sair
        print('\nOnde circulava o veículo?')
        print('Escolha uma opção:')
        print('1 - Localidade')
        print('2 - Fora da localidade')
        print('3 - Autoestrada')
        print('0 - Sair')
        
 # Pede ao utilizador para escolher a localização
 opcao = int(input('Introduza o local: ').strip().upper()[0]
        
  # Se a opção for 0, termina o programa
  if opcao == 0:
            print('Programa encerrado.')
            break
        
  # Pede ao utilizador a velocidade do veículo
 velocidade = int(input('Introduza a velocidade do veículo (km/h): '))
        
 # Variável para guardar a multa
  multa = 0
    
 # Decide qual função usar conforme a escolha do utilizador
  if opcao == 1:
            multa = calcular_multa_localidade(velocidade)
        elif opcao == 2:
            multa = calcular_multa_fora_localidade(velocidade)
        elif opcao == 3:
            multa = calcular_multa_autoestrada(velocidade)
       else:
          print('Opção inválida!')
            continue
        
   # Mostra a multa (ou indica que não há multa)
  if multa == 0:
          print('Não há multa a pagar.')
    else:
           print(f'Multa a pagar: {multa}€')

# Ponto de entrada do programa
if __name__ == '__main__':
    main()
