Ejercicio 1 - Longitud fija de una clave

Define un elemento "clave" que pueda tomar por valor exactamente diez caracteres, los
cuales podrán ser letras mayúsculas o minúsculas de la "a" a la "z", o dígitos del "0" al "9".
Por ejemplo, serán válidos los valores siguientes: "abcde12345", "Clave55ABC",
"1A2b3c4D5f", etc.
Hazlo de dos formas distintas, una usando xs:pattern y xs:length y otra usando
únicamente xs:pattern.

Ejercicio 2 - Longitud mínima y máxima de una clave

Dado el siguiente documento XML:

<?xml version="1.0" encoding="UTF-8"?>
<fichas xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
xsi:noNamespaceSchemaLocation="fichas.xsd">
<ficha>
<nombre>Ana Sanz Tin</nombre>
<clave>G8w2</clave>
</ficha>
<ficha>
<nombre>Iker Rubio Mol</nombre>
<clave>ag32Ue7AFF</clave>
</ficha>
</fichas>

Escribe el contenido del archivo "fichas.xsd" que permita validarlo, teniendo en cuenta
que el elemento "clave" debe poder tomar por valor un mínimo de cuatro caracteres y un
máximo de diez. Dichos caracteres pueden ser indistintamente letras mayúsculas o
minúsculas de la "a" a la "z", o dígitos del "0" al "9". La restricción solamente podrá
aplicarse al elemento "clave".
Para ello, se debe utilizar xs:pattern y también:
• xs:minLength que permite especificar la longitud mínima.
• xs:maxLength que permite especificar la longitud máxima.

Ejercicio 3 - Precios de artículos

Dado el archivo "precios.xsd":

<?xml version="1.0" encoding="UTF-8"?>
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema">
<xs:element name="precios">
<xs:complexType>
<xs:sequence>
<xs:element name="precio" maxOccurs="unbounded">
<xs:complexType>
<xs:simpleContent>
<xs:extension base="xs:decimal">
<xs:attribute name="moneda" type="xs:string" />
</xs:extension>
</xs:simpleContent>
</xs:complexType>
</xs:element>
</xs:sequence>
</xs:complexType>
</xs:element>
</xs:schema>

Realizar los cambios necesarios en el archivo "precios.xsd" para que permita validar el
siguiente documento XML:

<?xml version="1.0" encoding="UTF-8"?>
<articulos xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
xsi:noNamespaceSchemaLocation="articulos.xsd">
<articulo>
<nombre>Mesa</nombre>
<precio moneda="Euro">50</precio>
</articulo>
<articulo>
<nombre>Silla</nombre>
<precio moneda="Dólar">78.99</precio>
</articulo>
</articulos>

El archivo "precios.xsd" tiene que renombrarse a "articulos.xsd".

Ejercicio 4 - Información de ubicaciones

Dado el archivo "ubicaciones.xsd":

<?xml version="1.0" encoding="UTF-8"?>
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema">
<xs:element name="ubicaciones">
<xs:complexType>
<xs:sequence>
<xs:element name="ubicacion" type="direccion"
maxOccurs="unbounded"/>
</xs:sequence>
</xs:complexType>
</xs:element>
<xs:simpleType name="direccion">
<xs:restriction base="xs:string">
<xs:enumeration value="norte"/>
<xs:enumeration value="sur"/>
<xs:enumeration value="este"/>
<xs:enumeration value="oeste"/>
</xs:restriction>
</xs:simpleType>
</xs:schema>

Añade al archivo "ubicaciones.xsd", la definición de un nuevo elemento complexType
llamado "infoUbicacion" que amplíe la definición de "direccion", permitiendo validar el
siguiente documento XML:

<?xml version="1.0" encoding="UTF-8"?>
<ubicaciones xmlns:xsi="http://www.w3.org/2001/XMLSchema-
instance"
xsi:noNamespaceSchemaLocation="ubicaciones.xsd">
<ubicacion metros="32">norte</ubicacion>
<ubicacion metros="25">este</ubicacion>
<ubicacion metros="64">este</ubicacion>
</ubicaciones>

Ejercicio 5 - Colores de muebles

Haciendo uso del siguiente código:

<xs:complexType name="tipoColorMueble">
<xs:simpleContent>
<xs:extension base="tipoMueble">
<xs:attribute name="color">
<xs:simpleType>
<xs:restriction base="xs:string">
<xs:enumeration value="blanco"/>
<xs:enumeration value="gris"/>
<xs:enumeration value="negro"/>
<xs:enumeration value="wengue"/>
</xs:restriction>
</xs:simpleType>
</xs:attribute>
</xs:extension>
</xs:simpleContent>
</xs:complexType>
<xs:simpleType name="tipoMueble">
<xs:restriction base="xs:string">
<xs:enumeration value="armario"/>
<xs:enumeration value="mesa"/>
<xs:enumeration value="silla"/>
</xs:restriction>
</xs:simpleType>

Escribir el contenido del archivo "muebles.xsd" que permita validar el siguiente
documento XML:

<?xml version="1.0" encoding="UTF-8"?>
<muebles xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
xsi:noNamespaceSchemaLocation="muebles.xsd">
<mueble color="blanco">mesa</mueble>
<mueble color="gris">silla</mueble>
</muebles>