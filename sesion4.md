<!-- No borrar o modificar -->
[Inicio](./index.md)

## Sesión 4


<!-- Su documentación aquí -->

actividad sesión 4

public class Producto {
    //atributos
    public String nombre;
    private double precio;
    protected int cantidad;
    final String fabricante = "NORMA SA ";
    static String marca = "NORMA";
    String categoria;

    //constructor
    public Producto(String nombre, double precio, int cantidad, String categoria) {
        this.nombre = nombre;
        this.precio = precio;
        this.cantidad = cantidad;
        this.categoria = categoria;
    }
    //getter y sedder
    public String getNombre() {
        return nombre;
    }

    public void setNombre(String nombre) {
        this.nombre = nombre;
    }

    public double getPrecio() {
        return precio;
    }

    public void setPrecio(double precio) {
        this.precio = precio;
    }

    public int getCantidad() {
        return cantidad;
    }

    public void setCantidad(int cantidad) {
        this.cantidad = cantidad;
    }

    public static String getMarca() {
        return marca;
    }

    public static void setMarca(String marca) {
        Producto.marca = marca;
    }

    public String getCategoria() {
        return categoria;
    }

    public void setCategoria(String categoria) {
        this.categoria = categoria;
    }

    
    
    
}

public class Ejercicio3 {

    public static void main(String[] args) {
        //main
      Producto prod1 = new Producto("Cuaderno", 10800 ,30 , "utiles escolares");
        System.out.println( "el nombre del producto es: " + prod1.getNombre());
        System.out.println("el precio del producto es: " + prod1.getPrecio());
        System.out.println("el fabricante es: " + prod1.fabricante);
        prod1.setNombre("Cartuchera");
        System.out.println("e nombre del producto es: " + prod1.getNombre());
         prod1.setPrecio( 7500);
         System.out.println("el precio del prodcto es: " + prod1.getPrecio());
         
         
      
    }
    
        
    
    
    
}







