# CÓMO FIRMAR UTILIZANDO CAFF

Existe una herramienta que automatiza el firmado, encriptado y envío por correo de las llaves luego de una ceremonia PGP. Se trata de "caff", parte del paquete pgp-tools <https://pgp-tools.alioth.debian.org/> . Al menos en distribuciones Fedora y Ubuntu viene en los repositorios, por lo que es muy simple de instalar.

Luego de instalado, se ejecuta por primera vez para que cree la estructura de directorios y un archivo de configuración.

1. `% caff`

2. luego es importante revisar el archivo ~/.caffrc, para ajustar la configuración. Lo más importante es "owner", "email" y "keyid"; son sus propios datos. También en mi caso tengo que definir "mailer-send", para declarar cómo se despachan los correos. En mi caso uso un smtp externo, y se declara de este estilo:

    `$CONFIG{'mailer-send'} =  [ 'smtp', Server => '1.2.3.4', Port => '25' ];`

3. Con eso ya está listo.

4. Firmar la(s) llave(s):

   `% caff 11223344556677 11223344556688 ...`

   Importante es revisar que en la configuración tengan "no-download" con valor 0, para que baje las llaves de los keyservers. Si quieren que utilice las llaves desde su gnupg homedir, tienen que darle la opción "--keys-from-gnupg" a caff, para que las copie a su repositorio interno.

   caff irá preguntando paso por paso, y finalmente enviará los correos cifrados a los destinatarios.

