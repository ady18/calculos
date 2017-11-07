# calculos
package ejemploprogramacionpoo;
import java.util.*;
/**
 *
 * @author Adirane
 */
public class EjemploProgramacionPOO {

    public static void main(String[] args) {
        
        //Declaración  y creación del objeto "calc" de la clase "Calculos".
	Calculos calc = new Calculos();
        
	/**Declaración y creación del objeto "teclado" de la clase "Scanner". 
         * Utilizado para lectura de valores del teclado de la computadora.
         */
	Scanner teclado = new Scanner(System.in);

        //Variables
	float valor1, valor2, resultado = 0;
	int opcion;
        
        /**Menu que se presenta al usuario que utilizará el programa, 
         * para que este pueda elegir el calculo a ser efectuado o 
         * salir del programa.
         */
	do{
            
            System.out.println("\nSelecciona el tipo de calculo a realizar: ");
            System.out.println("1. Calculo 01");
            System.out.println("2. Calculo 02");
            System.out.println("3. Calculo 03");
            System.out.println("4. Salir");
            System.out.println("Opción: ");
            opcion = teclado.nextInt();

            //Lectura de los valores ingresados por el usuario
            if(opcion != 4){

		System.out.println("\nIngrese el primer valor: ");
		valor1 = teclado.nextFloat();
		System.out.println("\nIngrese el segundo valor: ");
		valor2 = teclado.nextFloat();

            //Ejecución del calculo elegido por el usuario
            switch(opcion){
		case 1: 
                    resultado = calc.calculo01(valor1, valor2);
                    break;
		case 2: 
                    calc.setNum1(valor1);
                    calc.setNum2(valor2);
		    resultado = calc.calculo02();
                    break;
		case 3: 
                    calc.setNum1(valor1);
		    calc.setNum2(valor2);
                    resultado = calc.getTotal();
                    break;
            }
            
            //Se presenta el resultado del calculo
            System.out.println("\n\n======================================");
            System.out.println("Resultado : " + resultado);
            System.out.println("\n\n======================================");
			}
	} while(opcion != 4);
        
    }
    
}
    
//Clase Calculos
class Calculos{

    //Atributos
    private float num1;
    private float num2;
    private float total;

    //Método constructor
    public Calculos(){
	num1 = 0;
	num2 = 0;
	total = 0;
    }
		
    //Método para regresar el valor del atributo "total"
                
    public float getTotal(){
	return(total);
    }
	
    //Método que ingresa valor al atributo "num1"
                
    public void setNum1(float v1){
	num1 = v1;
    }

    //Metodo construido para colocar valor en el atributo "num2"

    public void setNum2(float v1){
        num2 = v1;
    }

    /**Método construido para recibir dos valores, efectuar un calculo 
     * y retornar el resultado sin usar los atributos de la clase.
     */

    public float calculo01(float v1, float v2) {
        float res;
        res = (v1 * v2) / (v1 + v2);
        return(res);
    }

    /**Método construido para efectuar un cálculo con valores previamente 
     * pasados a los atributos "num1" e "num2" de la clase y retornar el 
     * valor de este cálculo.
     */

    public float calculo02 ( ){
        total = num1 - 3 * num2;
        return(total);
    }

    /**
     * Método construido para efectuar un cálculo con valores previamente 
     * pasados a los atributos "num1" y "num2" de la clase. 
     * El resultado del cálculo será almacenado en el atributo "total" y 
     * podrá ser obtenido por medio de la llamada al método "getTotal".
     */

    public void calculo03 ( ) {
        total = (num1 - num2) / num2;
    }
}
