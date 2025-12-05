# UNI-Bank
# Simulador de Banco con Reconocimiento Facial

Pequeño simulador en Python (orientado a objetos) que permite crear cuentas, depositar, retirar y transferir. Para operaciones sensibles (retirar/transferir) se activa la cámara y se realiza una verificación facial simple.

- Carpeta: `bank_sim`
- Ejecutables: `main.py` (launcher), `gui.py` (interfaz gráfica)
- Dependencias: `opencv-python`, `numpy`

## Características

✅ Crear cuenta con DNI de 8 dígitos  
✅ Registrar rostro (captura desde cámara)  
✅ Depositar dinero  
✅ Retirar dinero con verificación facial  
✅ Transferir a otras cuentas con verificación facial  
✅ Ver saldo y transacciones  
✅ Base de datos JSON persistente  
✅ Interfaz gráfica (GUI) con Tkinter  
✅ Terminal (CLI) interactiva  

## Instalación

```bash
# Instalar dependencias
pip install -r bank_sim/requirements.txt
```

## Uso

### Opción 1: Interfaz Gráfica (Recomendado)

```bash
cd /home/frvk/Documentos/Turtleproj
python3 bank_sim/main.py
# Seleccione opción "1" para GUI
```

**Flujo en GUI:**
1. Ingrese DNI en el campo de entrada
2. Seleccione una cuenta
3. Use los botones para: crear cuenta, registrar rostro, depositar, retirar, transferir
4. Las operaciones de retirar/transferir abren la cámara automáticamente

### Opción 2: Terminal (CLI)

```bash
cd /home/frvk/Documentos/Turtleproj
python3 bank_sim/main.py
# Seleccione opción "2" para CLI
```

**Flujo en CLI:**
1. Crear cuenta
2. Registrar rostro
3. Depositar
4. Retirar o Transferir (requiere verificación facial en vivo)

### Ejecutar directo GUI

```bash
cd /home/frvk/Documentos/Turtleproj
python3 bank_sim/gui.py
```

### Ejecutar directo CLI

```bash
cd /home/frvk/Documentos/Turtleproj
python3 -c "from bank_sim.main import run_cli; run_cli()"
```

## Estructura

```
bank_sim/
├── bank.py              # Lógica de cuentas y operaciones
├── face_auth.py         # Autenticación facial con OpenCV
├── gui.py               # Interfaz gráfica (Tkinter)
├── main.py              # Launcher CLI/GUI
├── requirements.txt     # Dependencias
├── README.md            # Este archivo
├── db/                  # Carpeta de base de datos (se crea automáticamente)
├── faces/               # Carpeta para fotos de registro (se crea automáticamente)
└── tests/               # Pruebas unitarias
    ├── run_bank_tests.py
    └── test_bank.py
```

## Notas

- El método de verificación usa ORB (feature matching); es simple y no reemplaza sistemas robustos.
- Si la cámara no está disponible, las funciones de facial lanzarán excepción.
- Los datos se guardan en `db/bank_db.json` automáticamente.
- Las fotos de referencia se guardan en `faces/{dni}.jpg`

Ejecutar:

```bash
python bank_sim/main.py
```
