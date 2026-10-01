#include <iostream>
using namespace std;

int main() {
    double nota;
    double suma = 0;
    double promedio;
    int aprobados = 0;
    char repetir;
    do {

// Reiniciamos los datos para cada consulta
        suma = 0;
        aprobados = 0;
        cout << "--------------------------------------\n";
        cout << "    REGISTRO DE CALIFICACIONES\n";
        cout << "--------------------------------------\n";

// ------------------------------------
// 1. CICLO FOR
// Solicitar las notas de 5 estudiantes
// ------------------------------------
        for (int estudiante = 1; estudiante <= 5; estudiante++) {
        cout << "Ingrese la nota del estudiante "
                 << estudiante << ": ";
            cin >> nota;

// ------------------------------------
// 2. CICLO WHILE
// Validar la nota
// ------------------------------------
        while (nota < 0 || nota > 5) {
                cout << "Nota invalida.\n";
                cout << "Ingrese una nota entre 0 y 5: ";
                cin >> nota;
            }

// Acumulador
            suma = suma + nota;

// Contador
            if (nota >= 3.0) {
                aprobados++;
            }
        }

// Calcular promedio
        promedio = suma / 5;
        cout << "\n--------------------------------------\n";
        cout << "              RESULTADOS\n";
        cout << "--------------------------------------\n";
        cout << "Suma de las notas: " << suma << endl;
        cout << "Promedio: " << promedio << endl;
        cout << "Estudiantes aprobados: " << aprobados << endl;
        cout << "Estudiantes reprobados: " 
             << 5 - aprobados << endl;

// =================================================
// 3. CICLO DO-WHILE
// Preguntar si desea repetir
// =================================================
        cout << "\n¿Desea registrar otro grupo? (S/N): ";
        cin >> repetir;
    } while (repetir == 'S' || repetir == 's');
    cout << "\nPrograma finalizado.\n";
    return 0;
}
