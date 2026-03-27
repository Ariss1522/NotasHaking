
# Reto 
### Rust fixme 1
## Descripcion
Have you heard of Rust? Fix the syntax errors in this Rust file to print the flag!Download the Rust code [here](https://challenge-files.picoctf.net/c_verbal_sleep/3f0e13f541928f420d9c8c96b06d4dbf7b2fa18b15adbd457108e8c80a1f5883/fixme1.tar.gz).
## Solucion
```
                                                                            
┌──(kali㉿kali)-[~]
└─$ wget https://challenge-files.picoctf.net/c_verbal_sleep/3f0e13f541928f420d9c8c96b06d4dbf7b2fa18b15adbd457108e8c80a1f5883/fixme1.tar.gz
--2026-03-25 18:25:39--  https://challenge-files.picoctf.net/c_verbal_sleep/3f0e13f541928f420d9c8c96b06d4dbf7b2fa18b15adbd457108e8c80a1f5883/fixme1.tar.gz
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.161.44.22, 3.161.44.103, 3.161.44.84, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|3.161.44.22|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1415 (1.4K) [application/octet-stream]
Saving to: ‘fixme1.tar.gz’

fixme1.tar.gz       100%[================>]   1.38K  --.-KB/s    in 0s      

2026-03-25 18:25:40 (50.6 MB/s) - ‘fixme1.tar.gz’ saved [1415/1415]

                                                                             
┌──(kali㉿kali)-[~]
└─$ file fixme1.tar.gz 
fixme1.tar.gz: gzip compressed data, last modified: Mon Dec 16 16:49:52 2024, from Unix, original size modulo 2^32 7168
                                                                             
┌──(kali㉿kali)-[~]
└─$ gzip -d fixme1.tar.gz
┌──(kali㉿kali)-[~]
└─$ tar -xvf fixme1.tar 
fixme1/
fixme1/Cargo.toml
fixme1/Cargo.lock
fixme1/src/
fixme1/src/main.rs
                                                                             
┌──(kali㉿kali)-[~]
└─$ cd fixme1     
                                                                             
┌──(kali㉿kali)-[~/fixme1]
└─$ nano src/main.rs
──(kali㉿kali)-[~/fixme1]
└─$ cargo run
    Updating crates.io index
  Downloaded xor_cryptor v1.2.3
  Downloaded either v1.13.0
  Downloaded rayon-core v1.12.1
  Downloaded crossbeam-epoch v0.9.18
  Downloaded crossbeam-deque v0.8.5
  Downloaded crossbeam-utils v0.8.20
  Downloaded rayon v1.10.0
  Downloaded 7 crates (379.2KiB) in 0.64s
   Compiling crossbeam-utils v0.8.20
   Compiling rayon-core v1.12.1
   Compiling either v1.13.0
   Compiling crossbeam-epoch v0.9.18
   Compiling crossbeam-deque v0.8.5
   Compiling rayon v1.10.0
   Compiling xor_cryptor v1.2.3
   Compiling rust_proj v0.1.0 (/home/kali/fixme1)
    Finished `dev` profile [unoptimized + debuginfo] target(s) in 6.20s
     Running `target/debug/rust_proj`
"picoCTF{4r3_y0u_4_ru$t4c30n_n0w?}"

```
## Notas adicionales 

## Referencias


