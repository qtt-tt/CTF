# Nombre del reto
>repetitions

---
# Descripción
>Can you make sense of this file?
>
>Download the file [here](https://artifacts.picoctf.net/c/474/enc_flag).

---
# Solución
Para comenzar con su solución, realizamos un wget para descargar el archivo llamado enc_flag, al realizarle un cat nos da una cadena bastante interesante.
```bash
wget https://artifacts.picoctf.net/c/474/enc_flag
cat enc_flag
VmpGU1EyRXlUWGxTYmxKVVYwZFNWbGxyV21GV1JteDBUbFpPYWxKdFVsaFpWVlUxWVZaS1ZWWnVh
RmRXZWtab1dWWmtSMk5yTlZWWApiVVpUVm10d1VWZFdVa2RpYlZaWFZtNVdVZ3BpU0VKeldWUkNk
MlZXVlhoWGJYQk9VbFJXU0ZkcVRuTldaM0JZVWpGS2VWWkdaSGRXCk1sWnpWV3hhVm1KRk5XOVVW
VkpEVGxaYVdFMVhSbFZhTTBKUFdXdGtlbVF4V2tkWGJYUllDbUY2UWpSWmEyaFRWakpHZEdWRlZs
aGkKYlRrelZERldUMkpzUWxWTlJYTkxDZz09Cg==
```
Ahora, en base64 encontramos que la longitud siempre es múltiplo de 4, algo característico es que si la cadena no cumple esta condición, se suele usar signos de = para completar la longitud.
Ahora, llevaremos la cadena a cyberchef para descubrir algo bastante curioso, nos da otra cadena que parece base64, por lo que se llevó varias veces.
1. [Primera decodificación](https://toolbox.itsec.tamu.edu/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)&input=Vm1wR1UxRXlSWGxVV0d4VFlteEtWVll3WkZOV2JHeHlWMjFHVjFKdGVEQlViRnBQWVd4S2RGVnNhRnBXVmxVeFdWWmFTMVpXV25WaA0KUm1SWFpXdGFiMWRXV210U01rNXlUbFpXV0FwaVZWcFVWbTEwZDFWV1pGZFZhMlJwWWxaYVdGWnROVmRWWjNCcFUwVktlbGRXVWtOaw0KTWxaWFZsaG9XR0pZUWs5VmJGSlhVMFprY1ZSdVRsZGFNMEpaVldwR1MyVldXa2RhU0dSWENrMXNXbnBXVjNoaFZtMUtSazVYT1ZWVw0KVmtwRVZHeGFZVmRGTVZoU2JGWmhUVEJLVUZkWGRHdGxiVkY0VjJ0a1dHSllVbGxEYlVZMlVXcFNXbUV5YUZSV2FrcEhaRWRXUmxacw0KYUdrS1lsUnJlbFpFUmxkVU1rcHpVV3hXVGxKWVRreERaejA5Q2c9PQ).
2. [Segunda decodificación](https://toolbox.itsec.tamu.edu/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)&input=VmpGU1EyRXlUWGxTYmxKVVYwZFNWbGxyV21GV1JteDBUbFpPYWxKdFVsaFpWVlUxWVZaS1ZWWnVhRmRXZWtab1dWWmtSMk5yTlZWWApiVVpUVm10d1VWZFdVa2RpYlZaWFZtNVdVZ3BpU0VKeldWUkNkMlZXVlhoWGJYQk9VbFJXU0ZkcVRuTldaM0JZVWpGS2VWWkdaSGRXCk1sWnpWV3hhVm1KRk5XOVVWVkpEVGxaYVdFMVhSbFZhTTBKUFdXdGtlbVF4V2tkWGJYUllDbUY2UWpSWmEyaFRWakpHZEdWRlZsaGkKYlRrelZERldUMkpzUWxWTlJYTkxDZz09).
3. [Tercera decodificación](https://toolbox.itsec.tamu.edu/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)&input=VjFSQ2EyTXlSblJUV0dSVllrWmFWRmx0TlZOalJtUlhZVVU1YVZKVVZuaFdWekZoWVZkR2NrNVVXbUZTVmtwUVdWUkdibVZXVm5WUgpiSEJzWVRCd2VWVXhXbXBOUlRWSFdqTnNWZ3BYUjFKeVZGZHdWMlZzVWxaVmJFNW9UVVJDTlZaWE1XRlVaM0JPWWtkemQxWkdXbXRYCmF6QjRZa2hTVjJGdGVFVlhibTkzVDFWT2JsQlVNRXNL).
4. [Cuarta decodificación](https://toolbox.itsec.tamu.edu/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)&input=V1RCa2MyRnRTWGRVYkZaVFltNVNjRmRXYUU5aVJUVnhWVzFhYVdGck5UWmFSVkpQWVRGbmVWVnVRbHBsYTBweVUxWmpNRTVHWjNsVgpXR1JyVFdwV2VsUlZVbE5oTURCNVZXMWFUZ3BOYkdzd1ZGWmtXazB4YkhSV2FteEVXbm93T1VOblBUMEs).
5. [Quinta decodificación](https://toolbox.itsec.tamu.edu/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)&input=WTBkc2FtSXdUbFZTYm5ScFdWaE9iRTVxVW1aaWFrNTZaRVJPYTFneVVuQlpla0pyU1ZjME5GZ3lVWGRrTWpWelRVUlNhMDB5VW1aTgpNbGswVFZkWk0xbHRWamxEWnowOUNnPT0).
6. [Sexta decodificación](https://toolbox.itsec.tamu.edu/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)&input=Y0dsamIwTlVSbnRpWVhObE5qUmZiak56ZEROa1gyUnBZekJrSVc0NFgyUXdkMjVzTURSa00yUmZNMlk0TVdZM1ltVjlDZz09).
Llegando directamente a la bandera

---
# Flag del reto
>picoCTF{base64_n3st3d_dic0d!n8_d0wnl04d3d_3f81f7be}

---
# Notas adicionales

---
# Referencias

Se investigó como identificar [base64](https://chatgpt.com/share/698bec08-5020-800b-8335-18b5e09c647d).