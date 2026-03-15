# Actividad: Validación de XML con XSD y RegEx

## Expresiones Regulares

* **Correo Electrónico (`email`)**
  * **RegEx:** `^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$`
  * **Explicación:** Valida que el correo tenga texto, el símbolo `@`, un dominio y una extensión final de 2 o más letras (como .com o .es).

* **Teléfono (`telefono`)**
  * **RegEx:** `^(\+34)?[6-9][0-9]{8}$`
  * **Explicación:** Formato de España. Son 9 números obligatorios que empiezan por 6, 7, 8 o 9. Permite poner de forma opcional el `+34` al principio.

* **Código Postal (`codigoPostal`)**
  * **RegEx:** `^(0[1-9]|[1-4][0-9]|5[0-2])[0-9]{3}$`
  * **Explicación:** Código postal español de 5 cifras. Los dos primeros números tienen que estar entre el 01 y el 52 obligatoriamente.

* **Nombre de Usuario (`nombreUsuario`)**
  * **RegEx:** `^[a-z][a-zA-Z0-9]{2,14}$`
  * **Explicación:** Obliga a que la primera letra sea minúscula. Permite letras y números con una longitud total de entre 3 y 15 caracteres.

* **Contraseña (`contrasena`)**
  * **RegEx:** `^(?=.*[a-z])(?=.*[A-Z])(?=.*\d)(?=.*[\W_]).{8,}$`
  * **Explicación:** Exige mínimo 8 caracteres, mezclando mayúsculas, minúsculas, números y símbolos. 
  * **Nota sobre el XSD:** Como la versión 1.0 de XSD da error con expresiones regulares tan complejas, en el código he aplicado esta regla usando la etiqueta `<xs:minLength value="8"/>` junto a un patrón básico de los caracteres que están permitidos.