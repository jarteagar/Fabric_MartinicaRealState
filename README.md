--- FASE 1: encabezado (lecturas de lista blanca) ---
api: <class 'win32com.gen_py.A058AF1E-0735-424C-A623-47C3D2E6567Ax0x9x0.ISCApplication.ISCApplication'>
MartName: Mart
Version: 10.10.00.38109
miembros (24): ApiVersion, ApplicationEnvironment, ApplicationServices, ApplicationWindows, CLSID, ConnectMMart, DisconnectMMart, MartName, ModelDirectories, Name, PersistenceUnits, ResolveMartModelPath, Sessions, Version, coclass_clsid, set_LogFile, upgradeLibraryCatalogInfo, upgradeLibraryPermissions, upgradeMartPermissions, upgradeModelCatalogInfo, upgradeModelPermissions, upgradeNewProfiles, upgradePermissionsOnProfiles, upgradeUsers

--- FASE 2: propiedades del wrapper (sin llamadas COM) ---
propiedades: ApiVersion, ApplicationEnvironment, ApplicationServices, ApplicationWindows, MartName, ModelDirectories, Name, PersistenceUnits, Sessions, Version

--- FASE 3: sondeo de candidatos en api ---
---- sondeo de candidatos en api ----
ModelDirectories: existe (metodo)
ModelDirectory: no existe
LocateDirectory: no existe
LocateDirectoryNext: no existe
LocateDirectoryUnit: no existe
LocateDirectoryUnitNext: no existe
LocateModelUnit: no existe
LocateModelUnitNext: no existe
GetDirectory: no existe
GetDirectories: no existe
Subdirectories: no existe
Directories: no existe
DirectoryUnits: no existe
ModelUnits: no existe
Units: no existe
Models: no existe
Model: no existe
OpenModel: no existe

--- FASE 4: raices de ModelDirectories ---

-- raiz[0] Name='dataSchema'
   type=<class 'win32com.gen_py.A058AF1E-0735-424C-A623-47C3D2E6567Ax0x9x0.ISCModelDirectory.ISCModelDirectory'>
   miembros (23): CLSID, CopyDirectory, CopyDirectoryUnit, CreateDirectory, DeleteDirectory, DeleteDirectoryUnit, DirectoryExists, DirectoryUnitExists, Flags, GetPropertyBag, IsOfType, LocateDirectory, LocateDirectoryNext, LocateDirectoryUnit, LocateDirectoryUnitNext, Locator, MoveDirectory, MoveDirectoryUnit, Name, PropertyBag, SetPropertyBag, Type, coclass_clsid
   propiedades wrapper: Flags, Locator, Name, PropertyBag, Type
---- sondeo de candidatos en raiz[0] ----
ModelDirectories: no existe
ModelDirectory: no existe
LocateDirectory: existe (metodo)
  LocateDirectory(): com_error: (-2147352561, 'Parßmetro no opcional.', None, None)
  LocateDirectory('*',): ISCModelDirectory = <win32com.gen_py.erwin Data Modeler Script Client API Type Library.ISCModelDirectory instance at 0x1419093162080>
  LocateDirectory('',): NoneType = None
  LocateDirectory('*.*',): ISCModelDirectory = <win32com.gen_py.erwin Data Modeler Script Client API Type Library.ISCModelDirectory instance at 0x1419093162080>
LocateDirectoryNext: existe (metodo)
  LocateDirectoryNext(): ISCModelDirectory = <win32com.gen_py.erwin Data Modeler Script Client API Type Library.ISCModelDirectory instance at 0x1419093162176>
  LocateDirectoryNext('*',): TypeError: ISCModelDirectory.LocateDirectoryNext() takes 1 positional argument but 2 were given
  LocateDirectoryNext('',): TypeError: ISCModelDirectory.LocateDirectoryNext() takes 1 positional argument but 2 were given
  LocateDirectoryNext('*.*',): TypeError: ISCModelDirectory.LocateDirectoryNext() takes 1 positional argument but 2 were given
LocateDirectoryUnit: existe (metodo)
  LocateDirectoryUnit(): com_error: (-2147352561, 'Parßmetro no opcional.', None, None)
