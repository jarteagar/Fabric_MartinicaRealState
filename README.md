Get-ChildItem salidas\*.jsonl | Select-Object Name, @{n='MB';e={[math]::Round($_.Length/1MB,1)}}
Y opcionalmente la primera línea del Entity para confirmar que las listas quedaron deduplicadas:
Get-Content salidas\UDV_Modelo_de_Datos_Fisico_V0.1094.jsonl -TotalCount 1
