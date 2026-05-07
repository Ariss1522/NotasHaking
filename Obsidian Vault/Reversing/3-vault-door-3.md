
# Reto 
### vault-door-3
## Descripcion
This vault uses for-loops and byte arrays.The source code for this vault is here: [VaultDoor3.java](https://challenge-files.picoctf.net/c_fickle_tempest/856cff883937e1cfe99e7e5b9c2fbbf08232a8135f919b1111615f007a4de03a/VaultDoor3.java)
## Solucion
```
public class VaultDoor3Solver {
    public static void main(String args[]) {
        // Esta es la cadena revuelta contra la que el programa original nos compara
        String target = "jU5t_a_sna_3lpm11g54e_u_4_m4r042";
        char[] password = new char[32];
        int i;
        
        // Revertimos el primer ciclo (los primeros 8 caracteres se quedan igual)
        for (i = 0; i < 8; i++) {
            password[i] = target.charAt(i);
        }
        
        // Revertimos el segundo ciclo (los caracteres del 8 al 15 están invertidos)
        for (; i < 16; i++) {
            password[23 - i] = target.charAt(i);
        }
        
        // Revertimos el tercer ciclo (posiciones pares del 16 al 30)
        for (; i < 32; i += 2) {
            password[46 - i] = target.charAt(i);
        }
        
        // Revertimos el cuarto ciclo (posiciones impares del 31 al 17)
        for (i = 31; i >= 17; i -= 2) {
            password[i] = target.charAt(i);
        }
        
        // Convertimos el arreglo de caracteres de vuelta a un String
        String flag = new String(password);
        
        System.out.println("¡Bandera encontrada!");
        System.out.println("picoCTF{" + flag + "}");
    }
}
picoCTF{jU5t_a_s1mpl3_an4gr4m_4_u_e45012}
```
## Notas adicionales 

## Referencias


