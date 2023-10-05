#incluir<bits/stdc++.h>
using namespace std;

class Empleado {
private:
    string Nombre;
    string Apellido;
    string Domicilio;
    int CantidadHijos;
    double SueldoBasico;
    int Antiguedad;

    // Función privada para calcular las deducciones
    double CalcularDeducciones() {
        double jubilacion = SueldoBasico * 0.11;
        double obraSocial = SueldoBasico * 0.03;
        double inssjp = SueldoBasico * 0.03;
        double deduccionesTotales = jubilacion + obraSocial + inssjp;
        return deduccionesTotales;
    }

public:
    // Constructor
    Empleado(string nombre, string apellido, string domicilio, int hijos, double sueldo, int antiguedad) {
        Nombre = nombre;
        Apellido = apellido;
        Domicilio = domicilio;
        CantidadHijos = hijos;
        SueldoBasico = sueldo;
        Antiguedad = antiguedad;
    }

    // Función para calcular el sueldo neto
    double CalcularSueldoNeto() {
        double deducciones = CalcularDeducciones();
        double sueldoNeto = SueldoBasico - deducciones;
        return sueldoNeto;
    }

    // Función para mostrar la información del empleado
    void MostrarInformacion() {
        cout << "Nombre: " << Nombre << " " << Apellido << endl;
        cout << "Domicilio: " << Domicilio << endl;
        cout << "Cantidad de hijos: " << CantidadHijos << endl;
        cout << "Sueldo Básico: $" << SueldoBasico << endl;
        cout << "Antigüedad: " << Antiguedad << " años" << endl;
        cout << "Sueldo Neto: $" << CalcularSueldoNeto() << endl;
    }
};

int main() {
    Empleado empleado("Juan", "Rodriguez", "123 Main St", 3, 500000, 12);
    empleado.MostrarInformacion();

    return 0;
}
