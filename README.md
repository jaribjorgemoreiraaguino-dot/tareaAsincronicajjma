# tareaasincronicajjma
"""
Sistema de Vehiculos
Estudiante: [ JARIB MOREIRA A.]
"""

# Sistema de Vehículos – Programación Orientada a Objetos
# Sistema de Vehículos - POO

class Motor:
    """Motor utilizado en los vehículos"""

    def __init__(self, tipo, potencia):
        self._tipo = tipo
        self._potencia = potencia
        self._on = False

    @property
    def tipo(self):
        return self._tipo

    @tipo.setter
    def tipo(self, valor):
        self._tipo = valor

    @property
    def potencia(self):
        return self._potencia

    @potencia.setter
    def potencia(self, valor):
        if valor > 0:
            self._potencia = valor

    def encender_motor(self):
        self._on = True
        print(f"Motor {self._tipo} ON ({self._potencia}HP)")

    def detener_motor(self):
        self._on = False
        print("Motor OFF")

def __str__(self):
        return f"{self._tipo} - {self._potencia}HP"


class Vehiculo:
    """Clase padre Vehiculo"""

    def __init__(self, marca, modelo, year, motor):
        self._marca = marca
        self._modelo = modelo
        self._year = year
        self._motor = motor
        self._on = False

    def encender(self):
        if not self._on:
            self._on = True
            self._motor.encender_motor()
            print(f"{self._marca} {self._modelo} ON")

    def apagar(self):
        if self._on:
            self._on = False
            self._motor.detener_motor()
            print(f"{self._marca} {self._modelo} OFF")

def __str__(self):
        return f"{self._marca} {self._modelo} {self._year} [{self._motor}]"


class Automovil(Vehiculo):
    """Automóvil heredado de Vehiculo"""

    def __init__(self, marca, modelo, year, motor, puertas):
        super().__init__(marca, modelo, year, motor)
        self._puertas = puertas

    def abrir_maletero(self):
        print(f"El maletero del {self._marca} {self._modelo} está abierto.")

    def tocar_claxon(self):
        print("Claxon: ¡BEEP!")

def __str__(self):
        base = super().__str__()
        return f"{base} - {self._puertas} puertas"


class Motocicleta(Vehiculo):
    """Motocicleta heredada de Vehiculo"""

    def __init__(self, marca, modelo, year, motor, cilindraje):
        super().__init__(marca, modelo, year, motor)
        self._cilindraje = cilindraje

    def hacer_caballito(self):
        print("Haciendo caballito!")

    def usar_patada_arranque(self):
        print("Arranque con patada...")
        self._motor.encender_motor()

def __str__(self):
        base = super().__str__()
        return f"{base} - {self._cilindraje}cc"


def main():
    print("=== Sistema de Vehículos ===\n")

    # Motores
    mot1 = Motor("EcoBoost", 180)
    mot2 = Motor("GT-Line", 250)
    mot3 = Motor("MonoSport", 150)
    mot_camaro = Motor("V8 Supercharged", 455)

    # Vehículos
    auto_kia = Automovil("Kia", "Rio", 2022, mot1, 4)
    auto_camaro = Automovil("Chevrolet", "Camaro", 2023, mot_camaro, 2)
    moto_yamaha = Motocicleta("Yamaha", "R15", 2021, mot3, 155)


    # Lista con for
    lista_vehiculos = [auto_kia, auto_camaro, moto_yamaha]

    print("Vehículos creados:")
    for v in lista_vehiculos:
        print(v)

    print("\n--- Pruebas de funcionamiento ---")

    print("\nProbando el Kia Rio:")
    auto_kia.encender()
    auto_kia.abrir_maletero()
    auto_kia.apagar()

    print("\nProbando el Camaro:")
    auto_camaro.encender()
    auto_camaro.abrir_maletero()
    auto_camaro.apagar()

    print("\nProbando Yamaha R15:")
    moto_yamaha.encender()
    moto_yamaha.hacer_caballito()
    moto_yamaha.apagar()

    print("\nFIN DEL PROGRAMA.")


if __name__ == "__main__":
    main()
