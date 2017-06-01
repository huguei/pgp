# CÓMO FIRMAR UTILIZANDO GPG

Este método es el más simple en el sentido que no requiere la utilización de ninguna otra herramienta aparte de "gpg", pero al ser manual es más trabajosa.

Supongamos que luego de una ceremonia de firma confío en el fingerprint del correo "usuario@ejemplo.cl" 

1. importar la llave a firmar:
     `% gpg --import usuario.asc`

2. editar la llave y verificar el fingerprint
```
% gpg --edit usuario@ejemplo.cl
[ ... ]

gpg> fpr
```

   verificar que el fingerprint indicado sea el mismo que el dictado por la propia persona en la ceremonia. Además revisar nombre y correo.

3. seleccionar el UID correspondiente que se quiere firmar, de acuerdo al número indicado entre paréntesis al lado de la identidad.
     `gpg> uid 1`

   el seleccionado queda con un asterisco.

4. confiar:
     `gpg> trust`

   acá definen el grado de confianza que les da la identidad. Si verificaron pasaporte y más de una identidad (a vuestro criterio), entonces pueden escoger el grado de confianza.

5. firmar
     `gpg> sign`

   solicitará su contraseña de la llave privada.

6. guardar
     `gpg> save`

7. Luego de eso pueden exportar la llave firmada y enviársela al usuario. Es ideal que se envíe ENCRIPTADA, para además asegurar que la persona es capaz de descifrar el correo, agregando un grado más de seguridad.

     `gpg --export -a usuario@ejemplo.cl > usuario-con-mi-firma.asc`

8. También es posible subir la llave a algún keyserver, para que mi firma sea pública y cualquiera pueda verificarla. Pero *OJO*, que hay ciertos usuarios que prefieren no tener su llave en los keyservers públicos, y otros que aunque la tengan prefieren no subir las firmas de otros usuarios (por temas de privacidad). Es recomendable consultar antes de subir a keyservers.


