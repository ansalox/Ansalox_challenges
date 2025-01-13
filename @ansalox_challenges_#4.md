## 4. Validador de contraseñas seguras

### Descripción
Se busca validar que una contraseña cumpla ciertos criterios mínimos de **complejidad**.

### Objetivo
- Evaluar una contraseña y determinar si es suficientemente “fuerte”.

### Requisitos mínimos (por ejemplo)
1. Al menos **8 caracteres** de longitud.
2. Al menos **1 letra mayúscula**.
3. Al menos **1 letra minúscula**.
4. Al menos **1 dígito** (`0-9`).
5. Al menos **1 carácter especial** (por ejemplo, `@, #, $, %, &`).

### Pasos a seguir
1. Leer la contraseña.
2. Verificar cada requisito.
3. Recopilar en una lista o arreglo qué requisitos no se cumplen (si hay alguno).
4. Mostrar:
   - Un mensaje de éxito si cumple todos.
   - Un mensaje con los criterios incumplidos, si falla.

### Consideraciones
- Define claramente qué se considera “carácter especial”.
- Puedes añadir más restricciones (evitar repeticiones, no contener el nombre de usuario, etc.).
