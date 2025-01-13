# Prueba Técnica : Sistema de Biblioteca con React, Node y MongoDB

Este desafío está inspirado en una **prueba técnica** para un puesto de desarrollador(a) Full Stack. El objetivo es construir un sistema de biblioteca que permita **registrar usuarios, manejar libros** y llevar un seguimiento de los préstamos y devoluciones, utilizando el stack **MERN** (MongoDB, Express/Node, React).

---

## Requerimientos Generales

1. **Frontend**: React (preferiblemente con [Create React App](https://create-react-app.dev/) o [Vite](https://vitejs.dev/)).
2. **Backend**: Node.js con el framework [Express](https://expressjs.com/).
3. **Base de Datos**: [MongoDB](https://www.mongodb.com/) usando [Mongoose](https://mongoosejs.com/) para la capa de modelo.
4. **Autenticación**: Basada en [JWT (JSON Web Tokens)](https://jwt.io/).
5. **Gestión de Estado** (en el cliente): Puede ser con [Redux](https://redux.js.org/) o [React Context](https://react.dev/reference/react/useContext).
6. **Diseño / UI**: Se recomienda usar una librería de componentes como [Material-UI](https://mui.com/) o [Ant Design](https://ant.design/).

---

## Funcionalidades Principales

1. **Registro e Inicio de Sesión de Usuario**  
   - El usuario debe poder **registrarse** con nombre, email y contraseña.  
   - El usuario debe poder **iniciar sesión** con sus credenciales, recibiendo un **token JWT** que le permita realizar operaciones.

2. **Gestión de Libros**  
   - Crear un modelo de libro que incluya, al menos, los campos:
     - Título
     - Autor
     - ISBN
     - Categoría (por ejemplo, “Ficción”, “Ciencia”, “Historia”, etc.)
     - Disponibilidad (si está disponible o prestado)
   - Permitir **crear**, **editar**, **listar** y **eliminar** libros desde el panel de administrador.
   - Mostrar un **catálogo público** de libros para que los usuarios vean la disponibilidad.

3. **Préstamo y Devolución de Libros**  
   - Los usuarios autenticados deben poder **solicitar** un préstamo de libro si está disponible.
   - Cuando un libro está prestado, se debe **marcar** como “no disponible”.
   - El usuario, o un administrador, debe poder **registrar la devolución** de un libro, pasando su estado a “disponible”.
   - Se recomienda crear un modelo separado (p. ej., `Loan` o `Borrow`) para almacenar la información de cada préstamo: 
     - ID del libro
     - ID del usuario
     - Fecha de préstamo
     - Fecha de devolución (si aplica)

4. **Roles de Usuario** (Opcional pero recomendado)
   - **Rol “administrador”**: acceso total para CRUD de libros y gestión de préstamos.  
   - **Rol “usuario normal”**: acceso limitado (p. ej., solo solicitar préstamos, ver historial y ver catálogo).

---

## Detalles Técnicos y Librerías Sugeridas

### Estructura del Proyecto

