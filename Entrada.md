```
package mundo;
import java.util.Date;
/**
 *
 * @author KAREN ERAZO y JULIANA MUÑOZ
 */
public class Entrada {
    private int idEntrada;
    private String fecha;
    private String descripcion;

    public Entrada() {
    }

    public Entrada(int idEntrada, String fecha, String descripcion) {
        this.idEntrada = idEntrada;
        this.fecha = fecha;
        this.descripcion = descripcion;
    }

    public int getIdEntrada() {
        return idEntrada;
    }

    public void setIdEntrada(int idEntrada) {
        this.idEntrada = idEntrada;
    }

    public String getFecha() {
        return fecha;
    }

    public void setFecha(String fecha) {
        this.fecha = fecha;
    }

    public String getDescripcion() {
        return descripcion;
    }

    public void setDescripcion(String descripcion) {
        this.descripcion = descripcion;
    }

    public Date getfecha() {
        throw new UnsupportedOperationException("Not supported yet."); // Generated from nbfs://nbhost/SystemFileSystem/Templates/Classes/Code/GeneratedMethodBody
    }
}
```
    
