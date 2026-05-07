
# Reto 
### m00nwalk
## Descripcion
Decode this [message](https://challenge-files.picoctf.net/c_fickle_tempest/f75cb0bb148301a92ee34a572e39d931d62c9c225f69e4b801ffa0fb6d2fe17b/message.wav) from the moon.
## Solucion
```
                                                                                    
┌──(kali㉿kali)-[~]
└─$ wget https://challenge-files.picoctf.net/c_fickle_tempest/f75cb0bb148301a92ee34a572e39d931d62c9c225f69e4b801ffa0fb6d2fe17b/message.wav  
--2026-05-01 13:48:56--  https://challenge-files.picoctf.net/c_fickle_tempest/f75cb0bb148301a92ee34a572e39d931d62c9c225f69e4b801ffa0fb6d2fe17b/message.wav
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.174.207.96, 3.174.207.125, 3.174.207.121, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|3.174.207.96|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 11066998 (11M) [application/octet-stream]
Saving to: ‘message.wav’

message.wav          100%[======================>]  10.55M  13.5MB/s    in 0.8s    

2026-05-01 13:48:58 (13.5 MB/s) - ‘message.wav’ saved [11066998/11066998]

                                                                                    
┌──(kali㉿kali)-[~]
└─$ git clone https://github.com/colaclanth/sstv.git
cd sstv
sudo pip3 install . --break-system-packages
Cloning into 'sstv'...
remote: Enumerating objects: 221, done.
remote: Counting objects: 100% (59/59), done.
remote: Compressing objects: 100% (10/10), done.
remote: Total 221 (delta 51), reused 49 (delta 49), pack-reused 162 (from 1)
Receiving objects: 100% (221/221), 1.01 MiB | 679.00 KiB/s, done.
Resolving deltas: 100% (139/139), done.
Processing /home/kali/sstv
  Preparing metadata (setup.py) ... done
Requirement already satisfied: numpy in /usr/lib/python3/dist-packages (from sstv==0.1) (2.3.5)
Requirement already satisfied: Pillow in /usr/lib/python3/dist-packages (from sstv==0.1) (11.3.0)
Collecting PySoundFile (from sstv==0.1)
  Downloading PySoundFile-0.9.0.post1-py2.py3-none-any.whl.metadata (9.4 kB)
Requirement already satisfied: scipy in /usr/lib/python3/dist-packages (from sstv==0.1) (1.16.3)
Requirement already satisfied: cffi>=0.6 in /usr/lib/python3/dist-packages (from PySoundFile->sstv==0.1) (2.0.0)
Requirement already satisfied: pycparser in /usr/lib/python3/dist-packages (from cffi>=0.6->PySoundFile->sstv==0.1) (2.23)
Downloading PySoundFile-0.9.0.post1-py2.py3-none-any.whl (24 kB)
Building wheels for collected packages: sstv
  DEPRECATION: Building 'sstv' using the legacy setup.py bdist_wheel mechanism, which will be removed in a future version. pip 25.3 will enforce this behaviour change. A possible replacement is to use the standardized build interface by setting the `--use-pep517` option, (possibly combined with `--no-build-isolation`), or adding a `pyproject.toml` file to the source tree of 'sstv'. Discussion can be found at https://github.com/pypa/pip/issues/6334                                                     
  Building wheel for sstv (setup.py) ... done                                       
  Created wheel for sstv: filename=sstv-0.1-py3-none-any.whl size=21571 sha256=612299026f1f216f5fb2042b0b3d899758ba489f50324c747fa90505fdc904a5
  Stored in directory: /tmp/pip-ephem-wheel-cache-b6yh1c5r/wheels/51/16/bd/ffe7502803a0a1878a8ba04ba9b249aa7231ff30d3d6e891cf
Successfully built sstv
Installing collected packages: PySoundFile, sstv
Successfully installed PySoundFile-0.9.0.post1 sstv-0.1
WARNING: Running pip as the 'root' user can result in broken permissions and conflicting behaviour with the system package manager, possibly rendering your system unusable. It is recommended to use a virtual environment instead: https://pip.pypa.io/warnings/venv. Use the --root-user-action option if you know what you are doing and want to suppress this warning.                                                         
                                                                                    
┌──(kali㉿kali)-[~/sstv]
└─$ sstv -d message.wav -o flag.png
usage: sstv [-h] [-d AUDIO_FILE] [-o OUTPUT_FILE] [-s SKIP] [-V] [--list-modes]
            [--list-audio-formats] [--list-image-formats]
sstv: error: argument -d/--decode: can't open 'message.wav': [Errno 2] No such file or directory: 'message.wav'
                                                                                    
┌──(kali㉿kali)-[~/sstv]
└─$ cd   
                                                                                    
┌──(kali㉿kali)-[~]
└─$ sstv -d message.wav -o flag.png
[sstv] Searching for calibration header... Found!    
[sstv] Detected SSTV mode Scottie 1
[sstv] Decoding image...   [##################################################] 100%
[sstv] Drawing image data...
[sstv] ...Done!
                                                                                    
┌──(kali㉿kali)-[~]
└─$ xdg-open flag.png
                                                                                    
┌──(kali㉿kali)-[~]
└─$ sstv -d message.wav -o flagg.png
[sstv] Searching for calibration header... Found!    
[sstv] Detected SSTV mode Scottie 1
[sstv] Decoding image...   [##################################################] 100%
[sstv] Drawing image data...
[sstv] ...Done!
                                                                                    
┌──(kali㉿kali)-[~]
└─$ xdg-open flagg.png  
picoCTF{beep_boop_im_in_space}
```
## Notas adicionales 

## Referencias


