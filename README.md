class Veiculo:
    def __init__(self, modelo, marca, cor, ano):
        self.modelo = modelo
        self.marca = marca
        self.cor = cor
        self.ano = ano

    def __str__(self):
        return f"Modelo: {self.modelo}, Marca: {self.marca}, Cor: {self.cor}, Ano: {self.ano}"

class Carro(Veiculo):
    pass

class Moto(Veiculo):
    pass

class CadastroVeiculos:
    def __init__(self):
        self.veiculos = {}

    def adicionar_veiculo(self, placa, veiculo):
        self.veiculos[placa] = veiculo

    def consultar_veiculo(self, placa):
        veiculo = self.veiculos.get(placa)
        if veiculo:
            print(f"Informações do veículo com placa {placa}:")
            print(veiculo)
        else:
            print("Veículo não encontrado.")

# Instanciando o cadastro
cadastro = CadastroVeiculos()
cadastro.adicionar_veiculo("ABC1234", Carro("Fusca", "Volkswagen", "azul", 1972))
cadastro.adicionar_veiculo("XYZ5678", Carro("Civic", "Honda", "preto", 2020))
cadastro.adicionar_veiculo("LMN9012", Carro("Mustang", "Ford", "vermelho", 1968))
cadastro.adicionar_veiculo("MOT0001", Moto("CB500", "Honda", "branca", 2018))
cadastro.adicionar_veiculo("MOT0002", Moto("Ninja", "Kawasaki", "verde", 2021))

# Loop para consulta
while True:
    placa_input = input("Digite a placa do veículo (ou 'sair' para encerrar): ").strip()
   
    if placa_input.lower() == 'sair':
        print("Encerrando o programa.")
        break
   
    cadastro.consultar_veiculo(placa_input)
