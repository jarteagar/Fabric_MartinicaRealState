$ python -m erwin_mart metadata --ruta "Modelo UDV/Modelo Fisico" --max-objetos 500 --salida salidas
INFO erwin_mart.session: conectado al MART Mart
binding: estatico (gen_py)
INFO erwin_mart.session: Mart agregado a ModelDirectories: mart://Mart
modelo: UDV Modelo de Datos Fisico V0.1094
locator: mart://Mart/Modelo UDV/Modelo Fisico/UDV Modelo de Datos Fisico V0.1094?<params>
  PersistenceUnits.Add(mart://Mart/Modelo UDV/Modelo Fisico/UDV Modelo de Datos Fisico V0.1094?<params>) -> OK
disposicion: Read_Only = Yes;
model_type: 3
sesion abierta
objetos en el modelo: 160075
  ... 200 objetos (Attribute)
  ... 400 objetos (Attribute)
corte por --max-objetos (500)
escritos: 500 objetos -> salidas\UDV_Modelo_de_Datos_Fisico_V0.1094.jsonl
inventario -> salidas\UDV_Modelo_de_Datos_Fisico_V0.1094_inventario.json
duracion: 42.2s
INFO erwin_mart.session: desconectado del MART
