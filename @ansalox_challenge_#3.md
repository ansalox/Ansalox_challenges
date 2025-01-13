## 3. Codificador y decodificador César

### Descripción
El **cifrado César** desplaza cada letra del alfabeto un número fijo de posiciones. Por ejemplo, con desplazamiento 3:  
- `A` → `D`  
- `B` → `E`  
- `Z` → `C` (se reinicia el alfabeto)

### Objetivo
- Codificar y decodificar un texto utilizando este método.

### Pasos a seguir
1. Leer el texto y el desplazamiento (número entero).
2. Implementar la función `codificar(texto, desplazamiento)`:
   - Recorrer cada carácter.
   - Si es letra, desplazarla en el alfabeto (respetar mayúsculas y minúsculas).
   - Si se pasa de `Z` o `z`, volver a `A` o `a`.
3. Implementar la función `decodificar(texto, desplazamiento)` invirtiendo el proceso.
4. Mostrar:
   - El texto original.
   - El texto codificado.
   - (Opcional) El texto decodificado.

### Consideraciones
- Decide si aplicas el desplazamiento **solo** a letras o también a números y símbolos.
- Puedes manejar el alfabeto inglés (26 letras) o incluir la “ñ” para el español.
