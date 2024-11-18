# Calculadora-basica
''' Desenvolvendo uma calculadora básica
'''
while True:
    num1 = int(input('Digite um numero\n'))
    operador = input('Qual a operacão,"*/+-"\n')
    num2 = int(input('Digite outro numero\n'))
    numerosValidos = None# None para garantir que o usuario digitou algum numero 
    numFloat1 = 0
    numFloat = 0
    resultado = ''
    try:
        numFloat1 = float(num1)
        numFloat = float(num2)  
        numerosValidos = True
    except:
        numerosValidos = None
        
    if numerosValidos is None:    
        print('Digite apenas Números')
        continue # continue para voltar ao input, caso o usuario nao digote números validos
    operadoresPermitidos = '*/+-'
    if operador not in operadoresPermitidos:
        print('Digite um operadopr valido.')
        continue
    if len(operador)>1:
        print('Digite apenas um operador.')
        continue
    print('Realizando seu cálculo')
    if operador == '+':
        resultado = num1 + num2
        print(f'A soma dos valores é, {num1}+{num2} =',resultado )
    elif operador == '-':
        resultado = num1 - num2
        print(f'A soma dos valores é, {num1}-{num2} =',resultado )
    elif operador == '/':
        resultado = num1 / num2
        print(f'A divisão dos valores é, {num1}/{num2} =',resultado )
    elif operador == '*':
       resultado = num1 * num2
       print(f'A multiplicação dos valores é, {num1}*{num2} =',resultado )
    else: 
        print('Não deveroia chegar ate aqui')    

    sair = input('Deseja sair [s]:').lower().startswith('s')# esses dois metodos garante que caso o usuário digite em letra minuscula sera valido, e precisa comecar  com"s"
    if sair == True:
        break    
    else:
        continue
