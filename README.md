$ python -m erwin_mart probar-apertura --ruta "Modelo UDV/Modelo Logico" --salida logico.txt
INFO erwin_mart.session: conectado al MART Mart
binding: estatico (gen_py)
INFO erwin_mart.session: Mart agregado a ModelDirectories: mart://Mart
--- PROBAR-APERTURA: sondeo de apertura de modelo ---
ruta: Modelo UDV/Modelo Logico

PASO 1: localizar carpeta y elegir unidad
carpeta: Modelo Logico
hijos disponibles: ['Ant']
  unidad disponible: UDV Modelo de Datos Logico V0.640
unidad elegida: UDV Modelo de Datos Logico V0.640
  [paso 496722 ms]

PASO 2: propiedades de la unidad del Mart
  >> unidad.Locator
  << str = 'mart://Mart/Modelo UDV/Modelo Logico/UDV Modelo de Datos Logico V0.640?<params>'
  >> unidad.Type
  << int = 2
  >> unidad.PropertyBag("Disposition")
  << str = "<error com_error: (-2147352567, 'Ocurrió una excepción.', (0, 'erwin9.SCAPI.PropertyBag.9.0', 'Property Bag Component ! Property argument is out of range.',...
  >> unidad.PropertyBag("Model_Type")
  << str = "<error com_error: (-2147352567, 'Ocurrió una excepción.', (0, 'erwin9.SCAPI.PropertyBag.9.0', 'Property Bag Component ! Property argument is out of range.',...
  [paso 13 ms]
locator: mart://Mart/Modelo UDV/Modelo Logico/UDV Modelo de Datos Logico V0.640?<params>

PASO 3: PersistenceUnits.Add
  PersistenceUnits.Add(mart://Mart/Modelo UDV/Modelo Logico/UDV Modelo de Datos Logico V0.640?<params>) -> OK
  [paso 19294 ms]

PASO 4: PropertyBag de la persistence unit
  >> pu.PropertyBag("Locator")
  << str = 'erwin://Mart://Mart/Modelo UDV/Modelo Logico/UDV Modelo de Datos Logico V0.640?<params>'
  >> pu.PropertyBag("Disposition")
  << str = 'Read_Only = Yes;'
  >> pu.PropertyBag("Model_Type")
  << int = 3
  [paso 6 ms]

PASO 5: Sessions.Add + Open
  >> api.Sessions.Add
  << ISCSession = <win32com.gen_py.erwin Data Modeler Script Client API Type Library.ISCSession instance at 0x1690352832624>
  >> sesion.Open(pu)
  << bool = True
  [paso 9 ms]

PASO 6: ModelObjects (inventario de clases)
  >> ModelObjects.Count
  << int = 58049
objetos totales: 58049
  Attribute: 216
  Entity: 28
  Key_Group: 115
  Key_Group_Member: 141
  (inventario limitado a 500 de 58049)
  [paso 95 ms]

PASO 7: muestra de propiedades
  [Entity] 'Party':
    Definition = 'Define a un Individuo/Persona Natural u Organización/Persona Jurídica. Cualq...
    Name = 'Party'
    Long_Id = '{79E1CA34-F847-41AE-B329-92E3CD4BAB8B}+00000000'
    Owner_Path = 'Modelo de Datos UDV'
    Type = 'Independent'
    Comment = 'Define a un Individuo/Persona Natural u Organización/Persona Jurídica. Cualq...
    Physical_Name = 'PARTY'
    Theme_Ref = 'Entidad Secundaria'
    Child_Relationships_Ref = 'R/300;'
    Dependent_Objects_Ref = '3. Cuenta;1. Party;Party;R/93;R/100;R/110;R/118;R/127;R/129;Party;R/300;R/36...
    Do_Not_Generate = 'false'
    Parent_Relationships_Ref = 'R/93;R/100;R/110;R/118;R/127;R/129;R/365;R/2140;R/2165;R/2169;R/2179;R/2343;'
    Attributes_Order_Ref = 'Codigo Clave Party;Tipo Clasificacion Interna Party;Tipo Party Identificacio...
    Physical_Columns_Order_Ref = 'Codigo Clave Party;Tipo Clasificacion Interna Party;Tipo Party Identificacio...
    Columns_Order_Ref = 'Codigo Clave Party;Tipo Clasificacion Interna Party;Tipo Party Identificacio...
    User_Formatted_Name = 'Party'
    User_Formatted_Physical_Name = 'PARTY'
    Shapes_Ref = 'Party;Party;Party;Party;Party;Party;Party;Party;Party;Party;Party;Party;'
    Image_Ref = 'Default Entity Small Icon'
    Icon_Image_Ref = 'Default Entity Icon'
    History_List = '<null>Event="2" Description=" (Modelo de Datos UDV)" SourcePath="" Comment="...
    Entity.Logical.Clasificacion del Dato = 'No Definido'
    Entity.Logical.Tipo de Entidad = 'No Definido'
    Entity.Logical.Dominio Principal = 'Clientes'
    Entity.Logical.Universal = 'No Definido'
    Entity.Physical.Clasificacion del Dato = 'No Definido'
    Entity.Physical.Tipo de Carga = 'No Definido'
    Entity.Physical.Tipo de Entidad = 'No Definido'
    Entity.Physical.Universal = 'No Definido'
    Entity.Physical.Tabla Cross = 'No Definido'
    ... (30+ propiedades)
  [Attribute] 'Codigo Clave Party':
    Definition = 'Llave surrogada para mantener Party Unico (Individuo y Organizacion)'
    Name = 'Codigo Clave Party'
    Long_Id = '{F2E6A7EC-CEEC-4F31-A4B4-37CD0D1E098E}+00000000'
    Owner_Path = 'Modelo de Datos UDV.Party'
    Type = 'Key'
    Physical_Data_Type = 'VARCHAR(128)'
    Null_Option_Type = 'NotNull'
    Physical_Order = '1'
    Comment = 'Llave surrogada para mantener Party Unico (Individuo y Organizacion)'
    Physical_Name = 'CODCLAVEPARTY'
    Logical_Data_Type = 'VARCHAR(128)'
    Parent_Domain_Ref = 'Codigo Clave SHA2 512'
    Hide_In_Logical = 'false'
    Hide_In_Physical = 'false'
    Master_Attribute_Ref = 'Codigo Clave Party'
    Attribute_Order = '1'
    Column_Order = '1'
    Dependent_Objects_Ref = 'Party;Codigo Clave Party;Codigo Clave Party;Codigo Clave Party;Codigo Clave ...
    Do_Not_Generate = 'false'
    User_Formatted_Name = 'Codigo Clave Party'
    User_Formatted_Physical_Name = 'CODCLAVEPARTY'
    Image_Ref = 'Default <unknown> Icon'
    History_List = '<null>Event="2" Description=" (Modelo de Datos UDV)" SourcePath="" Comment="...
    Attribute.Logical.Clasificacion del Dato = ' No DAC'
    Attribute.Logical.Atributo Cross = ' No'
    Attribute.Physical.Campo Cross = ' No'
    Attribute.Physical.Clasificacion del Dato = ' No DAC'
    Attribute.Physical.Particion = 'No Definido'
    Attribute.Physical.Exclusivo Cloud = 'No Definido'
    Attribute.Logical.Clave Secundaria = 'NO'
    ... (30+ propiedades)
  [Attribute] 'Tipo Clasificacion Interna Party':
    Definition = 'Código del Tipo de Persona.'
    Name = 'Tipo Clasificacion Interna Party'
    Long_Id = '{F069853D-A984-4AF9-8FC0-9FDFC6E84BC6}+00000000'
    Owner_Path = 'Modelo de Datos UDV.Party'
    Type = 'NonKey'
    Physical_Data_Type = 'CHAR(20)'
    Null_Option_Type = 'NotNull'
    Physical_Order = '2'
    Parent_Attribute_Ref = 'Tipo Clasificacion Interna Party'
    Parent_Relationship_Ref = 'R/300'
    Comment = 'Código del Tipo de Persona.'
    Physical_Name = 'TIPCLASIFINTERNAPARTY'
    Logical_Data_Type = 'CHAR(20)'
    Parent_Domain_Ref = 'Tipo'
    Hide_In_Logical = 'false'
    Hide_In_Physical = 'false'
    Master_Attribute_Ref = 'Tipo Clasificacion Interna Party'
    Attribute_Order = '2'
    Column_Order = '2'
    Dependent_Objects_Ref = 'Party;Tipo Clasificacion Interna Party;'
    Do_Not_Generate = 'false'
    User_Formatted_Name = 'Tipo Clasificacion Interna Party'
    User_Formatted_Physical_Name = 'TIPCLASIFINTERNAPARTY'
    Image_Ref = 'Default <unknown> Icon'
    History_List = '<null>Event="6" Description="Tipo Persona." SourcePath="" Comment="" CreateT...
    Attribute.Logical.Clasificacion del Dato = ' No DAC'
    Attribute.Logical.Atributo Cross = ' No'
    Attribute.Physical.Campo Cross = ' No'
    Attribute.Physical.Clasificacion del Dato = ' No DAC'
    Attribute.Physical.Particion = 'No Definido'
    ... (30+ propiedades)
  [paso 338 ms]

CIERRE: sesion.Close + Remove (no dejar sesiones en el Mart)

PROBAR-APERTURA: COMPLETO SIN CRASH
INFO erwin_mart.session: desconectado del MART
