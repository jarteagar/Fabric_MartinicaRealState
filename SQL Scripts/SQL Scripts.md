SCRIPTS de WAREHOUSE para la creacion de Roles

— Roles
CREATE ROLE [rol_usuarios];

CREATE ROLE [rol_analistas];

— Reglas de Enmascaramiento para proteger información de cara a los usuarios
— MASCARA DE MONTO DE INVERSION

ALTER TABLE MRS.campaigns

ALTER COLUMN BudgetUSD ADD MASKED WITH (FUNCTION = ‘default()’);

— MASCARA CONTACTO A LOS CLIENTES

ALTER TABLE MRS.clients

ALTER COLUMN Email ADD MASKED WITH (FUNCTION = ‘default()’);

— MASCARA CONTACTO A LOS BROKERS

ALTER TABLE MRS.brokers

ALTER COLUMN Email ADD MASKED WITH (FUNCTION = ‘default()’);

— Niveles de Acceso a Usuarios
GRANT SELECT ON SCHEMA::MRS TO rol_usuarios;

— Niveles de Acceso a los Analistas
GRANT SELECT ON SCHEMA::MRS TO rol_analistas;

GRANT SELECT, INSERT, UPDATE, DELETE ON SCHEMA::MRS TO rol_analistas;

GRANT UNMASK TO rol_analistas;
