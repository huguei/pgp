# CEREMONIA DE FIRMA DE LLAVES PGP

## TL;DR
  * ANTES: enviar su llave pública al organizador, por email
  * EN LA CEREMONIA: llevar documento(s) de identificación, y copia personal de propio fingerprint
  * DESPUÉS: firmar y enviar a los participantes. *NO SUBIR* a keyservers

## ¿DE QUÉ SE TRATA UNA CEREMONIA DE FIRMA DE LLAVES PGP?

Una ceremonia de firmas de llaves PGP (PGP keysigning party) es
una actividad en grupo donde cada participante demuestra ser dueño
de alguna llave PGP, y el resto testifica esta relación físico/virtual
mediante la firma con sus propias llaves.

Esta actividad es el fundamento de la arquitectura
de "peer-to-peer" de PGP, en contraste con otros esquemas de
"autoridad" (notaría) como PKI.

Para esto es necesaria una reunión física donde yo me identifico como
Hugo Salgado, lo demuestro con mis documentos de identidad, y dicto mi
llave (en realidad el fingerprint de mi llave). El resto de participantes
revisa una copia del fingerprint y toma notas de mi identidad (solo el
nombre, no se debe copiar números ni otros datos), para luego testificar
con sus firmas la certeza que la llave 0xF120A230 pertenece a un humano
llamado Hugo Salgado, con el correo hsalgado@nic.cl.


## PASOS DE UNA CEREMONIA DE FIRMA DE LLAVES PGP

1. previo a la ceremonia se debe enviar sus llaves públicas al organizador,
   por email.

2. el día del evento, deben llevar

  1. al menos un documento de identificación (mejor si son dos)
    donde se vea su fotografía y nombre completo (pasaporte,
    documento de identidad nacional, cédula de conducir, etc)

  2. una copia personal del fingerprint de su llave. Puede ser
    en cualquier medio que deseen, mientras estén seguros que
    es confiable (en su propio computador, tablet, teléfono,
    incluso escrita en un papel).

    Pueden obtener su fingerprint con gpg:
      `% gpg --fingerprint hsalgado@nic.cl`
    (es el valor de la línea 'Key fingerprint = ....' )

3. al comenzar la ceremonia se les entregará una hoja impresa
  con los fingerprints de todos los participantes.
  
4. Luego cada uno de los participantes en el orden de la hoja dictarán a
  viva voz su propio fingerprint, LEIDO DESDE SU PROPIO LUGAR privado
  del punto 2.1. Para leerlo se utiliza el alfabeto de
  radiotelefonía internacional (zero, one, two, three... alfa,
  bravo, charlie, delta, echo, foxtrot)

  El resto de participantes va verificando en sus hojas que el
  fingerprint sea el correcto.

5. Luego se arma un "carrusel" con todos los participantes,
  donde cada uno va mostrando sus documentos de identidad al
  resto de personas. Cada uno va tomando sus propias notas en
  las hojas, dependiendo del grado de confianza que le merezca.

  Es importante no copiar en las notas ninguna información de
  los documentos (números, fechas, etc), sino solo comprobar
  que el nombre es el correcto.

6. Fin de la ceremonia. Cada participante se lleva su hoja con
  sus  notas.

7. El organizador enviará a todos los participantes una keyring
  con todas las llaves del resto

8. Luego, esa noche o con calma al volver a su casa, cada
  participante firmará las llaves que le dieron confianza,
  basado en la hoja con sus notas.

  Las llaves firmadas se deben enviar a LOS PROPIOS DUEÑOS
  de las llaves, en manera encriptada. NO SUBIR A LOS
  KEYSERVERS, ya que eso se dejará a criterio de cada dueño
  de su llave.

  Se recomienda la herramienta "caff" del paquete pgp-tools.

