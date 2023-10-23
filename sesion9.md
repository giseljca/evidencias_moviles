<!-- No borrar o modificar -->
[Inicio](./index.md)

## Sesión 9 


<!-- Su documentación aquí -->

//main
public class Convertidor {

    public static void main(String[] args) {
        System.out.println("------Temperatura-------");
        System.out.println("");
        Temperatura t1 = new Temperatura("Celcius", "Fahrenheit");
        Temperatura t2 = new Temperatura("Fahrenheit", "Celcius");
        Temperatura t3 = new Temperatura("Celcius", "Kelvin");
        Temperatura t4 = new Temperatura("Kelvin", "Celcius");
        Temperatura t5 = new Temperatura("Fahrenheit", "Kelvin");
        Temperatura t6 = new Temperatura("Kelvin", "Fahrenheit");
        System.out.println("");
        System.out.println("de Celcius a Fahrenheit: ");
        t1.convertir(100);
        System.out.println("de Fahrenheit a celcius: ");
        t2.convertir(250);
        System.out.println("");
        System.out.println("de celcius a Kelvin : ");
        t3.convertir(180);
        System.out.println("de Kelvin a Celcius: " );
        t4.convertir(50);
        System.out.println("de Fahrenheit a kelvin: ");
        t5.convertir(300);
        System.out.println("de Kelvin a Fahrenheit");
        t6.convertir(500);
        System.out.println("");
        System.out.println("-----Longitud------");
        System.out.println("");
        
        Longitud L1 = new Longitud("Metros", "Pies");
        Longitud L2 = new Longitud("Pies", "Metros");
        Longitud L3 = new Longitud("Kilómetros", "Millas");
        Longitud L4 = new Longitud("Millas", "Kilómetros");
        System.out.println("de Metros a Pies: ");
        L1.convertir(400.);
        System.out.println("de Pies a Metros: ");
        L2.convertir(1000.);
        System.out.println("de Kilómetros a Millas: ");
        L3.convertir(2500.);
        System.out.println("de Millas a Kilómetros: ");
        L4.convertir(221.);
        
        System.out.println("-----Peso------");
        System.out.println("");
        
        Peso P1 = new Peso("Kilogramos", "Libras");
        Peso P2 = new Peso("Libras", "Kilogramos");
        Peso P3 = new Peso("gramos", "libras");
        Peso P4 = new Peso("libras", "gramos");
        System.out.println(" de kilogramos a libras ");
        P1.convertir(400);
        System.out.println("de Libras a Kilogramos: ");
        P2.convertir(1000);
        System.out.println("de gramos a libras: ");
        P3.convertir(10000);
        System.out.println("de Libras a gramos: ");
        P4.convertir(20);
        System.out.println("");
        
        System.out.println("----Divisas-----");
        System.out.println("");      
        Divisas D1 = new Divisas("USDT", "EURO");
        Divisas D2 = new Divisas("EURO", "SDT");
        Divisas D3 = new Divisas("USDT", "COP");
        Divisas D4 = new Divisas("COP", "USDT");
        System.out.println(" de USDT a EURO ");
        D1.convertir(40000);
        System.out.println("de EURO a USDT: ");
        D2.convertir(1000000);
        System.out.println("de USDT a COP: ");
        D3.convertir(90000);
        System.out.println("de COP a USDT: ");
        D4.convertir(8900);
        System.out.println("");    
        
        System.out.println("-----Binarios----");
        Binarios B1 = new Binarios("decimal", "binario");
        Binarios B2 = new Binarios("binario", "decimal");
        Binarios B3 = new Binarios("decimal", "hexadecimal");
        Binarios B4 = new Binarios("hexadecimal", "decimal");
        System.out.println(" de decimal a binario ");
        B1.convertir(19);
        System.out.println("de binario a decimal: ");
        B2.convertir(1000010);
        System.out.println("de deciaml a hexadecimal: ");
        B3.convertir(5);
        System.out.println("de hexadecimal a decimal: ");
        B4.convertir(4);
        
    }
}

//Temperatura
public class Temperatura extends Conversor {

    public Temperatura(String unidadOrigen, String unidadDestino) {
        super(unidadOrigen, unidadDestino);
    }

    @Override
    public double convertir(double cantidad) {
        if (unidadOrigen.equals("Celsius") && unidadDestino.equals("Fahrenheit")) {
            // Celsius a Fahrenheit
            return (cantidad * 9 / 5) + 32;
        } else if (unidadOrigen.equals("Fahrenheit") && unidadDestino.equals("Celsius")) {
            // Fahrenheit a Celsius
            return (cantidad - 32) * 5 / 9;
        } else if (unidadOrigen.equals("Celsius") && unidadDestino.equals("Kelvin")) {
            // Celsius a Kelvin
            return cantidad + 273.15;
        } else if (unidadOrigen.equals("Kelvin") && unidadDestino.equals("Celsius")) {
            // Kelvin a Celsius
            return cantidad - 273.15;
        } else if (unidadOrigen.equals("Fahrenheit") && unidadDestino.equals("Kelvin")) {
            // Fahrenheit a Kelvin
            double celsius = (cantidad - 32) * 5 / 9;
            return celsius + 273.15;
        } else if (unidadOrigen.equals("Kelvin") && unidadDestino.equals("Fahrenheit")) {
            // Kelvin a Fahrenheit
            double celsius = cantidad - 273.15;
            return (celsius * 9 / 5) + 32;
        } else {
            throw new IllegalArgumentException("Unidades de temperatura no compatibles");
        }
    }
}

//Longitud
public class Longitud extends Conversor {

    private double cantidad;
    public Longitud(String unidadOrigen, String unidadDestino) {
        super(unidadOrigen, unidadDestino);
    }

    @Override
    public double convertir(double cantidad) {
        // Código 
      if (unidadOrigen.equals("Metros")&& unidadDestino.equals("Pies")){
       return cantidad * 3.28084;
    
     }else if (unidadOrigen.equals("Pies")&& unidadDestino.equals("Metros")){
       return cantidad / 3.28084;
    
    } else if(unidadOrigen.equals("Kilómetros")&& unidadDestino.equals("Millas")){
       return cantidad * 0.621371; 
    }else if(unidadOrigen.equals("Millas")&& unidadDestino.equals("Kilómetros")){
       return cantidad / 0.621371; 
    } else {
         throw new IllegalArgumentException("Unidades de Longitud no compatibles");
     }
    }
    } 

//peso
<br>
public class Peso extends Conversor {
    <br>
    public Peso(String unidadOrigen, String unidadDestino) {
        super(unidadOrigen, unidadDestino);
    }
    <br>
     @Override
    public double convertir(double cantidad) {
        // Código 
        <br>
     if (unidadOrigen.equals("Kilogramos")&& unidadDestino.equals("Libras")){
       return cantidad * 2.20462;
    
     }else if (unidadOrigen.equals("Libras")&& unidadDestino.equals("Kilogramos")){
       return cantidad / 2.20462;
    
    } else if(unidadOrigen.equals("gramos")&& unidadDestino.equals("Libras")){
       return cantidad * 453.59237; 
    }else if(unidadOrigen.equals("Libras")&& unidadDestino.equals("gramos")){
       return cantidad / 453.59237; 
    } else {
         throw new IllegalArgumentException("Unidades de Peso no compatibles");
     }
    }
    }
//Divisas
public class Divisas extends Conversor {
     public Divisas(String unidadOrigen, String unidadDestino) {
        super(unidadOrigen, unidadDestino);
    }

    @Override
    public double convertir(double cantidad) {
       if (unidadOrigen.equals("USDT")&& unidadDestino.equals("EURO")){
       return cantidad * 0.85;
    
     }else if (unidadOrigen.equals("EURO")&& unidadDestino.equals("USDT")){
       return cantidad / 0.85;
    
    } else if(unidadOrigen.equals("USDT")&& unidadDestino.equals("COP")){
       return cantidad * 4000.0; 
    }else if(unidadOrigen.equals("COP")&& unidadDestino.equals("USDT")){
       return cantidad / 4000.0; 
    } else {
         throw new IllegalArgumentException("Unidades de conversión no compatibles");
     }
    }
}

// Binarios
public class Binarios extends Conversor {

    public Binarios(String unidadOrigen, String unidadDestino) {
        super(unidadOrigen, unidadDestino);
    }
    public String decimalToBinary(int decimalNumber){
        return Integer.toBinaryString(decimalNumber);
    }
       public int binaryToDecimal(String binaryNumber){
         return Integer.parseInt(binaryNumber ,4 );
       }
       
       public String decimaltoHexadecimal(int decimalNumber){
           return Integer.toBinaryString(decimalNumber);
       }
       
       public int hexadecimalToDeciamal(String hexadecimalNumber){
           return Integer.parseInt(hexadecimalNumber, 10);
       }
       
    @Override
    public double convertir(double cantidad) {
      if (unidadOrigen.equals("decimal")&& unidadDestino.equals("binario")){
       return Double.parseDouble(decimalToBinary((int)cantidad));
    
     }else if (unidadOrigen.equals("binario")&& unidadDestino.equals("decimal")){
       return binaryToDecimal(String.valueOf((int)cantidad));
    
    } else if(unidadOrigen.equals("decimal")&& unidadDestino.equals("hexadecimal")){
       return Double.parseDouble(decimalToHexadecimal((int)cantidad)); 
    }else if(unidadOrigen.equals("hexadecimal")&& unidadDestino.equals("decimal")){
       return hexadecimalToDeciamal(String.valueOf((int)cantidad)); 
    } else {
         throw new IllegalArgumentException("Unidades de conversión no compatibles");
     }
    }

    private String decimalToHexadecimal(int i) {
        throw new UnsupportedOperationException(); 
        
        
    }
}
  






