Subject	diagrama	bd	tabla_fisica	campo_fisico	campo_logico	pk	particion	definicion_campo_fisico	tipo_dato	parent_domain	
3. Cuenta	Cuenta Credito Personal		M_CUENTACREDITOPERSONAL	1	CODCLAVECTA	Codigo Clave Cuenta	Primary Key	No Definido		VARCHAR(128)	CodigoClaveSHA2512
3. Cuenta	Cuenta Credito Personal		M_CUENTACREDITOPERSONAL	10	TIPROLAGE	Tipo Rol Agencia	Non Primary Key	No Definido	Tipo de Rol relacionado al Rol Agencia	CHAR(20)	Tipo
3. Cuenta	Cuenta Credito Personal		M_CUENTACREDITOPERSONAL	11	CODAGE	Codigo Agencia	Non Primary Key	No Definido	"Código de actividad económica, CIIU (Clasificación Industrial Internacional Uniforme.) del cliente. Por ejemplo:

0092 : Personal Fuerzas Armadas  
0113 : Cultivos Frutas  
0121 : Cría de Ganados  
1542 : Elab. Azúcar  
Etc.
"	VARCHAR(30)	Codigo
