<!-- No borrar o modificar -->
[Inicio](./index.md)

## Sesión 7 


<!-- Su documentación aquí -->

public class Producto {
   private String nombre;
   private double precio;
   private int cantidad;
   
   //Constructores
  public Producto() {
    this.nombre = "Desconocido";
    this.precio = 0.0;
    this.cantidad = 0;
    }
  public Producto(String nombre, double precio) {
    this.nombre = nombre;
    this.precio = precio;
    this.cantidad = 0;
      
}
   public Producto(String nombre, double precio, int cantidad) {
    this.nombre = nombre;
    this.precio = precio;
    this.cantidad = cantidad;   
    }
    //metodos
    
    public double calcularValorTotal(){
        return precio * cantidad;
    }
    
    public void mostrarInformacion() {
    System.out.println("Informacion del produto");
    System.out.println("nombre: " + this.nombre);
    System.out.println("precio: " + this.precio);
    System.out.println("cantidad: " + this.cantidad);
    System.out.println("Valor total: " + calcularValorTotal());
        
    }
     // Metodo Sobrecargados
    
    public void incrementarCantidad(){
     cantidad++;
    
    }
 

    public void incrementarCantidad(int cantidadIncrementar){
    cantidad += cantidadIncrementar;
    }
    //Precio dolar
    public void actualizarPrecio(double nuevoPrecio) {
        precio = nuevoPrecio;
    }
    
    //Precio Euro
    public void actualizarPrecio(double nuevoPrecio, String moneda){
        double tasaCambio = 1.0;
        if (moneda.equals("Euros")){
            tasaCambio = 0.85;
        } else if (moneda.equals("Peso colombiano: ")){
            
        }
        
        precio = nuevoPrecio * tasaCambio;
        
    }
    
    //Precio moneja espefica
    
    public void actualizarPrecio (double nuevoprecio, String modena, double tasaCambio){
        if (modena.equals("Dolares")){
            precio = nuevoprecio;
        } else {
            precio = nuevoprecio * tasaCambio;
        }
    }
}

main
public class Sobrecarga {

    public static void main(String[] args) {
        Producto p1 = new Producto ();
        Producto p2 = new Producto ("Galletas", 2000);
        Producto p3 = new Producto ("Bolsa de arroz", 3000, 5);
        
        p1.mostrarInformacion();
        p2.mostrarInformacion();
        p3.mostrarInformacion();
        
        
        p1.incrementarCantidad();
        p2.incrementarCantidad(1);
        p3.actualizarPrecio(2.5);
        p3.incrementarCantidad();
        p2.actualizarPrecio(30, "euros");
        p2.actualizarPrecio(15, "peso Colombiano", 4000);
        
        
        p1.mostrarInformacion();
        p2.mostrarInformacion();
        p3.mostrarInformacion();
    }  
    }





