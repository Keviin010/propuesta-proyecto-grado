# Verificación y Validación — Proyecto OrderNow

## Características mínimas
- Catálogo visible de productos con nombre, precio, stock e imagen.  
- Carrito de compras para agregar o quitar productos.  
- Creación y registro de órdenes con estado inicial "En proceso".  
- Panel administrador para CRUD de productos y control de stock.  
- Listado de órdenes con cambio de estado ("En proceso", "Lista", "Completada").  
- Confirmación visual del pedido con número de orden.

---

## Casos de uso identificados antes de la construcción

###1. Crear y enviar orden
**Actor:** Cliente  
**Descripción:** El cliente selecciona productos y confirma la orden.  
**Criterios de aceptación:**  
- Mostrar catálogo y permitir agregar productos.  
- Guardar la orden en la base de datos.  
- Estado inicial: "En proceso".

---

###2. Gestión de productos
**Actor:** Administrador  
**Descripción:** El administrador agrega, edita o elimina productos.  
**Criterios de aceptación:**  
- Validar nombre, precio y stock.  
- Cambios visibles en el catálogo.

---

###3. Control de stock y órdenes
**Actor:** Administrador  
**Descripción:** El administrador actualiza el stock y cambia el estado de las órdenes.  
**Criterios de aceptación:**  
- No permitir pedidos sin stock.  
- Permitir cambiar estado a "Lista" o "Completada".

---

## Validación
- Formularios con campos requeridos y validación en cliente y servidor.  
- Prueba de creación de pedido con stock insuficiente.  
- Confirmación visible del pedido creado.





