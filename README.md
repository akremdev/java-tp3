# java-tp3

```java
package jdbcdema;
import java.sql.*;
import javax.sql.RowSetEvent;
import javax.sql.RowSetListener;
import javax.sql.rowset.JdbcRowSet;
import com.sun.rowset.JdbcRowSetImpl;
public static void main(String[] args) throws Exception {
JdbcRowSet rs;
int s = 0;
int matricule=0;
try {
Class.forName("com.mysql.jdbc.Driver");
rs = new JdbcRowSetImpl();
rs.setUrl("jdbc:mysql://localhost/demo");
rs.setUsername("root");
rs.setPassword("tootroot");
rs.setCommand("SELECT * FROM employees");
rs.setConcurrency(ResultSet.CONCUR_READ_ONLY);
rs.execute();
while (rs.next()) {
System.out.println("Nom : "+ rs.getString("last_name") + " ,
Prenom : "+ rs.getString("first_name") + " , Adresse : " +
rs.getString("adress")); s++;
}System.out.println("----------------------------------------------------- -");
System.out.println("La somme des liste des etudiants = "+ s);
System.out.println("----------------------------------------------------- -");
rs.close();
} catch ( SQLException ex ) {
System.out.println("Erreur de connexion\n "
+ex.getMessage()); } }
@Override
public void cursorMoved(RowSetEvent arg0) {
// TODO Auto-generated method stub
}
@Override public void rowChanged(RowSetEvent arg0) {
// TODO Auto-generated method stub
}
@Override public void rowSetChanged(RowSetEvent arg0) {
// TODO Auto-generated method stub
}
}
```
