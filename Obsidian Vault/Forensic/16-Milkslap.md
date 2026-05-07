
# Reto 
### - Milkslap
## Descripcion
🥛http://wily-courier.picoctf.net:51691/
## Solucion
```
                                                                                    
┌──(kali㉿kali)-[~]
└─$ sudo gem install zsteg
[sudo] password for kali: 
Successfully installed zsteg-0.2.14
Parsing documentation for zsteg-0.2.14
Done installing documentation for zsteg after 0 seconds
1 gem installed
                                                                                    
┌──(kali㉿kali)-[~]
└─$ zsteg -a concat.png
[!] #<Errno::ENOENT: No such file or directory @ rb_sysopen - concat.png>
                                                                                    
┌──(kali㉿kali)-[~]
└─$ wget http://wily-courier.picoctf.net:51691/concat_v.png
--2026-05-01 16:23:20--  http://wily-courier.picoctf.net:51691/concat_v.png
Resolving wily-courier.picoctf.net (wily-courier.picoctf.net)... 18.189.99.27
Connecting to wily-courier.picoctf.net (wily-courier.picoctf.net)|18.189.99.27|:51691... connected.
HTTP request sent, awaiting response... 200 OK
Length: 18095920 (17M) [image/png]
Saving to: ‘concat_v.png’

concat_v.png         100%[======================>]  17.26M  10.1MB/s    in 1.7s    

2026-05-01 16:23:22 (10.1 MB/s) - ‘concat_v.png’ saved [18095920/18095920]

                                                                                    
┌──(kali㉿kali)-[~]
└─$ zsteg -a concat_v.png                                  
/home/kali/.local/share/gem/ruby/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:369:in `prev_scanline_byte': stack level too deep (SystemStackError)
        from /home/kali/.local/share/gem/ruby/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:319:in `block in decoded_bytes'
        from /home/kali/.local/share/gem/ruby/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:318:in `upto'
        from /home/kali/.local/share/gem/ruby/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:318:in `decoded_bytes'
        from /home/kali/.local/share/gem/ruby/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line/mixins.rb:17:in `prev_scanline_byte'
        from /home/kali/.local/share/gem/ruby/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:377:in `prev_scanline_byte'
        from /home/kali/.local/share/gem/ruby/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:319:in `block in decoded_bytes'
        from /home/kali/.local/share/gem/ruby/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:318:in `upto'
        from /home/kali/.local/share/gem/ruby/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:318:in `decoded_bytes'
         ... 10225 levels...
        from /home/kali/.local/share/gem/ruby/3.3.0/gems/zsteg-0.2.14/lib/zsteg.rb:26:in `run'
        from /home/kali/.local/share/gem/ruby/3.3.0/gems/zsteg-0.2.14/bin/zsteg:8:in `<top (required)>'
        from /usr/local/bin/zsteg:25:in `load'
        from /usr/local/bin/zsteg:25:in `<main>'
                                                                                    
┌──(kali㉿kali)-[~]
└─$ export RUBY_THREAD_VM_STACK_SIZE=50000000
zsteg -a concat_v.png | grep picoCTF
b1,b,lsb,xy         .. text: "picoCTF{imag3_m4n1pul4t10n_sl4p5}\n"

picoCTF{imag3_m4n1pul4t10n_sl4p5}
```
## Notas adicionales 

## Referencias


