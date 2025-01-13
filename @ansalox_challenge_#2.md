## 2. Contar la frecuencia de cada palabra y la más repetida

### Descripción
La idea es procesar un texto para determinar cuántas veces aparece cada palabra y así descubrir cuál o cuáles son las más usadas.

### Objetivo
- Identificar la **frecuencia** de todas las palabras.
- Hallar la(s) palabra(s) con la frecuencia más alta.

### Pasos a seguir
1. Leer la cadena de texto completa.
2. Normalizar:
   - Convertir todo a minúsculas.
   - (Opcional) Quitar signos de puntuación para evitar confusiones.
3. Separar la cadena en palabras (usando espacios, por ejemplo).
4. Llevar un registro (diccionario/objeto/`Map`) de cuántas veces aparece cada palabra.
5. Calcular la frecuencia máxima.
6. Obtener las palabras que tengan esa frecuencia.
7. Mostrar:
   - El conteo de cada palabra.
   - La(s) palabra(s) más repetida(s).

### Consideraciones
- Puedes manejar plurales, sinónimos o “stopwords” si quieres profundizar.
- Probar con textos largos para ver eficiencia.
