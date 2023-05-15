# Ejercicio Base:
En su labor como programador de software ha sido elegido para el desarrollo de una aplicación de comision para una agencia de motos, que desea calcular el porcentaje de venta de 3 empleados segun las ventas. Esta aplicacion evalúa a los diferentes empleados de forma permanente y calcula el monto de la comision para el empleado. Como información básica de cada empleado se debe registrar el número de identificación, su nombre, la venta total y el salario mensual.

## Aclaraciones:
- Se supondrá que la aplicación solo se requiere para calcular la comision de los empleados.
- Para efectos de mantener la simplicidad del ejemplo no se contemplan manejar persistencia en el almacenamiento de los datos.
- No se realiza validación, ni se verifica calidad en los datos ingresados.

## Historia de usuario en Jira:
### Título: Calcular salario total de empleados de ventas
### Descripción:
Como gerente de recursos humanos, necesito un programa que calcule el salario total de mis empleados de ventas, incluyendo la comisión basada en su venta total, para poder hacer un seguimiento de sus salarios y asegurarme de que están recibiendo una compensación justa por su trabajo.

## Criterios de aceptación:
- El programa debe permitir al usuario ingresar el número de empleados de ventas.
- Para cada empleado, el programa debe solicitar el ID del empleado, el nombre del empleado, la venta total del empleado y el salario mensual del empleado.
- El programa debe calcular la comisión del empleado según las ventas totales, aplicando diferentes porcentajes de comisión según el rango de ventas.
- El salario total de cada empleado debe calcularse sumando el salario mensual y la comisión.
- El programa debe mostrar los detalles del salario total para cada empleado, incluyendo el ID del empleado, el nombre del empleado, la venta total del empleado, el salario mensual del empleado, el porcentaje de comisión y la comisión calculada.

## Tareas:
- Crear un formulario para que el usuario pueda ingresar el número de empleados de ventas.
- Para cada empleado, crear un formulario para que el usuario pueda ingresar el ID del empleado, el nombre del empleado, la venta total del empleado y el salario mensual del empleado.
- Escribir una función que calcule la comisión del empleado según las ventas totales y el rango de ventas.
- Escribir una función que calcule el salario total de cada empleado.
- Escribir una función que muestre los detalles del salario total para cada empleado.

## Nombre del Caso de Uso: Calcular Comisiones de Empleados
Actor(es) Principal(es): Usuario del Sistema
### Breve descripción:
Este caso de uso describe cómo el usuario puede ingresar información sobre los empleados de una empresa, incluyendo su ID, nombre, venta total y salario mensual, para calcular su comisión y salario total en base a una fórmula preestablecida.

## Flujo básico de eventos:
1. El usuario selecciona la opción para calcular comisiones de empleados en el menú principal del sistema.
2. El sistema solicita al usuario ingresar el número de empleados para los cuales se calcularán las comisiones.
3. El usuario ingresa el número de empleados y confirma la selección.
4. Para cada empleado, el sistema solicita al usuario ingresar su ID, nombre, venta total y salario mensual.
5. El usuario ingresa los datos y confirma la selección.
6. El sistema utiliza una fórmula preestablecida para calcular la comisión y el salario total del
empleado en base a su venta total y salario mensual.
7. El sistema muestra al usuario los resultados de los cálculos, incluyendo el ID del
empleado, su nombre, venta total, salario mensual, porcentaje de comisión, comisión y
salario total.
8. El usuario tiene la opción de volver a ingresar los datos de los empleados o salir del
sistema.

## Precondiciones:
- El usuario debe tener acceso al sistema y seleccionar la opción para calcular comisiones
de empleados desde el menú principal.
## Postcondiciones:
- El sistema calcula la comisión y el salario total de cada empleado ingresado por el usuario
y muestra los resultados al usuario.
- El usuario tiene la opción de volver a ingresar los datos de los empleados o salir del
sistema.
<img src = "Captura de pantalla 2023-05-15 093400.png" width="600" height="500">

## Aproximación al Pseudo código:

Algoritmo CalculoComision
	
	// Declaración de variables
	Definir empleados como Entero
	Definir id_empleado, nombre_empleado como Carácter
	Definir venta_total, salario_mensual, porcentaje_comision como Real
	
	// Lectura del número de empleados
	Escribir "Ingrese el número de empleados:"
	Leer empleados
	
	// Bucle para procesar cada empleado
	Para i Desde 1 Hasta empleados Con Paso 1 Hacer
		
		// Lectura de los datos del empleado
		Escribir "Ingrese el ID del empleado ", i, ":"
		Leer id_empleado
		
		Escribir "Ingrese el nombre del empleado ", i, ":"
		Leer nombre_empleado
		
		Escribir "Ingrese la venta total del empleado ", i, ":"
		Leer venta_total
		
		Escribir "Ingrese el salario mensual del empleado ", i, ":"
		Leer salario_mensual
		
		// Cálculo de la comisión y del salario total
		Si venta_total < 500000 Entonces
			porcentaje_comision <- 0.05
		Sino Si venta_total < 1000000 Entonces
				porcentaje_comision <- 0.075
			Sino
				porcentaje_comision <- 0.1
			FinSi
			Fin Si
			
			comision <- venta_total * porcentaje_comision
			salario_total <- salario_mensual + comision
			
			// Impresión de los resultados
			Escribir "Empleado ", i, ":"
			Escribir "ID: ", id_empleado
			Escribir "Nombre: ", nombre_empleado
			Escribir "Venta total: ", venta_total
			Escribir "Salario mensual: ", salario_mensual
			Escribir "Porcentaje de comisión: ", porcentaje_comision
			Escribir "Comisión: ", comision
			Escribir "Salario total: ", salario_total
			
		FinPara
		
FinAlgoritmo





## Codigo en java Programacion Estructurada:

/**
 * Write a description of class EstudianteEstr here.
 * 
 * @author (your name) 
 * @version (a version number or a date)
 */
import java.util.Scanner;

public class CalculoComision {

    public static void main(String[] args) {
        
        Scanner entrada = new Scanner(System.in);
        
        int empleados;
        String id_empleado, nombre_empleado;
        double venta_total, salario_mensual, porcentaje_comision, comision, salario_total;
        
        System.out.print("Ingrese el número de empleados: ");
        empleados = entrada.nextInt();
        
        for (int i = 1; i <= empleados; i++) {
            
            System.out.print("Ingrese el ID del empleado " + i + ": ");
            id_empleado = entrada.next();
            
            System.out.print("Ingrese el nombre del empleado " + i + ": ");
            nombre_empleado = entrada.next();
            
            System.out.print("Ingrese la venta total del empleado " + i + ": ");
            venta_total = entrada.nextDouble();
            
            System.out.print("Ingrese el salario mensual del empleado " + i + ": ");
            salario_mensual = entrada.nextDouble();
            
            if (venta_total < 500000) {
                porcentaje_comision = 0.05;
            } else if (venta_total < 1000000) {
                porcentaje_comision = 0.075;
            } else {
                porcentaje_comision = 0.1;
            }
            
            comision = venta_total * porcentaje_comision;
            salario_total = salario_mensual + comision;
            
            System.out.println("Empleado " + i + ":");
            System.out.println("ID: " + id_empleado);
            System.out.println("Nombre: " + nombre_empleado);
            System.out.println("Venta total: " + venta_total);
            System.out.println("Salario mensual: " + salario_mensual);
            System.out.println("Porcentaje de comisión: " + porcentaje_comision);
            System.out.println("Comisión: " + comision);
            System.out.println("Salario total: " + salario_total);
            
        }
        
        entrada.close();

    }

}


## Codigo en java Programacion Orientada a Objetos:

import java.util.Scanner;

public class POO {
    
    private String id_empleado;
    private String nombre_empleado;
    private double venta_total;
    private double salario_mensual;
    private double porcentaje_comision;
    private double comision;
    private double salario_total;
    
    public POO(String id, String nombre, double venta, double salario) {
        this.id_empleado = id;
        this.nombre_empleado = nombre;
        this.venta_total = venta;
        this.salario_mensual = salario;
        
        if (venta_total < 500000) {
            this.porcentaje_comision = 0.05;
        } else if (venta_total < 1000000) {
            this.porcentaje_comision = 0.075;
        } else {
            this.porcentaje_comision = 0.1;
        }
        
        this.comision = venta_total * porcentaje_comision;
        this.salario_total = salario_mensual + comision;
    }
    
    public String getId() {
        return id_empleado;
    }
    
    public String getNombre() {
        return nombre_empleado;
    }
    
    public double getVentaTotal() {
        return venta_total;
    }
    
    public double getSalarioMensual() {
        return salario_mensual;
    }
    
    public double getPorcentajeComision() {
        return porcentaje_comision;
    }
    
    public double getComision() {
        return comision;
    }
    
    public double getSalarioTotal() {
        return salario_total;
    }
    
    public void imprimirInformacion() {
        System.out.println("Empleado " + id_empleado + ":");
        System.out.println("Nombre: " + nombre_empleado);
        System.out.println("Venta total: " + venta_total);
        System.out.println("Salario mensual: " + salario_mensual);
        System.out.println("Porcentaje de comisión: " + porcentaje_comision);
        System.out.println("Comisión: " + comision);
        System.out.println("Salario total: " + salario_total);
    }

    public static void main(String[] args) {
        
        Scanner entrada = new Scanner(System.in);
        
        int empleados;
        
        System.out.print("Ingrese el número de empleados: ");
        empleados = entrada.nextInt();
        
        POO[] lista_empleados = new POO[empleados];
        
        for (int i = 0; i < empleados; i++) {
            
            String id_empleado, nombre_empleado;
            double venta_total, salario_mensual;
            
            System.out.print("Ingrese el ID del empleado " + (i+1) + ": ");
            id_empleado = entrada.next();
            
            System.out.print("Ingrese el nombre del empleado " + (i+1) + ": ");
            nombre_empleado = entrada.next();
            
            System.out.print("Ingrese la venta total del empleado " + (i+1) + ": ");
            venta_total = entrada.nextDouble();
            
            System.out.print("Ingrese el salario mensual del empleado " + (i+1) + ": ");
            salario_mensual = entrada.nextDouble();
            
            lista_empleados[i] = new POO(id_empleado, nombre_empleado, venta_total, salario_mensual);
            
        }
        
        for (POO empleado : lista_empleados) {
            empleado.imprimirInformacion();
        }
        
        entrada.close();

    }

}















