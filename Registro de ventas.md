#include <iostream>
using namespace std;

int main() {
    double venta;
    double totalVentas;
    int ventasGrandes;
    char repetir;
    do {
    
// Reiniciar los valores para una nueva jornada
        totalVentas = 0;
        ventasGrandes = 0;
        cout << "======================================\n";
        cout << "         REGISTRO DE VENTAS\n";
        cout << "======================================\n\n";
// ==========================================
// CICLO FOR
// Registrar 5 ventas
// ==========================================
        for (int ventaNumero = 1; ventaNumero <= 5; ventaNumero++) {
             cout << "Ingrese el valor de la venta "
                 << ventaNumero << ": $";
            cin >> venta;
// ==========================================
// CICLO WHILE
// Validar que la venta sea mayor que 0
// ==========================================
            while (venta <= 0) {
                cout << "El valor debe ser mayor que $0.\n";
                cout << "Ingrese nuevamente la venta: $";
                cin >> venta;
            }
 // =========================================
 // ACUMULADOR
 // ==========================================
            totalVentas = totalVentas + venta;

// ==========================================
// CONTADOR
// ==========================================
            if (venta > 100000) {
                ventasGrandes++;
            }
        }

// ==========================================
// RESULTADOS
// ==========================================
        cout << "\n======================================\n";
        cout << "              RESUMEN DE VENTAS\n";
        cout << "======================================\n";
        cout << "Total vendido: $" 
             << totalVentas << endl;
        cout << "Ventas superiores a $100.000: "
             << ventasGrandes << endl;

// =======================================
// CICLO DO-WHILE
// Preguntar si desea repetir
// ==========================================
        cout << "\n¿Desea registrar otra jornada? (S/N): ";
        cin >> repetir;

   } while (repetir == 'S' || repetir == 's');
      cout << "\nPrograma finalizado.\n";
      return 0;
}
  
