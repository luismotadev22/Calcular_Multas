def calcular_multa_localidade(vel):
    if vel < 50:
        return 0
    elif vel >= 120:
        return 320
    elif vel >= 90:
        return 120
    else:
        return 60

def calcular_multa_fora_localidade(vel):
    if vel < 50:
        return 0
    elif vel >= 120:
        return 120
    elif vel > 90:
        return 60
    else:
        return 0

def calcular_multa_autoestrada(vel):
    if vel < 50:
        return 0
    elif vel > 175:
        return 360
    elif vel > 150:
        return 120
    elif vel > 120:
        return 60
    else:
        return 0

def main():
    while True:
        print('\nOnde circulava o veículo?')
        print('1 - Localidade')
        print('2 - Fora da localidade')
        print('3 - Autoestrada')
        print('0 - Sair')
        
 try:
    opcao = int(input('Introduza o local: '))
    except ValueError:
    print('Entrada inválida! Introduza um número.')
    continue

if opcao == 0:
            print('Programa encerrado.')
            break

velocidade = int(input('Introduza a velocidade do veículo (km/h): '))

  multa = 0
    if opcao == 1:
            multa = calcular_multa_localidade(velocidade)
        elif opcao == 2:
            multa = calcular_multa_fora_localidade(velocidade)
        elif opcao == 3:
            multa = calcular_multa_autoestrada(velocidade)
        else:
            print('Opção inválida!')
            continue

if multa == 0:
      print('Não há multa a pagar.')
    else:
          print(f'Multa a pagar: {multa}€')

if __name__ == '__main__':
    main()
