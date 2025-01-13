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

### Estructura del Proyecto (ejemplo no obligatorio)

project/ ┣━ backend/ ┃ ┣━ src/ ┃ ┃ ┣━ config/ ┃ ┃ ┣━ controllers/ ┃ ┃ ┣━ models/ ┃ ┃ ┣━ routes/ ┃ ┃ ┗━ server.js ┃ ┣━ package.json ┃ ┗━ ... ┗━ frontend/ ┣━ src/ ┃ ┣━ components/ ┃ ┣━ pages/ ┃ ┣━ services/ ┃ ┗━ App.jsx (o .tsx) ┣━ package.json ┗━ ...


Esta es una sugerencia. Adáptala según tu criterio, pero mantén **separados** el frontend y el backend.

### Backend (Node/Express)

- **Express** para definir rutas.
- **Mongoose** para la conexión con MongoDB.
- **bcrypt** (o similar) para **encriptar contraseñas**.
- **jsonwebtoken** para emitir y validar **tokens JWT**.
- **DOTENV** para manejar variables de entorno (p. ej., puerto, credenciales, URL de la DB).

#### Rutas de Ejemplo

1. `POST /api/auth/register`  
   - Registra un nuevo usuario.  
2. `POST /api/auth/login`  
   - Verifica credenciales, devuelve un JWT.
3. `GET /api/books`  
   - Lista todos los libros disponibles.
4. `POST /api/books` (solo admin)  
   - Crea un libro.
5. `PUT /api/books/:id` (solo admin)  
   - Actualiza datos de un libro.
6. `DELETE /api/books/:id` (solo admin)  
   - Elimina un libro.
7. `POST /api/loans` (user/admin)  
   - Solicita un préstamo de libro.
8. `PUT /api/loans/:id/return` (user/admin)  
   - Registra la devolución de un libro.

### Frontend (React)

- **React Router** para las **rutas** de la aplicación (p. ej., `/login`, `/register`, `/books`, `/loans`).
- **Axios** (u otra librería HTTP) para comunicarte con el backend.
- **Redux** (o **Context API**):
  - Manejar el estado global de la aplicación (usuarios, libros, etc.).
- **Material-UI** o **Ant Design** (o cualquier otra) para una interfaz estilizada y componentes listos.

#### Vistas Principales

1. **Login** y **Registro**  
   - Formularios controlados para capturar datos.  
   - Llamadas al backend vía Axios.  
   - Guardar el JWT en localStorage/cookies tras iniciar sesión.
2. **Lista de Libros**  
   - Vista pública para ver catálogo de libros.
   - Opción para **crear/editar/eliminar** libros si se es administrador.
3. **Gestión de Préstamos**  
   - Para usuarios normales: botón “Solicitar Préstamo” cuando un libro esté disponible.
   - Para administradores: vista con todos los préstamos activos, posibilidad de registrar devoluciones.
4. **Panel de Usuario**  
   - Mostrar los préstamos vigentes del usuario.
   - Historial de préstamos pasados (si se desea).

---

## Requerimientos Adicionales

- **Validaciones**: Debes validar en el backend que no se puedan prestar libros inexistentes o ya prestados.  
- **Seguridad**:
  - Middleware que verifique el token JWT y asocie la petición a un usuario.
  - Rutas que solo permitan acceso a usuarios con rol específico, si implementas roles.
- **Documentación**:  
  - Se valora el uso de [Swagger](https://swagger.io/) o [Postman Collection](https://learning.postman.com/docs/getting-started/importing-and-exporting-data/) para documentar y probar la API.
- **Manejo de Errores**:
  - Respuestas claras al cliente en caso de errores (usuario duplicado, token inválido, libro no encontrado, etc.).

---

## Entrega y Evaluación

1. **Repositorio**: Proporciona un enlace a tu repositorio con dos carpetas (o dos proyectos):  
   - `backend`  
   - `frontend`
2. **Instrucciones**: Añade un `README.md` con pasos para:
   - Instalar dependencias.
   - Configurar variables de entorno.
   - Ejecutar tanto el **cliente** como el **servidor**.
3. **Funcionalidad**: Se probará:
   - El registro/login de usuarios.
   - La CRUD de libros.
   - El sistema de préstamos/devoluciones.
4. **Calidad de Código**:
   - Estructura clara y limpia.
   - Uso apropiado de promesas (async/await) y manejo de excepciones.
   - Buenas prácticas de React (componentes reutilizables, uso correcto de hooks).
5. **Extras Opcionales**:
   - Despliegue en un servicio gratuito (Heroku, Render, etc.) para mostrar la demo en vivo.
   - Uso de testing (Jest, React Testing Library, etc.).
   - UI extra (filtrado, paginación, búsquedas).

---

### ¡Éxitos en el desarrollo de tu Sistema de Biblioteca!
Este es un **proyecto completo** que te permitirá demostrar tus habilidades en **frontend**, **backend** y **base de datos**. Tómate el tiempo necesario para planificar la arquitectura, implementar las funcionalidades y documentarlo adecuadamente. ¡Mucho éxito! 
