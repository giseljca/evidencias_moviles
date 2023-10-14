<!-- No borrar o modificar -->
[Inicio](./index.md)

## Sesión 5 


<!-- Su documentación aquí -->

ejercicio sesión 5

//clase principal:

public class Ejercicio_herencia {

    public static void main(String[] args) {
        System.out.println("-------Automovil------");
        System.out.println("");
        Automovil a1 = new Automovil(4,"manual","rojo", "AEBJK-16","Toyota","GR corolla", 2023 );
        a1.mostrarInformacionAutomovil();
        System.out.println("");
        System.out.println("******motocicleta******");
        System.out.println("");
        Motocicleta m1 = new Motocicleta (10000, "deportiva", "EKLMF-06", "negra con verde", "Suzuki", "destroger", 2022);
        m1.mostrarInformacionMotocicleta();
    }

    }

//Clase padre Vehiculo:
public class Vehiculo {
    protected String marca; // Cambiamos a protegido
    protected String modelo; // Cambiamos a protegido
    int año;

    public Vehiculo(String marca, String modelo, int año) {
        this.marca = marca;
        this.modelo = modelo;
        this.año = año;
    }
public void mostrarInformacion() {
        System.out.println("Marca: " + marca);
        System.out.println("Modelo: " + modelo);
        System.out.println("Año: " + año);
    }
    
}

//clase hija Automovil:

public class Automovil extends Vehiculo {
    private int numPuertas;
    private String tipoTransmision;
    private String color;
    private String placa;
    

    public Automovil(int numPuertas, String tipoTransmision,String color,String placa, String marca, String modelo, int año) {
        super(marca, modelo, año);
        this.numPuertas = numPuertas;
        this.tipoTransmision = tipoTransmision;
        this.color = color;
        this.placa = placa;
    }
    
    public void mostrarInformacionAutomovil() {
        System.out.println("Número de puertas: " + numPuertas);
        System.out.println("Tipo de transmisición: " + tipoTransmision);
        System.out.println("Color: " + color);
        System.out.println("Placa: " + placa);
        System.out.println("Marca: " + marca);
        System.out.println("Modelo: " + modelo);
        System.out.println("Año: " + año);
        
       
    } 
}

//clase hija motocicleta:

public class Motocicleta extends Vehiculo {
    private int cilindraje;
    private String tipo;
    private String color;
    private String placa;

    public Motocicleta(int cilindraje, String tipo, String color, String placa, String marca, String modelo, int año) {
        super(marca, modelo, año);
        this.cilindraje = cilindraje;
        this.tipo = tipo;
        this.color = color;
        this.placa = placa;
    }
    
    public void mostrarInformacionMotocicleta(){
        System.out.println("cilindraje: " + cilindraje);
        System.out.println("tipo de motocicleta: " + tipo);
        System.out.println("placa: " + placa);
        System.out.println("color: " + color);
        System.out.println("Marca: " + marca);
        System.out.println("modelo: " + modelo);
        System.out.println("Año: " + año);
    }
    
}





