# Análisis de Tasas de Empleo y Desempleo: España vs Unión Europea (2006-2024)

Este proyecto realiza un análisis comparativo de las tasas de empleo y desempleo entre España y la Unión Europea desde 2006 hasta 2024, utilizando Python para el procesamiento de datos y la visualización.

## Estructura del Proyecto


print(f"Archivo '{output_path}' creado con éxito en la carpeta actual.")
print("Puedes editarlo con Word y subirlo a GitHub.")

## Características del Análisis

### Procesamiento de Datos
- **Combinación de datasets**: Unificación de datos de empleo y desempleo
- **Limpieza de datos**: Conversión de formatos (coma decimal a punto decimal)
- **Validación de datos**: Manejo de valores inconsistentes o faltantes

### Análisis Realizado
- **Estadísticas descriptivas**: Media, desviación estándar, mínimos y máximos
- **Análisis comparativo**: España vs Unión Europea
- **Correlaciones**: Relación entre empleo y desempleo
- **Tendencias temporales**: Evolución 2006-2024

### Visualizaciones Generadas
1. Evolución del empleo y desempleo en España
2. Evolución del empleo y desempleo en la UE
3. Comparativa España vs UE (empleo)
4. Comparativa España vs UE (desempleo)
5. Diferencias absolutas entre España y UE

## Tecnologías Utilizadas

- **Python 3.8+**
- **Pandas**: Manipulación y análisis de datos
- **NumPy**: Cálculos numéricos
- **Matplotlib**: Visualizaciones básicas
- **Seaborn**: Visualizaciones estadísticas
##  Instalación y Uso
Requisitos de sistema
pandas>=1.3.0
numpy>=1.21.0
matplotlib>=3.4.0
seaborn>=0.11.0
Resultados Destacados
Tendencias Principales
```bash
1. Clonar el repositorio
git clone https://github.com/relojius/proyecto_final.git
cd empleo-desempleo-espana-ue
2. Crear entorno virtual
python -m venv venv
venv\Scripts\activate     # Windows
3. Isntalar dependencias
pip install -r requirements.txt
4. Realizar análisis de datos obtenidos
Con el el programa visual studio y a partir de un código generado por pandas, numpy y otras librerias. Observamos las siguiente tendencias princiapales


España : Mayor volatilidad en ambas tasas
Unión Europea : Mayor estabilidad y tendencia constante
Brecha España-UE : Diferencia significativa en periodos de crisis

Puntos Clave

Máximo desempleo España : 26,1% (2013)
Mínimo desempleo España : 8,2% (2007)
Brecha empleo España-UE : Promedio -3.3 puntos
Brecha desempleo España-UE : Promedio +5.8 puntos

Estructura de datos
datos de Entrada

Ámbito geográfico : España / Unión Europea
Periodo : Año (2006-2024)
Total : Tasa porcentual (formato europeo con coma decimal)

Datos de Salida

Tasa_Empleo : Float (formato internacional con punto decimal)
Tasa_Desempleo : Float (formato internacional con punto decimal)

Autor
Daniel - https://github.com/relojius
Licencia
Este proyecto está bajo la Licencia MIT - ver el archivo LICENSE para más detalles.
Soporte
Si tienes preguntas o encuentras algún problema:

Contacto: relojius@gmail.com
