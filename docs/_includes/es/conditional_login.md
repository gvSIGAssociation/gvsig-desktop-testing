${check} Si se presenta la ventana de título "Inicio de sesión de usuario":
* ${check} Introduzca en el campo de texto "Usuario" el valor ```${USER}``` (USER)  {% include var_copy.html var="USER"%}
  * ${check} Introduzca en el campo de texto "Contraseña" el valor ```${PASSWORD}``` (PASSWORD)  {% include var_copy.html var="USER"%}.
  * ${check} Pulse el botón "Aceptar".
  * ${check} Se cerrara la venta de inicio de sesión y le devolverá a la ventana en la que estuviese trabajando.
