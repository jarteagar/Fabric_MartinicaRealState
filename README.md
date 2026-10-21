$ python -m erwin_mart probar-apertura --ruta "Modelo UDV/Modelo Fisico" --salida fisico.txt
INFO erwin_mart.session: conectado al MART Mart
binding: estatico (gen_py)
INFO erwin_mart.session: Mart agregado a ModelDirectories: mart://Mart
--- PROBAR-APERTURA: sondeo de apertura de modelo ---
ruta: Modelo UDV/Modelo Fisico

PASO 1: localizar carpeta y elegir unidad
carpeta: Modelo Fisico
hijos disponibles: ['Ant']
  unidad disponible: UDV Modelo de Datos Fisico V0.1094
unidad elegida: UDV Modelo de Datos Fisico V0.1094
  [paso 508679 ms]

PASO 2: propiedades de la unidad del Mart
  >> unidad.Locator
  << str = 'mart://Mart/Modelo UDV/Modelo Fisico/UDV Modelo de Datos Fisico V0.1094?<params>'
  >> unidad.Type
  << int = 2
  >> unidad.PropertyBag("Disposition")
  << str = "<error com_error: (-2147352567, 'Ocurrió una excepción.', (0, 'erwin9.SCAPI.PropertyBag.9.0', 'Property Bag Component ! Property argument is out of range.',...
  >> unidad.PropertyBag("Model_Type")
  << str = "<error com_error: (-2147352567, 'Ocurrió una excepción.', (0, 'erwin9.SCAPI.PropertyBag.9.0', 'Property Bag Component ! Property argument is out of range.',...
  [paso 11 ms]
locator: mart://Mart/Modelo UDV/Modelo Fisico/UDV Modelo de Datos Fisico V0.1094?<params>

PASO 3: PersistenceUnits.Add
  PersistenceUnits.Add(mart://Mart/Modelo UDV/Modelo Fisico/UDV Modelo de Datos Fisico V0.1094?<params>) -> OK
  [paso 55233 ms]

PASO 4: PropertyBag de la persistence unit
  >> pu.PropertyBag("Locator")
  << str = 'erwin://Mart://Mart/Modelo UDV/Modelo Fisico/UDV Modelo de Datos Fisico V0.1094?<params>'
  >> pu.PropertyBag("Disposition")
  << str = 'Read_Only = Yes;'
  >> pu.PropertyBag("Model_Type")
  << int = 3
  [paso 6 ms]

PASO 5: Sessions.Add + Open
  >> api.Sessions.Add
  << ISCSession = <win32com.gen_py.erwin Data Modeler Script Client API Type Library.ISCSession instance at 0x2558301060464>
  >> sesion.Open(pu)
  << bool = True
  [paso 31 ms]

PASO 6: ModelObjects (inventario de clases)
  >> ModelObjects.Count
  << int = 160075
objetos totales: 160075
  Attribute: 311
  Entity: 11
  Key_Group: 79
  Key_Group_Member: 99
  (inventario limitado a 500 de 160075)
  [paso 162 ms]

PASO 7: muestra de propiedades
  [Entity] 'Organizacion':
    Definition = 'Persona Jurídica es una entidad confirmada por una, dos o más personas que e...
    Name = 'Organizacion'
    Long_Id = '{9AE448F2-F651-44EC-925C-6D88D557A3A3}+00000000'
    Owner_Path = 'Modelo de Datos UDV_FISICO'
    Type = 'Dependent'
    Comment = 'Persona Jurídica es una entidad confirmada por una, dos o más personas que e...
    Physical_Name = 'M_ORGANIZACION'
    Child_Relationships_Ref = 'R/371;R/393;R/394;R/395;R/396;R/397;R/398;R/399;R/417;R/418;R/424;R/425;R/28...
    Dependent_Objects_Ref = '1. Party;R/371;R/393;R/394;R/395;R/396;R/397;R/398;R/399;R/417;R/418;Organiz...
    Do_Not_Generate = 'false'
    Parent_Relationships_Ref = 'R/1667;R/2115;R/2900;R/6080;R/6504;'
    Attributes_Order_Ref = 'Codigo Clave Party;Tipo Clasificacion Interna Organizacion;Descripcion Tipo ...
    Physical_Columns_Order_Ref = 'Codigo Clave Party;Tipo Clasificacion Interna Organizacion;Descripcion Tipo ...
    Columns_Order_Ref = 'Codigo Clave Party;Tipo Clasificacion Interna Organizacion;Descripcion Tipo ...
    User_Formatted_Name = 'Organizacion'
    User_Formatted_Physical_Name = 'M_ORGANIZACION'
    Shapes_Ref = 'Organizacion;Organizacion;Organizacion;'
    Image_Ref = 'Default Entity Small Icon'
    Icon_Image_Ref = 'Default Entity Icon'
    History_List = '<null>Event="2" Description=" (Modelo de Datos UDV)" SourcePath="" Comment="...
    Entity.Logical.Clasificacion del Dato = 'No Definido'
    Entity.Logical.Tipo de Entidad = 'Sub-Tipo'
    Entity.Logical.Dominio Principal = ''
    Entity.Physical.Clasificacion del Dato = 'No Definido'
    Entity.Physical.Tipo de Entidad = 'No Definido'
    Entity.Physical.Dominio Principal = 'Cliente'
    Entity.Physical.Tipo de Carga = ' Tipo 1 (No Historia)'
    Entity.Physical.Universal = 'No Definido'
    Entity.Logical.Universal = 'No Definido'
    Entity.Physical.Tabla Cross = 'No Definido'
    ... (30+ propiedades)
  [Attribute] 'Fecha Constitucion':
    Definition = 'Fecha de constitución de la empresa.'
    Name = 'Fecha Constitucion'
    Long_Id = '{307A26E1-4DC1-4444-8A61-A2B8ECB3B844}+00000000'
    Owner_Path = 'Modelo de Datos UDV_FISICO.Organizacion'
    Type = 'NonKey'
    Physical_Data_Type = 'DATE'
    Null_Option_Type = 'Null'
    Physical_Order = '24'
    Comment = 'Fecha de constitución de la empresa.'
    Physical_Name = 'FECCONSTITUCION'
    Logical_Data_Type = 'DATE'
    Parent_Domain_Ref = 'Fecha'
    Hide_In_Logical = 'false'
    Hide_In_Physical = 'false'
    Master_Attribute_Ref = 'Fecha Constitucion'
    Font_Size = '14'
    Attribute_Order = '24'
    Column_Order = '24'
    Dependent_Objects_Ref = 'Organizacion;FECCONSTITUCION;'
    Do_Not_Generate = 'false'
    User_Formatted_Name = 'Fecha Constitucion'
    User_Formatted_Physical_Name = 'FECCONSTITUCION'
    Font_Moniker = '14'
    Image_Ref = 'Default <unknown> Icon'
    History_List = '<null>Event="2" Description=" (Modelo de Datos UDV)" SourcePath="" Comment="...
    Attribute.Logical.Clasificacion del Dato = ' No DAC'
    Attribute.Physical.Clasificacion del Dato = ' No DAC'
    Attribute.Physical.Campo Cross = ' No'
    Attribute.Logical.Atributo Cross = ' No'
    Attribute.Physical.Particion = 'No Definido'
    ... (30+ propiedades)
  [Attribute] 'Flag Matriz Exterior':
    Definition = 'Indicador de tenencia de casa de matriz en el exterior.'
    Name = 'Flag Matriz Exterior'
    Long_Id = '{F9631142-D68D-4EFD-8CBE-5ACD81F47A28}+00000000'
    Owner_Path = 'Modelo de Datos UDV_FISICO.Organizacion'
    Type = 'NonKey'
    Physical_Data_Type = 'CHAR(1)'
    Null_Option_Type = 'Null'
    Physical_Order = '25'
    Comment = 'Indicador de tenencia de casa de matriz en el exterior.'
    Physical_Name = 'FLGMATRIZEXTERIOR'
    Logical_Data_Type = 'CHAR(1)'
    Parent_Domain_Ref = 'Flag'
    Hide_In_Logical = 'false'
    Hide_In_Physical = 'false'
    Master_Attribute_Ref = 'Flag Matriz Exterior'
    Font_Size = '14'
    Attribute_Order = '25'
    Column_Order = '25'
    Dependent_Objects_Ref = 'Organizacion;FLGMATRIZEXTERIOR;'
    Do_Not_Generate = 'false'
    User_Formatted_Name = 'Flag Matriz Exterior'
    User_Formatted_Physical_Name = 'FLGMATRIZEXTERIOR'
    Font_Moniker = '14'
    Image_Ref = 'Default <unknown> Icon'
    History_List = '<null>Event="2" Description=" (Modelo de Datos UDV)" SourcePath="" Comment="...
    Attribute.Logical.Clasificacion del Dato = ' No DAC'
    Attribute.Physical.Clasificacion del Dato = ' No DAC'
    Attribute.Physical.Campo Cross = ' No'
    Attribute.Logical.Atributo Cross = ' No'
    Attribute.Physical.Particion = 'No Definido'
    ... (30+ propiedades)
  [paso 483 ms]

CIERRE: sesion.Close + Remove (no dejar sesiones en el Mart)

PROBAR-APERTURA: COMPLETO SIN CRASH
INFO erwin_mart.session: desconectado del MART
