
# Reto 
### vault-door-4
## Descripcion
This vault uses ASCII encoding for the password.The source code for this vault is here: [VaultDoor4.java](https://challenge-files.picoctf.net/c_fickle_tempest/5c887bc56d0c788895c28b80d7b702aff7b889fc7d8edf83fe0dc25c8aa11756/VaultDoor4.java)
## Solucion
```
import java.util.*;

  

class VaultDoor4 {

public static void main(String args[]) {

VaultDoor4 vaultDoor = new VaultDoor4();

Scanner scanner = new Scanner(System.in);

System.out.print("Enter vault password: ");

String userInput = scanner.next();

String input = userInput.substring("picoCTF{".length(),userInput.length()-1);

if (vaultDoor.checkPassword(input)) {

System.out.println("Access granted.");

} else {

System.out.println("Access denied!");

}

}

  

// I made myself dizzy converting all of these numbers into different bases,

// so I just *know* that this vault will be impenetrable. This will make Dr.

// Evil like me better than all of the other minions--especially Minion

// #5620--I just know it!

//

// .:::. .:::.

// :::::::.:::::::

// :::::::::::::::

// ':::::::::::::'

// ':::::::::'

// ':::::'

// ':'

// -Minion #7781

public boolean checkPassword(String password) {

byte[] passBytes = password.getBytes();

byte[] myBytes = {

106 , 85 , 53 , 116 , 95 , 52 , 95 , 98 ,

0x55, 0x6e, 0x43, 0x68, 0x5f, 0x30, 0x66, 0x5f,

0142, 0131, 0164, 063 , 0163, 0137, 0145, 060 ,

'2' , '1' , '3' , '8' , '7' , '2' , '1' , '3' ,

};

/*for (int i=0; i<32; i++) {

if (passBytes[i] != myBytes[i]) {

return false;

}

}*/

String flag = new String(myBytes);

System.out.println(flag);

return true;

}

}
picoCTF{jU5t_4_bUnCh_0f_bYt3s_e021387213}
```
## Notas adicionales 

## Referencias


