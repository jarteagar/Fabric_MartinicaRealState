$ python -m erwin_mart metadata --ruta "Modelo UDV/Modelo Logico" --max-objetos 500 --salida salidas
INFO erwin_mart.session: conectado al MART Mart
binding: estatico (gen_py)
INFO erwin_mart.session: Mart agregado a ModelDirectories: mart://Mart
modelo: UDV Modelo de Datos Logico V0.640
locator: mart://Mart/Modelo UDV/Modelo Logico/UDV Modelo de Datos Logico V0.640?<params>
  PersistenceUnits.Add(mart://Mart/Modelo UDV/Modelo Logico/UDV Modelo de Datos Logico V0.640?<params>) -> OK
disposicion: Read_Only = Yes;
model_type: 3
sesion abierta
objetos en el modelo: 58049
  ... 200 objetos (Key_Group)
  ... 400 objetos (Key_Group_Member)
corte por --max-objetos (500)
escritos: 500 objetos -> salidas\UDV_Modelo_de_Datos_Logico_V0.640.jsonl
inventario -> salidas\UDV_Modelo_de_Datos_Logico_V0.640_inventario.json
duracion: 12.9s
INFO erwin_mart.session: desconectado del MART
