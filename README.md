# Funções
criando_funcoes
# VA = 5%
#Esse comentário indica que o valor do Vale Alimentação (VA) é 5% do salário bruto.
# VT = 6%
#Similarmente, esse comentário indica que o valor do Vale Transporte (VT) é 6% do salário bruto.
# INSS = 11%
# Aqui, o comentário informa que o desconto do INSS é 11% do salário bruto.
# Auxilio creche = 15%
# Esse comentário especifica que o auxílio-creche é 15% do salário bruto.
from funcoes_funcionario import *
#Essa linha importa todas as funções definidas no módulo funcoes_funcionario. Essas funções provavelmente contêm lógica para calcular os descontos e o salário líquido.
nome = input("Digite o nome do funcionário: ")
#Solicita ao usuário que digite o nome do funcionário e armazena o valor na variável nome.
salario_bruto = float(input("Digite o salário bruto: R$ "))
# Solicita ao usuário que digite o salário bruto (como um número decimal) e armazena o valor na variável salario_bruto.
VA = desconto_va(salario_bruto)
VT = desconto_vt(salario_bruto)
INSS = desconto_inss(salario_bruto)
#Essas linhas calculam os descontos específicos (VA, VT e INSS) com base no salário bruto.
CRECHE = 0.0
#Inicializa a variável CRECHE com o valor 0.0.
filhos = ''
while filhos != 'S' and filhos != 'N':
#verifica se o usuário possui filhos e, se sim, calcula o desconto do auxílio-creche.
    filhos = input("Você possui filhos? (S) Sim | (N) Não: ").upper()
    if filhos != 'S' and filhos != 'N':
        print("Você só pode digitar (S) ou (N).")
if filhos == 'S':
    CRECHE = desconto_creche(salario_bruto)
#As linhas finais exibem o salário líquido e o total de descontos.
print(f"{nome} seu salário liquido é R$ {salario_liquido(salario_bruto, INSS, VA, VT, CRECHE)}")
print(f"Total de descontos R$ { total_descontos(INSS, VA, VT, CRECHE) }")
