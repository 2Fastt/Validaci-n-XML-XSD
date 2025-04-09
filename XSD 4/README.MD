Ejercicio 1 - Alumnos 1

Diseña el esquema XSD para el siguiente archivo XML con las siguientes
consideraciones:
• El elemento número será un entero entre 0 y 500.
• El elemento teléfono será un entero y dicho elemento podrá aparecer entre 0 y 5
veces.
• El atributo dni será una plantilla de 8 números y una letra mayúscula.

<?xml version="1.0" encoding="UTF-8"?>
<alumno dni="12345678A"
xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
xsi:noNamespaceSchemaLocation="alumno.xsd">
<nombre>Juan Garcia</nombre>
<direccion>
<calle>Avenida de la Fuente</calle>
<numero>6</numero>
<ciudad>Zafra</ciudad>
<provincia>Badajoz</provincia>
</direccion>
<telefono>924555555</telefono>
<telefono>658741236</telefono>
</alumno>
Ejercicio 2 - Alumnos 2

Diseña el esquema XSD para el siguiente archivo XML con las siguientes
consideraciones:
• El elemento número será un entero entre 0 y 500.
• El elemento teléfono será un entero y dicho elemento podrá aparecer entre 0 y 5
veces.
• El elemento dirección podrá aparecer 1 o 2 veces.
• El elemento provincia sólo podrá contener Badajoz o Cáceres. Modifica el alumno
Juan Andrés para que su provincia sea Cáceres.
• El atributo dni será una plantilla de 8 números y una letra mayúscula.

<?xml version="1.0" encoding="UTF-8"?>
<alumnos xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
xsi:noNamespaceSchemaLocation="alumnos.xsd">
<alumno dni="11111111A">
<nombre>Juan Andrés</nombre>
<direccion>
<calle>Avenida de la Fuente</calle>
<numero>6</numero>
<ciudad>Zafra</ciudad>
<provincia>Badajoz</provincia>
</direccion>
<telefono>924555555</telefono>
</alumno>
<alumno dni="22222222B">
<nombre>Jose Sanchez</nombre>
<direccion>
<calle>Calle Ancha</calle>
<numero>3</numero>
<ciudad>Zafra</ciudad>
<provincia>Badajoz</provincia>
</direccion>
<direccion>
<calle>Calle Mayor</calle>
<numero>33</numero>
<ciudad>Zafra</ciudad>
<provincia>Badajoz</provincia>
</direccion>
<telefono>924550000</telefono>
</alumno>
</alumnos>

Ejercicio 3 - Heladería 1

Diseña el esquema XSD para el siguiente archivo XML con las siguientes
consideraciones:
• Como primer elemento de helado podemos elegir, o bien chocolate, o bien fresa
(pero no los dos al mismo tiempo). Estos elementos almacenarán la cantidad en
gramos (como un número entero entre 0 y 1000).
• Como segundo elemento de helado se podrá elegir uno de los siguientes vainilla,
turrón o nata. Estos elementos almacenarán la cantidad en gramos (como un
número entero entre 0 y 1000).
• El atributo fabricación indicará la fecha en la que se fabricó el mismo mediante
el tipo de dato fecha.

<?xml version="1.0" encoding="UTF-8"?>
<heladeria xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
xsi:noNamespaceSchemaLocation="heladeria.xsd">
<helado fabricación="2015-01-30">
<chocolate>250</chocolate>
<turron>300</turron>
</helado>
<helado fabricación="2015-01-30">
<fresa>500</fresa>
<vainilla>200</vainilla>
</helado>
</heladeria>

Ejercicio 4 - Heladería 2

Diseña el esquema XSD para el siguiente archivo XML con las siguientes
consideraciones:
• El helado sólo puede ser de fresa y chocolate, o bien, de vainilla y chocolate.
• Los sabores serán elementos vacíos.

<?xml version="1.0" encoding="UTF-8"?>
<heladeria xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
xsi:noNamespaceSchemaLocation="heladeria.xsd">
<helado>
<fresa />
<chocolate />
</helado>
<helado>
<vainilla />
<chocolate />
</helado>
</heladeria>

Ejercicio 5 - FAQ

Diseña el esquema XSD para el siguiente archivo XML con las siguientes
consideraciones:
• El elemento versión será una plantilla que permita números seguidos de un punto
y seguido de más números.
• El elemento fecha será de tipo fecha.
• El elemento faq está compuesto por solo un elemento info y por uno o más
elementos part.
• El elemento info está compuesto por un titulo, un autor, y puede tener o no email,
versión y fecha.
• El elemento part puede tener uno o más elementos q.
• El elemento q está compuesto por los elementos qtext y a que son obligatorios.

<?xml version="1.0" encoding="UTF-8" ?>
<faq>
<info>
<titulo>WINDOWS98? SOLO SI ME OBLIGAN!</titulo>
<autor>Fernando Damián Lorenzo García</autor>
<email>Fer@yahoo.es </email>
<version>1.0</version>
<fecha>1999-05-01</fecha>
</info>
<part>
<q>
<qtext>¿Por qué tengo que instalar W95?</qtext>
<a> A mi también me parece una buena pregunta.</a>
</q>
<q>
<qtext>Y de que me vale?</qtext>
<a>Otra ingeniosa pregunta.</a>
</q>
</part>
</faq>

Ejercicio 6 - Librería

Diseña el esquema XSD para el siguiente archivo XML con las siguientes
consideraciones:
• La librería tiene obligatoriamente un código, una dirección, un teléfono, un
propietario, y uno o más libros.
• El código será un número entero entre 1000 y 9999.
• El propietario tiene un nombre y puede tener ninguno o varios teléfonos.
• El teléfono sólo se definirá una vez en el esquema, repitiendo su uso. Su
contenido será una plantilla de 9 números.
• Cada libro está formado por los elementos título, autor, puede tener o no formato,
publicación, precio, cantidad.
• El formato podrá ser rústica, tapa blanda o tapa dura.

<?xml version="1.0" encoding="UTF-8" ?>
<libreria>
<codigo>1263</codigo>
<direccion>Juan de Juni, 31</direccion>
<telefono>983555555</telefono>
<propietario>
<nombre>Juanito</nombre>
<telefono>656222111</telefono>
</propietario>
<libro>
<titulo>Cien años de soledad</titulo>
<autor>Gabriel García Márquez</autor>
<formato>Rústica</formato>
<publicacion>1967</publicacion>
<precio>23,5</precio>
</libro>
</libreria>