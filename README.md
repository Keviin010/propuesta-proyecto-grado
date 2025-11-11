# REQUERIMIENTOS FINALES — OrderNow: Sistema de Pedidos para Restaurantes

**Autor:** Kevin Dair Royo Cuesta  
**Carrera:** Tecnología en Desarrollo de Software  
**Universidad:** Universidad Católica Luis Amigó

---

## Índice
1. Resumen ejecutivo  
2. Objetivo  
3. Alcance  
4. Requisitos funcionales  
5. Requisitos no funcionales (calidad)  
6. Casos de uso principales  
7. Criterios de aceptación y pruebas esenciales  
8. Plan de Validación y Verificación (V&V)  
9. Entregables y documentación asociada  
10. Priorización y estimación  

---

## 1. Resumen ejecutivo
OrderNow es una plataforma web pensada para optimizar el proceso de pedidos en establecimientos de comida (restaurantes, puestos y cafeterías). Su propósito es facilitar al cliente la selección y el envío de pedidos, y ofrecer a los administradores herramientas sencillas para gestionar el catálogo, y procesar órdenes.

---

## 2. Objetivo
Diseñar y desarrollar un sistema web que permita a los clientes realizar pedidos de forma ágil y segura, y a los administradores gestionar productos, stock y órdenes con trazabilidad.

### Objetivos específicos
- Presentar un catálogo claro y accesible con información esencial de los productos.  
- Implementar un flujo de carrito y checkout que garantice la creación correcta de órdenes.  
- Ofrecer un panel administrativo para CRUD de productos, control de stock y gestión de órdenes.  
- Garantizar validaciones cliente/servidor que eviten inconsistencias y errores frecuentes.

---

## 3. Alcance
**Incluye (MVP):**
- Catálogo público de productos con nombre, precio, stock e imagen.  
- Carrito de compras con operaciones de añadir/quitar/ajustar cantidades.  
- Proceso de checkout que genera una orden con estado inicial "En proceso".  
- Panel administrativo básico para CRUD de productos y visualización/gestión de órdenes.  
- Validaciones esenciales en cliente y servidor.

**Exclusiones (fase inicial):**
- Integración con pasarelas de pago en producción.  
- Integraciones con POS físicos.  
- Multisede/multi-tenant avanzado.  
- Pruebas de carga a gran escala.

---

## 4. Requisitos funcionales
- **RF01 — Catálogo:** Mostrar productos activos con nombre, descripción breve, precio, stock e imagen.  
- **RF02 — Carrito:** Añadir, eliminar y modificar cantidades; ver subtotal y total.  
- **RF03 — Crear orden:** Registrar la orden en la base de datos con número único y estado "En proceso".  
- **RF04 — Panel administrativo:** Crear, editar y eliminar productos; gestionar stock e imágenes.  
- **RF05 — Control de stock:** Impedir confirmación de órdenes si la cantidad solicitada supera el inventario.  
- **RF06 — Visualización de órdenes:** Listado de órdenes con filtros por estado y detalle por orden.  
- **RF07 — Validaciones:** Formularios con campos obligatorios y validación tanto cliente como servidor.  
- **RF08 — Confirmación:** Mostrar confirmación al cliente con número de orden y resumen después del checkout.

---

## 5. Requisitos no funcionales (calidad)
Basados en buenas prácticas y criterios de calidad:

- **Usabilidad:** Interfaz intuitiva y responsive, accesible para distintos perfiles de usuario.  
- **Fiabilidad:** Persistencia e integridad de datos; manejo adecuado de errores.  
- **Rendimiento:** Operaciones críticas con latencias aceptables en condiciones nominales.  
- **Seguridad:** Almacenamiento seguro de credenciales, validaciones server-side y control de accesos.  
- **Mantenibilidad:** Código documentado y modular para facilitar futuras mejoras.  
- **Portabilidad:** Compatibilidad con navegadores modernos y dispositivos móviles.  



---

## 6. Casos de uso principales

### Caso de uso 1 — Registro de cliente
**Actor:** Cliente  
**Descripción:** El usuario crea una cuenta para realizar pedidos.  
**Precondición:** No tener cuenta previa.  
**Flujo principal:** ingreso de nombre, correo y contraseña → validación → registro → confirmación.  
**Resultado esperado:** Registro guardado y confirmación visible; evitar correos duplicados.

### Caso de uso 2 — Inicio de sesión
**Actor:** Cliente  
**Descripción:** Acceso al sistema mediante correo y contraseña.  
**Resultado esperado:** Acceso correcto si credenciales válidas; mensaje de error en caso contrario.

### Caso de uso 3 — Crear orden (checkout)
**Actor:** Cliente  
**Descripción:** Cliente finaliza compra desde el carrito.  
**Flujo principal:** validar stock → crear orden (estado "En proceso") → mostrar confirmación.  
**Resultado esperado:** Orden registrada con número y stock actualizado si corresponde.

### Caso de uso 4 — Gestión de productos
**Actor:** Administrador  
**Descripción:** CRUD de productos y actualización de stock.  
**Resultado esperado:** Cambios reflejados en catálogo público; validaciones de campos.

### Caso de uso 5 — Gestión y visualización de órdenes
**Actor:** Administrador  
**Descripción:** Visualizar, filtrar y actualizar estados de las órdenes (En proceso, Lista, Completada).  
**Resultado esperado:** Filtros funcionales y cambios de estado persistentes.

---

## 7. Criterios de aceptación y pruebas esenciales
Cada funcionalidad debe incluir pruebas que verifiquen sus criterios:

- **Registro:** No permitir correos duplicados; mostrar confirmación.  
- **Login:** Validación de credenciales; manejo de mensajes de error.  
- **Carrito/checkout:** Bloquear checkout cuando el carrito esté vacío o cuando exista falta de stock; generar orden con número único.  
- **Control de stock:** Al crear una orden válida, decrementar stock; impedir crear orden si stock insuficiente.  
- **Panel admin:** Validaciones en formularios; cambios reflejados en catálogo.  
- **Pruebas E2E:** Flujo completo desde catálogo → carrito → checkout → ver orden en panel admin.

---

## 8. Plan de Validación y Verificación (V&V)

### Validación (¿construimos lo correcto?)
- **Revisión de requisitos:** Revisiones periódicas con stakeholders para asegurar alineación.  
- **Pruebas de usabilidad:** Entrevistas y pruebas con prototipos para comprobar facilidad de uso.  
- **Prueba de aceptación:** Escenarios reales ejecutados por usuarios representativos antes de una release.

### Verificación (¿construimos bien?)
- **Trazabilidad:** Mapear cada requisito a casos de uso y casos de prueba.  
- **Pruebas unitarias e integración:** Cobertura en lógica crítica (stock, creación de órdenes).  
- **Consistencia de datos:** Pruebas que validen transacciones y comportamiento ante errores (rollback).  
- **Checklist de seguridad:** Verificación de almacenamiento de credenciales y control de accesos.

### Casos de prueba prioritarios (ejemplos)
- Intento de registro con correo duplicado → debe rechazarse.  
- Intento de checkout con cantidad superior al stock → debe rechazarse.  
- Creación de orden con múltiples ítems → stock decrementado correctamente y orden registrada.  
- Cambio de estado de una orden por admin → reflejado en la UI del administrador.

---

## 9. Entregables y documentación asociada
- Documento de requerimientos (este archivo).  
- Diagrama de casos de uso y diagramas UML (clases, ER).  
- Prototipos o capturas de pantallas del flujo cliente y admin.  
- Matriz de trazabilidad requisito → caso de uso → prueba.  

  ---

## 10. Priorización y estimación
- **Prioridad alta:** Catálogo, carrito, checkout, control de stock y confirmación.  
- **Prioridad media:** Panel admin completo, generación de reportes/estadísticas.  
- **Estimación inicial:** Flujo de creación y envío de orden — 5 puntos de historia (valor referencial).

---

### Sugerencia de commit para GitHub

