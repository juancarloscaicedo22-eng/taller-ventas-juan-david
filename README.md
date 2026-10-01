# Taller de Ventas - Juan David

Sistema de registro de ventas con Firebase Authentication y Firestore.
Incluye login con Email y Google, y diagrama de frecuencia por producto.

## Diagrama de Flujo + Frecuencia

```mermaid
flowchart TD
    A([INICIO - Login]) --> B{¿Acción?}
    B -- Crear Cuenta --> C[createUserWithEmailAndPassword]
    B -- Email --> D[signInWithEmailAndPassword]
    B -- Google --> E[signInWithPopup]
    C --> F[App Ventas]
    D --> F
    E --> F
    F --> G[Formulario Venta<br/>Fecha Producto Cantidad Precio]
    G --> H[importe = cantidad * precio]
    H --> I[(Firestore ventas)]
    I --> J[onSnapshot cargarVentas]
    J --> K[productosMap suma importe]
    K --> L[Chart.js Bar]
    L --> M[/DIAGRAMA DE FRECUENCIA/]
    M --> N([FIN])
  ```
