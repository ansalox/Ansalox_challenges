## 1. Verificar si una frase es un pangrama

### Descripción
Un **pangrama** es una frase que contiene todas las letras del alfabeto al menos una vez.  
Un ejemplo clásico (en inglés) es:
> "The quick brown fox jumps over the lazy dog"

### Objetivo
Determinar si la frase ingresada por el usuario es un pangrama.

### Pasos a seguir
1. Leer una cadena de texto completa (incluyendo espacios y mayúsculas).
2. Normalizar la frase (convertir a minúsculas, eliminar espacios extra, etc.).
3. Recorrer cada carácter:
   - Verificar si es una letra (de `a` a `z`).
   - Si lo es, agregarla a un **conjunto** (o `Set`) de letras encontradas.
4. Comparar la cantidad de letras únicas con la cantidad total del alfabeto (26 si usas el alfabeto inglés).
5. Mostrar un mensaje que indique si la frase es pangrama o no.

### Consideraciones
- Puedes ignorar o incluir la “ñ” y caracteres acentuados, dependiendo de la complejidad que desees.
- Si incluyes la “ñ” en español, tendrías que verificar 27 letras.
