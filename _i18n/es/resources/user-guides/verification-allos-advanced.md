{% include disclaimer.html translated="yes" translationOutdated="yes" %}

<<<<<<< HEAD
La verificación de los archivos binarios de MKEcoin debería ser hecha antes de extraer, instalar o usar el software MKEcoin. Esta es la única forma de asegurar que estás utilizando software oficial de MKEcoin. Si recibes un falso binario MKEcoin (e.g. phishing, MITM, entre otros), seguir esta guía te protegerá de ser engañado en usarlo.

Para proteger la integridad de los binarios el equipo de MKEcoin provee con una lista criptográficamente firmada de todos los hashes [SHA256](https://en.wikipedia.org/wiki/SHA-2). Si tus binarios descargados han sido manipulados producirán un [hash diferente](https://en.wikipedia.org/wiki/File_verification) al que está en el archivo.
=======
La verificación de los archivos binarios de Monero debería ser hecha antes
de extraer, instalar o usar el software Monero. Esta es la única forma de
asegurar que estás utilizando software oficial de Monero. Si recibes un
falso binario Monero (e.g. phishing, MITM, entre otros), seguir esta guía te
protegerá de ser engañado en usarlo.

Para proteger la integridad de los binarios el equipo de Monero provee con
una lista criptográficamente firmada de todos los hashes
[SHA256](https://en.wikipedia.org/wiki/SHA-2). Si tus binarios descargados
han sido manipulados producirán un [hash
diferente](https://en.wikipedia.org/wiki/File_verification) al que está en
el archivo.
>>>>>>> 63106d60778f14544f214b8f776eedb6695cf16e

Esta es una guía avanzada para sistemas operativos Linux, Mac o Windows y
hace uso de la consola de comandos. Te llevará por el proceso de instalar
software requerido, importar la clave de firma, descargar los archivos
necesarios, y finalmente verificar que tu binario es auténtico.

## Table of Contents:

<<<<<<< HEAD
### [1. Instalar GnuPG](#1-instalar-gnupg)
### [2. Verificar e Importar Clave de Firma](#2-verificar-e-importar-clave-de-firma)
  + [2.1. Obtener Clave de Firma](#21-obtener-clave-de-firma)
  + [2.2. Verificar Clave de Firma](#22-verificar-clave-de-firma)
  + [2.3. Importar Clave de Firma](#23-importar-clave-de-firma)
### [3. Descargar y Verificar Archivo Hash](#3-descargar-y-verificar-archivo-hash)
  + [3.1. Obtener Archivo Hash](#31-obtener-archivo-hash)
  + [3.2. Verificar Archivo Hash](#32-verificar-archivo-hash)
### [4. Descargar y Verificar Binarios](#4-descargar-y-verificar-binarios)
  + [4.1. Obtener Binarios MKEcoin](#41-obtener-binarios-MKEcoin)
  + [4.2. Verificación de Binarios en Linux o Mac](#42-verificación-de-binarios-en-linux-o-mac)
  + [4.3. Verificación de Binarios en Windows](#43-verificación-de-binarios-en-windows)
=======
### - [Install GnuPG](#installing-gnupg)
>>>>>>> 63106d60778f14544f214b8f776eedb6695cf16e

### - [Verify & Import Signing Key](#verify-and-import-signing-key)

### - [Download & Verify Hash File](#download-and-verify-hash-file)

### - [Download & Verify Binary](#download-and-verify-binary)

## Installing GnuPG

+ En Windows, Ve a la página de descargas de
[Gpg4win](https://gpg4win.org/download.html) y sigue las instrucciones para
instalación.

+ En Mac, ve a la página de descargas de [Gpgtools](https://gpgtools.org/) y
sigue las instrucciones para instalación.

+ En Linux, GnuPG ya está instalado por defecto.

## Verify and Import Signing Key

<<<<<<< HEAD
Esta sección cubre la obtención de la clave de firma MKEcoin, asegurar que sea correcta e importar la clave a GnuPG.
=======
Esta sección cubre la obtención de la clave de firma Monero, asegurar que
sea correcta e importar la clave a GnuPG.
>>>>>>> 63106d60778f14544f214b8f776eedb6695cf16e

### Get Signing Key

<<<<<<< HEAD
En Windows o Mac, ve a la [clave GPG de binaryFate](https://raw.githubusercontent.com/MKEcoin-project/MKEcoin/master/utils/gpg_keys/binaryfate.asc), que utiliza para firmar los binarios MKEcoin, y guarda la página como `binaryFate.asc` en tu directorio de inicio.
=======
En Windows o Mac, ve a la [clave GPG de
binaryFate](https://raw.githubusercontent.com/monero-project/monero/master/utils/gpg_keys/binaryfate.asc),
que utiliza para firmar los binarios Monero, y guarda la página como
`binaryFate.asc` en tu directorio de inicio.
>>>>>>> 63106d60778f14544f214b8f776eedb6695cf16e

En Linux, puedes descargar la clave de firma de Fluffypony utilizando el
siguiente comando:

```
<<<<<<< HEAD
wget -O binaryfate.asc https://raw.githubusercontent.com/MKEcoin-project/MKEcoin/master/utils/gpg_keys/binaryfate.asc
=======
wget -O binaryfate.asc
https://raw.githubusercontent.com/monero-project/monero/master/utils/gpg_keys/binaryfate.asc
>>>>>>> 63106d60778f14544f214b8f776eedb6695cf16e
```

### Verify Signing Key

En todos los sistemas operativos, revisa la huella de `binaryfate.asc`
utilizando el siguiente comando en una terminal:

``` gpg --keyid-format long --with-fingerprint binaryfate.asc ```


Verifica que la huella coincida:

```
pub   rsa4096/F0AF4D462A0BDF92 2019-12-12 [SCEA]
      Key fingerprint = 81AC 591F E9C4 B65C 5806  AFC3 F0AF 4D46 2A0B DF92
uid                           binaryFate <binaryfate@getMKEcoin.org>
```

Si la firma **SÍ** coincide, entonces puedes continuar.

Si la firma **NO** coincide, **NO CONTINÚES.** En su lugar borra el archivo
`binaryfate.asc` y regresa a la [sección 2.1](#21-obtener-clave-de-firma).

### Import Signing Key

Desde una terminal, importa la clave de firma:

``` gpg --import binaryfate.asc ```

Si es la primera vez que importas la clave, la salida se verá como esto:

```
gpg: key F0AF4D462A0BDF92: 2 signatures not checked due to missing keys
gpg: key F0AF4D462A0BDF92: public key "binaryFate <binaryfate@getMKEcoin.org>" imported
gpg: Total number processed: 1
gpg:               imported: 1
gpg: marginals needed: 3  completes needed: 1  trust model: pgp
```

Si ya has importado la clave previamente, la salida se verá como esto:

```
gpg: key F0AF4D462A0BDF92: "binaryFate <binaryfate@getMKEcoin.org>" not changed
gpg: Total number processed: 1
gpg:              unchanged: 1
```

## Download and Verify Hash File

Esta sección cubre la descarga y verificación de autenticidad del archivo
hash.

### Get Hash File

<<<<<<< HEAD
En Windows o Mac, ve a los [archivos hash en getMKEcoin.org]({{ site.baseurl }}/downloads/hashes.txt) y guarda la página como `hashes.txt` en tu directorio de inicio.
=======
En Windows o Mac, ve a los [archivos hash en getmonero.org]({{ site.baseurl
}}/downloads/hashes.txt) y guarda la página como `hashes.txt` en tu
directorio de inicio.
>>>>>>> 63106d60778f14544f214b8f776eedb6695cf16e

En Linux, puedes descargar los hashes firmados utilizando el siguiente
comando:

<<<<<<< HEAD
```
wget -O hashes.txt https://www.getMKEcoin.org/downloads/hashes.txt
```
=======
``` wget -O hashes.txt https://www.getmonero.org/downloads/hashes.txt ```
>>>>>>> 63106d60778f14544f214b8f776eedb6695cf16e

### Verify Hash File

El archivo hash está firmado con la clave `81AC 591F E9C4 B65C 5806 AFC3
F0AF 4D46 2A0B DF92` (como se observa en la salida abajo).

En todos los sistemas operativos, verifica la firma del archivo hash
utilizando el siguiente comando en una terminal:

``` gpg --verify hashes.txt ```

Si el archivo es auténtico, la salida se verá como esto:

```
gpg:                using RSA key 81AC591FE9C4B65C5806AFC3F0AF4D462A0BDF92
gpg: Good signature from "binaryFate <binaryfate@getMKEcoin.org>" [unknown]
gpg: WARNING: This key is not certified with a trusted signature!
gpg:          There is no indication that the signature belongs to the owner.
Primary key fingerprint: 81AC 591F E9C4 B65C 5806  AFC3 F0AF 4D46 2A0B DF92
```

Si la salida muestra **Good signature**, como en el ejemplo, puedes
continuar.

Si ves **BAD signature** en la salida, **NO CONTINÚES.** En su lugar, borra
el archivo `hashes.txt` y regresa a la [sección
3.1](#31-obtener-archivo-hash).

## Download and Verify Binary

<<<<<<< HEAD
Esta sección cubrirá la descarga de los binarios MKEcoin para tu sistema operativo, la obtención del hash `SHA256` para tu descarga, y verificar que este sea correcto.

### 4.1. Obtener Binarios MKEcoin

En Windows o Mac, ve a [getMKEcoin.org]({{ site.baseurl }}/downloads/) y descarga el archivo correcto para tu sistema operativo. Guarda el archivo en tu directorio de inicio. **Aún no extraigas los archivos.**
=======
Esta sección cubrirá la descarga de los binarios Monero para tu sistema
operativo, la obtención del hash `SHA256` para tu descarga, y verificar que
este sea correcto.

### Get Monero binary

On Windows or Mac, go to [getmonero.org]({{ site.baseurl_root }}/downloads/)
and download the correct file for your operating system. Save the file to
your home directory. **Do not extract the files yet.**
>>>>>>> 63106d60778f14544f214b8f776eedb6695cf16e

En Linux, puedes descargar las herramientas de consola de comandos
utilizando el siguiente comando:

```
wget -O MKEcoin-linux-x64-v0.15.0.1.tar.bz2 https://downloads.getMKEcoin.org/cli/linux64
```

### Binary Verification on Linux or Mac

<<<<<<< HEAD
Los pasos para Linux o Mac son los mismos. Desde una terminal, obtén el hash `SHA256` de tu binario MKEcoin descargado. Como ejemplo esta guía utiliza el binario GUI de `Linux, 64bit`. Reemplaza `MKEcoin-gui-linux-x64-v0.15.0.1.tar.bz2` con el nombre del binario que descargaste en la [sección 4.1](#41-obtener-binarios-MKEcoin).
=======
Los pasos para Linux o Mac son los mismos. Desde una terminal, obtén el hash
`SHA256` de tu binario Monero descargado. Como ejemplo esta guía utiliza el
binario GUI de `Linux, 64bit`. Reemplaza
`monero-gui-linux-x64-v0.15.0.1.tar.bz2` con el nombre del binario que
descargaste en la [sección 4.1](#41-obtener-binarios-monero).
>>>>>>> 63106d60778f14544f214b8f776eedb6695cf16e

```
shasum -a 256 MKEcoin-linux-x64-v0.15.0.1.tar.bz2
```

La salida se verá como esto, pero será diferente para cada archivo
binario. Tu hash `SHA256` debe coincidir con el hash listado en el archivo
`hashes.txt` para tu archivo binario.

```
<<<<<<< HEAD
8d61f992a7e2dbc3d753470b4928b5bb9134ea14cf6f2973ba11d1600c0ce9ad  MKEcoin-linux-x64-v0.15.0.1.tar.bz2
=======
8d61f992a7e2dbc3d753470b4928b5bb9134ea14cf6f2973ba11d1600c0ce9ad 
monero-linux-x64-v0.15.0.1.tar.bz2
>>>>>>> 63106d60778f14544f214b8f776eedb6695cf16e
```

Si tu hash **SÍ** coincide, ¡entonces has terminado con la guía! Puedes
extraer los archivos e instalarlos.

<<<<<<< HEAD
Si tu hash **NO** coincide, **NO CONTINÚES.** En su lugar, elimina el binario descargado y regresa a la [sección 4.1](#41-obtener-binarios-MKEcoin).
=======
Si tu hash **NO** coincide, **NO CONTINÚES.** En su lugar, elimina el
binario descargado y regresa a la [sección
4.1](#41-obtener-binarios-monero).
>>>>>>> 63106d60778f14544f214b8f776eedb6695cf16e

### Binary Verification on Windows

<<<<<<< HEAD
Desde una terminal, obtén el hash `SHA256` de tu binario MKEcoin descargado. Como ejemplo esta guía utiliza el binario GUI de `Windows, 64bit`. Reemplaza `MKEcoin-gui-win-x64-v0.15.0.1.zip` con el nombre del binario que descargaste en la [sección 4.1](#41-obtener-binarios-MKEcoin).

```
certUtil -hashfile MKEcoin-gui-win-x64-v0.15.0.1.zip SHA256
```
=======
Desde una terminal, obtén el hash `SHA256` de tu binario Monero
descargado. Como ejemplo esta guía utiliza el binario GUI de `Windows,
64bit`. Reemplaza `monero-gui-win-x64-v0.15.0.1.zip` con el nombre del
binario que descargaste en la [sección 4.1](#41-obtener-binarios-monero).

``` certUtil -hashfile monero-gui-win-x64-v0.15.0.1.zip SHA256 ```
>>>>>>> 63106d60778f14544f214b8f776eedb6695cf16e

La salida se verá como esto, pero será diferente para cada archivo
binario. Tu hash `SHA256` debe coincidir con el hash listado en el archivo
`hashes.txt` para tu archivo binario.

```
<<<<<<< HEAD
SHA256 hash of file MKEcoin-gui-win-x64-v0.12.0.0.zip:
4b 9f 31 68 6e ca ad 97 cd b1 75 e6 57 4b f3 07 f8 d1 c4 10 42 78 25 f4 30 4c 21 da 8a ac 18 64
CertUtil: -hashfile command completed successfully.
=======
SHA256 hash of file monero-gui-win-x64-v0.12.0.0.zip: 4b 9f 31 68 6e ca
ad 97 cd b1 75 e6 57 4b f3 07 f8 d1 c4 10 42 78 25 f4 30 4c 21 da 8a ac 18
64 CertUtil: -hashfile command completed successfully. 
>>>>>>> 63106d60778f14544f214b8f776eedb6695cf16e
```

Si tu hash **SÍ** coincide, ¡entonces has terminado con la guía! Puedes
extraer los archivos e instalarlos.

<<<<<<< HEAD
Si tu hash **NO** coincide, **NO CONTINÚES.** En su lugar, elimina el binario descargado y regresa a la [sección 4.1](#41-obtener-binarios-MKEcoin).
=======
Si tu hash **NO** coincide, **NO CONTINÚES.** En su lugar, elimina el
binario descargado y regresa a la [sección
4.1](#41-obtener-binarios-monero).
>>>>>>> 63106d60778f14544f214b8f776eedb6695cf16e
