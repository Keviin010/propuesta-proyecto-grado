# OrderNow — Sistema de Pedidos para Restaurantes
**Autor:** Kevin Dair Royo Cuesta  

---

## Objetivo  
Diseñar y desarrollar un sistema web que permita a los clientes realizar pedidos de forma rápida y a los administradores gestionar productos, stock y órdenes.  

---

## Objetivos específicos  
- Mostrar catálogo de productos del establecimiento.  
- Permitir a los clientes crear y enviar órdenes.  
- Gestionar stock y productos desde un panel administrador.  
- Marcar órdenes como completadas y habilitar vista de pedidos listos.  

---

## Funcionalidades principales  
- Pantalla de productos disponibles.  
- Carrito de compras y creación de órdenes.  
- Panel administrador para gestionar productos y stock.  
- Seguimiento de órdenes: en proceso, completadas, listas para recoger.  

---

## Tecnologías  
- **Frontend:** React + Next.js 14 (App Router)  
- **Backend:** Node.js con Server Actions  
- **Base de datos:** MySQL con Prisma ORM  

---

## Metodología  
1. Análisis y levantamiento de requisitos.  
2. Diseño de la base de datos y diagramas UML.  
3. Implementación del backend, frontend y conexión a la base de datos.  
4. Pruebas unitarias e integración.  
5. Documentación y despliegue en GitHub.  

---

## Impacto esperado  
Optimizar la toma de pedidos en restaurantes mediante un sistema simple, ágil y centralizado para clientes y administradores.  

---

## Usuarios objetivo  
- Clientes de restaurantes o puestos de comida.  
- Administradores o encargados del establecimiento.

## Descargar diagrama pdf
[Diagrama pdf](Ordernow.pdf)

### Diagrama del Proyecto
---
[diagrama](sistema.jpg)
---

# Historias de Usuario

## Crear y enviar orden
Como cliente, quiero seleccionar productos del catálogo y confirmar una orden, para que el restaurante la reciba.

*Criterios de aceptación:*
- Catálogo visible con productos disponibles.
- Carrito para agregar o quitar productos.
- Confirmación y registro de la orden en la base de datos.
- Estado inicial de la orden: "En proceso".

---

## Gestión de productos
Como administrador, quiero agregar, editar o eliminar productos, para mantener actualizado el menú.

*Criterios de aceptación:*
- Formulario con nombre, precio, stock e imagen.
- Validación de campos antes de guardar.
- Cambios reflejados en el catálogo.

---

## Control de stock
Como administrador, quiero actualizar el stock de cada producto, para que los clientes vean solo lo disponible.

*Criterios de aceptación:*
- Modificación de stock en el panel.
- Bloqueo de pedidos si no hay stock.
- Catálogo actualizado en tiempo real.

---

## Visualización de órdenes
Como administrador, quiero ver todas las órdenes en una lista, para gestionarlas fácilmente.

*Criterios de aceptación:*
- Listado de órdenes con estado (en proceso, completada, lista para recoger).
- Posibilidad de cambiar el estado desde el panel.
- Filtros por estado.

---

## Confirmación de pedido
Como cliente, quiero recibir un mensaje al enviar mi orden, para estar seguro de que fue registrada.

*Criterios de aceptación:*
- Mensaje de confirmación en pantalla con número de orden.
- Resumen de productos y precio total.

## Prioridad
Alta

## Estimación
5 puntos de historia
