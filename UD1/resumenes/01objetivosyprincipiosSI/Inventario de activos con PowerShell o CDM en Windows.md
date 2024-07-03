# Inventario de activos con PowerShell o CDM en Windows

Tanto PowerShell como CMD proporcionan comandos útiles para realizar un inventario de activos en Windows. PowerShell es más flexible y potente, permitiendo exportar fácilmente la información a diferentes formatos y realizar tareas más complejas. CMD es más sencillo y rápido para obtener información básica. Utiliza la herramienta que mejor se adapte a tus necesidades y al entorno en el que estés trabajando.

### Inventario de Activos con PowerShell

PowerShell es una herramienta poderosa para la administración de sistemas Windows. Puedes usar cmdlets específicos para recolectar información sobre el hardware y software instalado.

#### Listar Paquetes de Software Instalados

Puedes utilizar el cmdlet `Get-WmiObject` o `Get-CimInstance` para obtener una lista de los paquetes de software instalados.

```powershell
Get-WmiObject -Class Win32_Product | Select-Object -Property Name, Version, Vendor
```

O, usando `Get-CimInstance`:

```powershell
Get-CimInstance -ClassName Win32_Product | Select-Object -Property Name, Version, Vendor
```

#### Listar Información del Hardware

Para obtener información sobre el hardware, puedes usar varios cmdlets de PowerShell. Aquí hay algunos ejemplos:

- **Procesador**:

```powershell
Get-WmiObject -Class Win32_Processor | Select-Object -Property Name, Manufacturer, NumberOfCores, NumberOfLogicalProcessors
```

- **Memoria RAM**:

```powershell
Get-WmiObject -Class Win32_PhysicalMemory | Select-Object -Property Manufacturer, Capacity, Speed
```

- **Disco Duro**:

```powershell
Get-WmiObject -Class Win32_DiskDrive | Select-Object -Property Model, Manufacturer, Size
```

- **Placa Base**:

```powershell
Get-WmiObject -Class Win32_BaseBoard | Select-Object -Property Manufacturer, Product
```

#### Exportar Información a un Archivo

Para exportar la información recolectada a un archivo CSV, puedes usar el cmdlet `Export-Csv`.

```powershell
Get-WmiObject -Class Win32_Product | Select-Object -Property Name, Version, Vendor | Export-Csv -Path "C:\Inventario_Software.csv" -NoTypeInformation
```

Para hardware:

```powershell
Get-WmiObject -Class Win32_Processor | Select-Object -Property Name, Manufacturer, NumberOfCores, NumberOfLogicalProcessors | Export-Csv -Path "C:\Inventario_Procesador.csv" -NoTypeInformation
```

### Inventario de Activos con CMD

El Command Prompt también puede ser usado para obtener información básica del sistema utilizando herramientas integradas como `wmic`.

#### Listar Paquetes de Software Instalados

```cmd
wmic product get name,version,vendor
```

#### Listar Información del Hardware

- **Procesador**:

```cmd
wmic cpu get name,manufacturer,numberofcores,numberoflogicalprocessors
```

- **Memoria RAM**:

```cmd
wmic memorychip get manufacturer,capacity,speed
```

- **Disco Duro**:

```cmd
wmic diskdrive get model,manufacturer,size
```

- **Placa Base**:

```cmd
wmic baseboard get manufacturer,product
```

#### Exportar Información a un Archivo

Para exportar la información a un archivo, puedes redirigir la salida a un archivo de texto.

```cmd
wmic product get name,version,vendor > C:\Inventario_Software.txt
```

Para hardware:

```cmd
wmic cpu get name,manufacturer,numberofcores,numberoflogicalprocessors > C:\Inventario_Procesador.txt
```

### …