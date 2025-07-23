# Função para calcular multa quando circula dentro de uma localidade
def calcular_multa_localidade(vel):
    # Se a velocidade for inferior a 50 km/h, não há multa
    if vel < 50:
        return 0
    # Se a velocidade for igual ou superior a 120 km/h, a multa é 320€
    elif vel >= 120:
        return 320
    # Se a velocidade for igual ou superior a 90 km/h, a multa é 120€
    elif vel >= 90:
        return 120
    # Caso contrário (entre 50 km/h e 89 km/h), a multa é 60€
    else:
        return 60

# Função para calcular multa fora da localidade
def calcular_multa_fora_localidade(vel):
    # Se a velocidade for inferior a 50 km/h, não há multa
    if vel < 50:
        return 0
    # Se a velocidade for igual ou superior a 120 km/h, a multa é 120€
    elif vel >= 120:
        return 120
    # Se a velocidade for superior a 90 km/h, a multa é 60€
    elif vel > 90:
        return 60
    # Caso contrário (abaixo de 90 km/h), não há multa
    else:
        return 0

# Função para calcular multa na autoestrada
def calcular_multa_autoestrada(vel):
    # Se a velocidade for inferior a 50 km/h, não há multa
    if vel < 50:
        return 0
    # Se a velocidade for superior a 175 km/h, a multa é 360€
    elif vel > 175:
        return 360
    # Se a velocidade for superior a 150 km/h, a multa é 120€
    elif vel > 150:
        return 120
    # Se a velocidade for superior a 120 km/h, a multa é 60€
    elif vel > 120:
        return 60
    # Caso contrário (até 120 km/h), não há multa
    else:
        return 0

# Função principal que controla todo o programa
def main():
    while True:  # Ciclo infinito para permitir várias verificações até o utilizador sair
        # Menu de escolha para o utilizador
        print('\nOnde circulava o veículo?')
        print('1 - Localidade')
        print('2 - Fora da localidade')
        print('3 - Autoestrada')
        print('0 - Sair')
        
# Tentativa de ler a opção do utilizador e validar se é um número
 try:
         opcao = int(input('Introduza o local: '))
      except ValueError:
            # Caso o utilizador não introduza um número, mostra erro e volta ao início do ciclo
            print('Entrada inválida! Introduza um número.')
            continue

# Se a opção for 0, termina o programa
if opcao == 0:
            print('Programa encerrado.')
            break

 # Pede ao utilizador a velocidade do veículo
 velocidade = int(input('Introduza a velocidade do veículo (km/h): '))

# Inicializa a variável multa com 0
  multa = 0

 # Decide qual função chamar consoante a opção escolhida
 if opcao == 1:
            multa = calcular_multa_localidade(velocidade)
    elif opcao == 2:
            multa = calcular_multa_fora_localidade(velocidade)
     elif opcao == 3:
            multa = calcular_multa_autoestrada(velocidade)
     else:
   # Caso a opção seja inválida, mostra mensagem e volta ao menu
      print('Opção inválida!')
         continue

 # Mostra o resultado da multa
 if multa == 0:
         print('Não há multa a pagar.')
     else:
        print(f'Multa a pagar: {multa}€')

# Ponto de entrada do programa: só executa main() se for corrido diretamente
if __name__ == '__main__':
    main()
