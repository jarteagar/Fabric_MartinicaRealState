$ python -m erwin_mart datos --ruta "Modelo UDV/Modelo Logico" --sondeo --max-objetos 500
INFO erwin_mart.session: conectado al MART Mart
binding: estatico (gen_py)
INFO erwin_mart.session: Mart agregado a ModelDirectories: mart://Mart
modelo: UDV Modelo de Datos Logico V0.640
locator: mart://Mart/Modelo UDV/Modelo Logico/UDV Modelo de Datos Logico V0.640?<params>
  PersistenceUnits.Add(mart://Mart/Modelo UDV/Modelo Logico/UDV Modelo de Datos Logico V0.640?<params>) -> OK
disposicion: Read_Only = Yes;
model_type: 3
sesion abierta
  ... 200 objetos (Key_Group)
  ... 400 objetos (Key_Group_Member)
corte por --max-objetos (500)
sondeo: 500 objetos
clases:
  Attribute: 216
  Entity: 28
  Key_Group: 115
  Key_Group_Member: 141
propiedades por clase:
  Attribute: Attribute.Logical.Atributo Cross(216), Attribute.Logical.Clasificacion del Dato(216), Attribute.Logical.Clave Secundaria(216), Attribute.Logical.Udp(216), Attribute.Physical.Campo Cross(216), Attribute.Physical.Clasificacion del Dato(216), Attribute.Physical.Exclusivo Cloud(216), Attribute.Physical.Particion(216), Attribute_Order(216), Column_Order(214), Comment(216), Definition(198), Dependent_Objects_Ref(216), Do_Not_Generate(216), Font_Color(21), Font_Moniker(35), Font_Size(16), Hide_In_Logical(216), Hide_In_Physical(216), History_List(216), Image_Ref(216), Is_Color_Inherited(23), Is_Font_Bold(23), Is_Font_Inherited(4), Is_Logical_Only(2), Is_Physical_Only(2), Logical_Data_Type(216), Long_Id(216), Master_Attribute_Ref(216), Name(216), Null_Option_Type(216), Owner_Path(216), Parent_Attribute_Ref(96), Parent_Domain_Ref(216), Parent_Relationship_Ref(96), Physical_Data_Type(216), Physical_Name(216), Physical_Order(214), Type(216), User_Formatted_Name(216), User_Formatted_Physical_Name(216)
  Entity: Attributes_Order_Ref(28), Child_Relationships_Ref(17), Columns_Order_Ref(27), Comment(28), Definition(28), Dependent_Objects_Ref(28), Do_Not_Generate(28), Entity.Logical.Clasificacion del Dato(28), Entity.Logical.Dominio Principal(28), Entity.Logical.Filtro Despliegue 2021(28), Entity.Logical.Tipo de Entidad(28), Entity.Logical.Tipo de Vista(28), Entity.Logical.Universal(28), Entity.Physical.Clasificacion del Dato(28), Entity.Physical.Estado Cloud(28), Entity.Physical.Frecuencia Vacuum(28), Entity.Physical.Frecuencia Vacuum_1(28), Entity.Physical.Tabla Cross(28), Entity.Physical.Tipo de Carga(28), Entity.Physical.Tipo de Entidad(28), Entity.Physical.Universal(28), History_List(28), Icon_Image_Ref(28), Image_Ref(28), Is_Logical_Only(1), Is_Physical_Only(1), Long_Id(28), Name(28), Owner_Path(28), Parent_Relationships_Ref(21), Physical_Columns_Order_Ref(27), Physical_Name(28), Shapes_Ref(28), Theme_Ref(6), Type(28), User_Formatted_Name(28), User_Formatted_Physical_Name(28)
  Key_Group: Dependent_Objects_Ref(115), Do_Not_Generate(115), Index_Members_Order_Ref(113), Is_Logical_Only(2), Is_Physical_Only(2), Is_Unique(115), Key_Group.Physical.BYTES POR SEGMENTO(115), Key_Group.Physical.CAMBIO(115), Key_Group.Physical.CAMBIO_1(115), Key_Group.Physical.NOMBRE DE INDICE(115), Key_Group.Physical.TOTAL DE ESPACIO DEL INDICE (MB)(115), Key_Group_Members_Order_Ref(115), Key_Group_Type(115), Long_Id(115), Name(115), Owner_Path(115), Physical_Name(115), Relationship_Ref(87), User_Formatted_Name(115), User_Formatted_Physical_Name(115)
  Key_Group_Member: Attribute_Ref(141), Dependent_Objects_Ref(141), Hide_In_Logical(141), Hide_In_Physical(141), Index_Member_Order(137), Is_Logical_Only(4), Is_Physical_Only(4), Key_Group_Member_Order(141), Long_Id(141), Name(141), Owner_Path(141), Parent_Key_Group_Member_Ref(94), Physical_Name(141), User_Formatted_Name(141), User_Formatted_Physical_Name(141)
vocabulario:
  Attribute.Attribute.Logical.Clasificacion del Dato: ' No DAC'x211, 'No DAC'x4, 'No Sensible'x1
  Attribute.Attribute.Logical.Clave Secundaria: 'NO'x216
  Attribute.Logical_Data_Type: 'CHAR(1)'x10, 'CHAR(20)'x70, 'DATE'x25, 'DECIMAL (19,8)'x7, 'DECIMAL (22,4)'x1, 'INTEGER'x6, 'VARCHAR(120)'x11, 'VARCHAR(128)'x18, 'VARCHAR(20)'x1, 'VARCHAR(256)'x21, 'VARCHAR(30)'x39, 'VARCHAR(64)'x7
  Attribute.Null_Option_Type: '0'x151, '1'x65
  Attribute.Physical_Data_Type: 'CHAR(1)'x10, 'CHAR(20)'x70, 'DATE'x5, 'DECIMAL(19,8)'x7, 'DECIMAL(22,4)'x1, 'INT'x6, 'TIMESTAMP'x20, 'VARCHAR(120)'x11, 'VARCHAR(128)'x18, 'VARCHAR(256)'x21, 'VARCHAR(30)'x40, 'VARCHAR(64)'x7
Key_Group.Type x Relationship_Ref:
  'IF1' con relationship: 14
  'IF10' con relationship: 3
  'IF11' con relationship: 1
  'IF12' con relationship: 3
  'IF13' con relationship: 4
  'IF14' con relationship: 4
  'IF15' con relationship: 4
  'IF16' con relationship: 4
  'IF17' con relationship: 4
  'IF18' con relationship: 2
  'IF19' con relationship: 2
  'IF2' con relationship: 10
  'IF21' con relationship: 1
  'IF22' con relationship: 1
  'IF23' con relationship: 1
  'IF3' con relationship: 7
  'IF4' con relationship: 4
  'IF5' con relationship: 4
  'IF6' con relationship: 4
  'IF7' con relationship: 3
  'IF8' con relationship: 3
  'IF9' con relationship: 4
  'PK' sin relationship: 28
sondeo completo (no se escribio artefacto)
INFO erwin_mart.session: desconectado del MART
