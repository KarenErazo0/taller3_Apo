```

package umariana.taller3;
import java.text.SimpleDateFormat;
import java.util.ArrayList;
import java.util.Date;
import java.util.Scanner;
import mundo.Entrada;

public class Taller3 {
    private ArrayList<Entrada> misEntradas;
    private Scanner lector;

    public Taller3() {
        //nuevo contenedor vacio
        misEntradas = new ArrayList<>();
        lector = new Scanner(System.in);
    }

    //metodo para mostrar el menu de opciones
    public void mostrarMenu() {
    boolean activo = true;

        //crear un ciclo para mantener el menu activo hasta finalizar
    do {
        System.out.println("-------BIENVENIDO--------");
        System.out.println("1. Agregar Entrada\n2. Consultar entrada\n3. Modificar entrada\n4. Eliminar entrada\n5. Salir");
        int opcion = lector.nextInt();
           
        switch (opcion) {
            case 1:
                agregarEntrada();
                break;
            case 2:
                if (misEntradas.size() == 0) {
                System.out.println("No hay entradas agregadas.");
                } else {
                      
                consultarEntrada();
                }
                break;

            case 3:
                if (misEntradas.size() == 0) {
                System.out.println("No hay entradas agregadas");
                } else {
                modificarEntrada();
                }
                break;
                

            case 4:
                if (misEntradas.size() == 0) {
                System.out.println("No hay entradas agregadas");
                } else {
                eliminarEntrada();
                }
                break;
            case 5:
                //establecer variable para terminar el ciclo
                activo = false;
                System.out.println("=====PROGRAMA TERMINADO=====");
                break;

            default:
            // mensaje de error si se ingresa una opcion incorrecta
            System.out.println("opcion no valida");
            }
           }while (activo);
    }

    public void agregarEntrada() {
    SimpleDateFormat formato = new SimpleDateFormat("dd-MM-yyyy");
    String fecha = formato.format(new Date());
    System.out.println("Fecha: " + fecha);
    lector.nextLine();

    int idEntrada = 1; // Asigna un valor predeterminado


    System.out.println("ID asignado: " + idEntrada);       
    System.out.println("Ingrese la descripción:");
    String descripcion = lector.nextLine(); 
    System.out.println("Entrada agregada correctamente");

    // Crear la nueva entrada utilizando el idEntrada correcto
    Entrada nuevaEntrada = new Entrada(idEntrada, fecha, descripcion);
    // Agregar la nueva entrada a la lista
    misEntradas.add(nuevaEntrada);
}


   
    private void consultarEntrada() {
    System.out.print("Ingrese la fecha de la Entrada que desea consultar (dd-MM-yyyy): ");
    lector.nextLine();
    String fechaBuscada = lector.nextLine(); // El usuario ingresa la fecha
    // Verificar si hay entradas en esa fecha
  SimpleDateFormat formatter = new SimpleDateFormat("dd-MM-yyyy");
    
    for (Entrada entrada : misEntradas) {
        if (entrada.getFecha().equals(fechaBuscada)) {
            // Se encontró al menos una entrada con la fecha especificada

            System.out.println("ID: " + entrada.getIdEntrada() + " | Fecha: " + entrada.getFecha() + " | Descripción: " + entrada.getDescripcion());
            System.out.println("-------------------");
        }else{
            System.out.println("No se encontro la fecha de la Entrada");
        }
    }
    
}
    public void modificarEntrada() {
        System.out.println("=====MODIFICAR====");
        System.out.println("Ingrese el ID de la entrada que desea modificar:");
        int id = lector.nextInt();
        lector.nextLine(); // Consumir el carácter de nueva línea pendiente

        boolean verificar = false;
        for (Entrada e : misEntradas) {
        if (e.getIdEntrada() == id) {
            verificar = true;
            System.out.println("Entrada encontrada:");
            System.out.println("ID: " + e.getIdEntrada());
            System.out.println("Descripción actual: " + e.getDescripcion());
            System.out.println("Ingrese la nueva descripción:");
            String nuevaDescripcion = lector.nextLine();
            e.setDescripcion(nuevaDescripcion);
            System.out.println("Entrada modificada exitosamente.");
            break;
            }
            }
        if (!verificar) {
        System.out.println("No se encontró ninguna entrada con el ID proporcionado.");
        }  
        }
    
     public void eliminarEntrada() {
        System.out.println("=====ELIMINAR ENTRADA=====");
        System.out.println("Ingrese el id de la entrada a eliminar: ");
        int id =lector.nextInt();
        for(Entrada e: misEntradas){
        if(e.getIdEntrada()==id){
            System.out.println("Deseas eliminar la entrada?\n1. Confirmar\n2. Cancelar");
            int opcion = lector.nextInt();
            if(opcion==1){
            misEntradas.remove(e);
            System.out.println("Entrada eliminada");
            break;
            }else if(opcion==2){
            System.out.println("Se canceló eliminar entrada");
            }
            break;
            }else {
            System.out.println("no se encontró ninguna entrada");
            }   
            }
        // Implementación de eliminarEntrada()
        }
    public void mostrarEntrada() {    
        // Implementación de mostrarEntrada()
    }
    public static void main(String[] args) {
        Taller3 organizador = new Taller3();
        organizador.mostrarMenu();
    }
}
```

