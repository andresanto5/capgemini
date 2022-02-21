# Github-para-o-desafio-de-programacao
Questões 1 a 3
Cada questão já veio com um exemplo. Basta rodar no terminar python nome_do_arquivo.py ou usar diretamente da IDE de preferência.

Questão 1:
def asterisk():
	number = eval(input("Digite um número: ")) #Recebendo um número inteiro na variável number
	aux = 1 #Variável auxiliar 
	for i in range(number-1, -1, -1): #laço que inicia do tamanho da variável number -1 e vai decrescendo em 1 ponto
		print(" "*i,"*"*aux) #Imprime na tela a quantidade de espaço (valor máximo do laço) e a quantidade de * que vai aumentando a cada interação com a váriavel auxiliar
		aux+=1 #Incremento da variável auxíliar em 1 ponto a cada interação
#Iniciando o programa
asterisk()

Questão 2:
import re #importando a biblioteca de expressão regular

def check_passw(password):
	while True:
		#Usando expressão regular para checar os requisitos mínimos da senha
		digit_error = re.search(r"\d", password) is None
		lowercase_error = re.search(r"[a-z]", password) is None
		uppercase_error = re.search(r"[A-Z]", password) is None
		specialCharacter_error = re.search(r"[!@#$%^&*()-+]", password) is None
		space_error = re.search(r"\s", password) is not None
		
		#Caso algum erro seja encontrado retorna a respectiva ajuda
		if len(password)<6: print(f"Você digitou {len(password)} caracteres e a senha precisa ser no mímino 6 caracteres")
		if digit_error: print("Sua senha deve conter no mínimo 1 digito: ")
		if lowercase_error: print("Sua senha deve conter no mínimo 1 letra em minúsculo: ")
		if uppercase_error: print("Sua senha deve conter no mínimo 1 letra em maiúsculo: ")
		if specialCharacter_error: print("Sua senha deve conter no mínimo 1 caractere especial.\nOs caracteres especiais são: !@#$%^&*()-+\n")
		elif space_error: print("Sua senha não deve ter espaços: ")
		
		else: print("Valid password!"); break #se a seja estiver com os requisitos mínimos acaba o programa
		
		'''
		Verifica se o usuário quer continuar com a senha anterior se se prefere digitar uma nova
		'''
		cont = eval(input("Digite 1 para continuar escrevendo a senha anterior\nOu outro número para escrever uma nova senha"))
		if cont == 1:
			newpassword = input(f"Digite mais {6-(len(password))} caracteres: ")
			password = password+newpassword
			print(f"Sua senha é: {password}")
		else:
			password = input("Digite uma senha válida: ")
			print(f"Sua senha é: {password}")

#Iniciando o programa
password = input("Digite sua senha: ")
check_passw(password)

Questão 3:
palavra = 'ovo'

def extNum(elem, tam2):
	tmp=[]
	cont = tam2
	tam1 =0
	for i in range(len(elem)):
		a =(elem[tam1:tam2])
		if len(a) == cont:
			tmp.append(a)
		tam1+=1
		tam2+=1
	return tmp

def anagramaPerfeito(palavra):
	for letra in range(len(palavra)-1,-1,-1):
		return (palavra[letra])

tmp2 = []

for i in range(len(palavra)):
	tmp2.append(extNum(palavra, i+1))
	#print(tmp2)
cont =0
l=[]
sortedTmp =[]
sorted2 = []
tmp3 = []
contador = 0
for i in tmp2:
	for j in i:
		sortedTmp.append("".join(sorted(j)))
sortedTmp.sort()
for i in range(len(sortedTmp)-1):
	if (sortedTmp[i] == sortedTmp[i + 1]):
		cont+=1

print(cont)
