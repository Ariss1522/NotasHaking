
# Reto 
### Rust fixme 2
## Descripcion
The Rust saga continues? I ask you, can I borrow that, pleeeeeaaaasseeeee?Download the Rust code [here](https://challenge-files.picoctf.net/c_verbal_sleep/babfbee79718a6363826ba86300173ffde6d81577e9dd07d4130c53a7eecf6c3/fixme2.tar.gz).
## Solucion
```
                                                                            
┌──(kali㉿kali)-[~]
└─$ wget https://challenge-files.picoctf.net/c_verbal_sleep/babfbee79718a6363826ba86300173ffde6d81577e9dd07d4130c53a7eecf6c3/fixme2.tar.gz
--2026-03-25 18:51:07--  https://challenge-files.picoctf.net/c_verbal_sleep/babfbee79718a6363826ba86300173ffde6d81577e9dd07d4130c53a7eecf6c3/fixme2.tar.gz
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.161.44.22, 3.161.44.84, 3.161.44.61, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|3.161.44.22|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1585 (1.5K) [application/octet-stream]
Saving to: ‘fixme2.tar.gz’

fixme2.tar.gz      100%[================>]   1.55K  --.-KB/s    in 0s      

2026-03-25 18:51:08 (91.8 MB/s) - ‘fixme2.tar.gz’ saved [1585/1585]

                                                                            
┌──(kali㉿kali)-[~]
└─$ gzip -d fixme2.tar.gz
                                                                            
┌──(kali㉿kali)-[~]
└─$ tar -xvf fixme2.tar
fixme2/
fixme2/Cargo.toml
fixme2/Cargo.lock
fixme2/src/
fixme2/src/main.rs
                                                                            
┌──(kali㉿kali)-[~]
└─$ cd fixme2       
                                                                            
┌──(kali㉿kali)-[~/fixme2]
└─$ nano src/main.rs
                                                                            
┌──(kali㉿kali)-[~/fixme2]
└─$ cargo run      
   Compiling crossbeam-utils v0.8.20
   Compiling rayon-core v1.12.1
   Compiling either v1.13.0
   Compiling crossbeam-epoch v0.9.18
   Compiling crossbeam-deque v0.8.5
   Compiling rayon v1.10.0
   Compiling xor_cryptor v1.2.3
   Compiling rust_proj v0.1.0 (/home/kali/fixme2)
    Finished `dev` profile [unoptimized + debuginfo] target(s) in 4.05s
     Running `target/debug/rust_proj`
Using memory unsafe langu
```
## Notas adicionales 

## Referencias


