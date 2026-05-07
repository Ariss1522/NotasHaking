
# Reto 
### vault-door-training
## Descripcion
Your mission is to enter Dr. Evil's laboratory and retrieve the blueprints for his Doomsday Project. The laboratory is protected by a series of locked vault doors. Each door is controlled by a computer and requires a password to open. Unfortunately, our undercover agents have not been able to obtain the secret passwords for the vault doors, but one of our junior agents obtained the source code for each vault's computer! You will need to read the source code for each level to figure out what the password is for that vault door. As a warmup, we have created a replica vault in our training facility.The source code for the training vault is here: [VaultDoorTraining.java](https://challenge-files.picoctf.net/c_fickle_tempest/c04132d895d748e87dd052bcfbc5186348a7cdb644ab9b5b82be9a82a02a30a8/VaultDoorTraining.java)
## Solucion
```
                                                                          
┌──(kali㉿kali)-[~]
└─$ wget https://challenge-files.picoctf.net/c_fickle_tempest/c04132d895d748e87dd052bcfbc5186348a7cdb644ab9b5b82be9a82a02a30a8/VaultDoorTraining.java
--2026-04-29 09:52:14--  https://challenge-files.picoctf.net/c_fickle_tempest/c04132d895d748e87dd052bcfbc5186348a7cdb644ab9b5b82be9a82a02a30a8/VaultDoorTraining.java
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 18.238.132.49, 18.238.132.115, 18.238.132.26, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|18.238.132.49|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 943 [application/octet-stream]
Saving to: ‘VaultDoorTraining.java’

VaultDoorTraining.j 100%[================>]     943  --.-KB/s    in 0s      

2026-04-29 09:52:14 (9.85 MB/s) - ‘VaultDoorTraining.java’ saved [943/943]

                                                                             
┌──(kali㉿kali)-[~]
└─$ cat VaultDoorTraining.java 
import java.util.*;

class VaultDoorTraining {
    public static void main(String args[]) {
        VaultDoorTraining vaultDoor = new VaultDoorTraining();
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

    // The password is below. Is it safe to put the password in the source code?
    // What if somebody stole our source code? Then they would know what our
    // password is. Hmm... I will think of some ways to improve the security
    // on the other doors.
    //
    // -Minion #9567
    public boolean checkPassword(String password) {
        return password.equals("w4rm1ng_Up_w1tH_jAv4_000AXPNPN0i");
    }
}
                                                                             
┌──(kali㉿kali)-[~]
└─$ javac VaultDoorTraining.java 
                                                                                    
┌──(kali㉿kali)-[~]
└─$ java VaultDoorTraining VaultDoorTraining.java 
Enter vault password: picoCTF(w4rm1ng_Up_w1tH_jAv4_000AXPNPN0i)
Access granted.
                                                                         
picoCTF(w4rm1ng_Up_w1tH_jAv4_000AXPNPN0i)
```
## Notas adicionales 

## Referencias


