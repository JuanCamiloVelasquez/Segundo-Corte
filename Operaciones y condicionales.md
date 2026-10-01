#include <iostream>
#include <iomanip>   
using namespace std;

int main() {
//---------------- 1. DECLARACIÓN DE VARIABLES ----------------
    float nota;            //nota definitiva del estudiante   (0.0 - 5.0)
    int asistencia;      //porcentaje de asistencia        (0 - 100)
    int categoria;         // 1=Superior  2=Alto  3=Basico  4=Bajo
    cout << fixed << setprecision(1);
    cout << "--- CLASIFICADOR DE DESEMPEÑO ACADEMICO ---" << endl <<endl;

//---------------- 2. LECTURA DE DATOS ----------------
    cout << "Ingrese la nota definitiva (0.0 - 5.0): ";
    cin >> nota;
    cout << "Ingrese el porcentaje de asistencia (0 - 100): ";
    cin >> asistencia;
    cout << endl;

/* ---------------- 3. VALIDACIÓN POR RANGOS ---------------- 
       Usamos el operador lógico || (O): basta con que UNA de las condiciones sea verdadera para que el dato sea invalido.
       return 1 termina el programa indicando "error".                                                                    */
    if (nota < 0.0 || nota > 5.0) {
        cout << "ERROR: La nota debe estar entre 0.0 y 5.0" << endl;
        return 1;
    }
    if (asistencia < 0 || asistencia > 100) {
        cout << "ERROR: La asistencia debe estar entre 0 y 100" << endl;
        return 1;
    }

/*---------------- 4. CLASIFICACIÓN CON else if ---------------- 
      El orden IMPORTA: C++ evalua de arriba hacia abajo y se detiene en la primera condición verdadera.
      Por eso no hace falta escribir (nota >= 4.6 && nota <= 5.0) en el primer caso.*/
    if (nota >= 4.6) {
        categoria = 1;                                       //Superior
    } else if (nota >= 4.0) {
        categoria = 2;                                       //Alto
    } else if (nota >= 3.0) {
        categoria = 3;                                       //Básico
    } else {
        categoria = 4;                                       //Bajo
    }

/*---------------- 5. CONDICIONAL ANIDADO ---------------- 
      Un if dentro de otro if. La regla institucional dice que aunque la nota sea aprobatoria (>= 3.0), el estudiante reprueba si su asistencia es menor al 70%.*/
    bool aprobado;
    if (nota >= 3.0) {
        if (asistencia >= 70) {
            aprobado = true;
        } else {
            aprobado = false; 
            categoria = 4                  
        }
    } else {
        aprobado = false;               
    }
   
/*--------------- 6. MENSAJE CON switch-case ---------------- 
      Switch solo funciona con valores EXACTOS de tipo entero o char. nunca con rangos. Por eso primero convertimos el rango de notas en la variables entera 'categoria'.
      Sin 'break' la ejecución continúa hacia el siguiente case        */
    cout << "-----------------------------------------------" << endl;
    cout << "Nota registrada  : " << nota << endl;
    cout << "Asistencia      : " << asistencia << "%" << endl;
    cout << "Desempeño       : ";
    switch (categoria) {
        case 1:
            cout << "SUPERIOR" << endl;
            cout << "Excelente trabajo, mantenga el ritmo" << endl;
            break;
        case 2:
            cout << "ALTO" << endl;
            cout << "Muy buen resultado, esta cerca del nivel superior" << endl;
            break;
        case 3:
            cout << "BÁSICO" << endl;
            cout << "Aprobado, pero conviene reforzar los temas vistos" << endl;
            break;
        case 4:
            cout << "BAJO" << endl;
            cout << "Debe presentar plan de mejoramiento." << endl;
            break;
        default:
            cout << "SIN CLASIFICAR" << endl;    
    }

//---------------- 7. RESULTADO FINAL (if-else simple) ----------------
    if (aprobado) {
        cout << "Estado            : APROBADO" << endl;
    } else {
        cout << "Estado            : REPROBADO" << endl;
    }
    cout << "-----------------------------------------------" << endl;
    
 return 0;
}
    return 0;
}
