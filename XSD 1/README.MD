Ejercicio 1.

Dado el siguiente documento XML:

<?xml version="1.0" encoding="UTF-8"?>
<fichas xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
xsi:noNamespaceSchemaLocation="fichas.xsd">
<ficha numero="1">
<nombre>Ana Sanz Tin</nombre>
<edad>22</edad>
</ficha>
<ficha numero="2">
<nombre>Iker Rubio Mol</nombre>
<edad>23</edad>
</ficha>
</fichas>

Escribe el contenido del archivo "fichas.xsd" que permita validarlo.

Ejercicio 2.
Dado el siguiente documento XML:

<?xml version="1.0" encoding="UTF-8"?>
<fichas xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
xsi:noNamespaceSchemaLocation="fichas.xsd">
<ficha numero="1">
<nombre>Ana Sanz Tin</nombre>
<edad>22</edad>
</ficha>
<ficha numero="2">
<nombre>Iker Rubio Mol</nombre>
<edad>23</edad>
</ficha>
</fichas>

Escribe el contenido del archivo "fichas.xsd" que permita validarlo, teniendo en cuenta
que se debe definir la "edad" con la restricción de que el valor que tome no pueda ser
menor que 0 ni mayor que 130.
Además, en vez de xs:minInclusive y xs:maxInclusive, se debe utilizar:
• xs:minExclusive que sirve para especificar que el valor debe ser mayor que el
indicado.
• xs:maxExclusive que sirve para especificar que el valor debe ser menor que el
indicado.

Ejercicio 3.

Dado el siguiente documento XML:

<?xml version="1.0" encoding="UTF-8"?>
<precios xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
xsi:noNamespaceSchemaLocation="precios.xsd">
<precio>8</precio>
<precio>2.6</precio>
<precio>4.95</precio>
<precio>187</precio>
</precios>

Escribe el contenido del archivo "precios.xsd" que permita validarlo, teniendo en cuenta
que el elemento "precio" puede tomar por valor un número que contenga tres dígitos
como máximo y, de ellos, solamente dos pueden ser decimales. Para ello, escribir una
restricción que no podrá ser utilizada por otros elementos y, por otra parte, haga uso de:
• xs:totalDigits que sirve para especificar el número máximo de dígitos que puede
tener un número, incluyendo a los decimales.
• xs:fractionDigits que sirve para especificar el número máximo de decimales que
puede tener un número.

Ejercicio 4.

Dada la siguiente definición:

<xs:element name="vehiculo">
<xs:simpleType>
<xs:restriction base="xs:string">
<xs:enumeration value="barco"/>
<xs:enumeration value="bicicleta"/>
<xs:enumeration value="coche"/>
<xs:enumeration value="tren"/>
</xs:restriction>
</xs:simpleType>
</xs:element>

¿De qué otro modo se puede definir el elemento "vehículo" y un xs:simleType llamado
tipoDeVehiculo que restringiese a "barco", "bicicleta", "coche" y "tren" como los únicos
valores aceptables para el vehículo, de forma que dicho tipo pudiera ser también
utilizado por otros elementos?

Ejercicio 5.
Dado el archivo "fichas.xsd" cuyo contenido es:

<?xml version="1.0" encoding="UTF-8"?>
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema">
<xs:element name="fichas">
<xs:complexType>
<xs:sequence>
<xs:element name="ficha" maxOccurs="unbounded">
<xs:complexType>
<xs:sequence>
<xs:element name="nombre" type="xs:string"/>
<xs:element name="iniciales">
<xs:simpleType>
<xs:restriction base="xs:string">
<xs:pattern value="[A-Z][A-Z][A-Z]"/>
</xs:restriction>
</xs:simpleType>
</xs:element>
<xs:element name="edad" type="xs:integer"/>
</xs:sequence>
</xs:complexType>
</xs:element>
</xs:sequence>
</xs:complexType>
</xs:element>
</xs:schema>
Corregir los errores cometidos en el siguiente documento XML, para que sea válido:
<?xml version="1.0" encoding="UTF-8"?>
<fichas xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
xsi:noNamespaceSchemaLocation="fichas.xsd">
<ficha>
<nombre>Antonio Machado Ruiz</nombre>
<iniciales>AMR</iniciales>
<edad>22</edad>
</ficha>
<ficha>
<nombre>Mario Moreno</nombre>
<iniciales>MM</iniciales>
<edad>23</edad>
</ficha>
<ficha>
<iniciales>ALO</iniciales>
<nombre>Ada Lovelace</nombre>
<edad>24</edad>
</ficha>
<ficha>
<nombre>pablo ruiz picasso</nombre>
<iniciales>prp</iniciales>
<edad>24</edad>
</ficha>
</fichas>

Ejercicio 6.

Dado el archivo "fichas.xsd":

<?xml version="1.0" encoding="UTF-8"?>
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema">
<xs:element name="fichas">
<xs:complexType>
<xs:sequence>
<xs:element name="ficha" maxOccurs="unbounded">
<xs:complexType>
<xs:sequence>
<xs:element name="nombre" type="xs:string"/>
<xs:element name="iniciales">
<xs:simpleType>
<xs:restriction base="xs:string">
<xs:pattern value="[A-Z][A-Z][A-Z]"/>
</xs:restriction>
</xs:simpleType>
</xs:element>
<xs:element name="edad" type="xs:integer"/>
</xs:sequence>
</xs:complexType>
</xs:element>
</xs:sequence>
</xs:complexType>
</xs:element>
</xs:schema>

Realizar los cambios necesarios en "fichas.xsd", para que el siguiente documento XML
sea válido:

<?xml version="1.0" encoding="UTF-8"?>
<fichas xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
xsi:noNamespaceSchemaLocation="fichas.xsd">
<ficha>
<nombre>Ana Sanz Tin</nombre>
<iniciales>AST</iniciales>
<edad>22</edad>
<iniciales-al-reves>TSA</iniciales-al-reves>
</ficha>
<ficha>
<nombre>Iker Rubio Mol</nombre>
<iniciales>IRM</iniciales>
<edad>23</edad>
<iniciales-al-reves>MRI</iniciales-al-reves>
</ficha>
</fichas>

Nota: hay que tener en cuenta que el elemento iniciales-al-reves debe ser del mismo tipo
que iniciales, y dicho tipo solamente deberá definirse una vez.
Si se quisiera permitir que las tres letras de iniciales e iniciales-al-reves, sean
minúsculas o mayúsculas indistintamente; en lugar de [A-Z][A-Z][A-Z] ¿qué se podría
escribir?