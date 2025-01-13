## 5. Resolver un laberinto NxN

### Descripción
Dispones de una **matriz NxN** que representa un laberinto:
- `0` para celdas transitables.
- `1` para celdas bloqueadas.  
La entrada está en `(0, 0)` y la salida en `(N-1, N-1)`.

### Objetivo
- Encontrar un **camino** desde la esquina superior izquierda hasta la esquina inferior derecha, si es que existe.

### Pasos a seguir
1. Leer el valor de `N` (tamaño de la matriz).
2. Generar o recibir la matriz con valores `0` y `1`.
3. Implementar un algoritmo de búsqueda (DFS, BFS, etc.) para encontrar la ruta:
   - Solo se puede mover a celdas con `0`.
   - Definir los movimientos permitidos (arriba, abajo, izquierda, derecha, etc.).
4. Marcar las celdas visitadas para evitar ciclos.
5. Concluir la búsqueda cuando se llegue a `(N-1, N-1)` o no queden celdas por explorar.
6. Mostrar la ruta encontrada o indicar si no existe.

### Consideraciones
- Puedes mostrar la ruta como una lista de coordenadas o “pintarla” en la matriz.
- Prueba con distintos tamaños para evaluar el rendimiento.

---

### Notas Finales
- Cada desafío puede tener su propio `README.md` con estos pasos **sin** el código de la solución.
- La **solución** puede ir en archivos separados (`solucion.js`, `solucion.py`, etc.) o en otra rama del repositorio.
- Personaliza, añade o quita requisitos a tu gusto. ¡La idea es fomentar el razonamiento y la práctica constante!
