# crear_readme.py
# Este script crea un archivo README.docx para tu proyecto

from docx import Document
from docx.shared import Inches, Pt
from docx.enum.text import WD_ALIGN_PARAGRAPH
from docx.enum.style import WD_STYLE_TYPE
import os

# Crear un nuevo documento
doc = Document()

# === Portada ===
title = doc.add_heading('Análisis de Tasas de Empleo y Desempleo', 0)
title.alignment = WD_ALIGN_PARAGRAPH.CENTER

subtitle = doc.add_paragraph('España vs Unión Europea (2006-2024)')
subtitle.alignment = WD_ALIGN_PARAGRAPH.CENTER
doc.add_paragraph('')

# Añadir separador
doc.add_paragraph('')  # Espacio
doc.add_paragraph('-' * 60).alignment = WD_ALIGN_PARAGRAPH.CENTER
doc.add_paragraph('')  # Espacio

# Información del autor
author = doc.add_paragraph()
author.add_run('Autor: ').bold = True
author.add_run('Daniel')
doc.add_paragraph('Curso: Data Analyst')
doc.add_paragraph('Fecha: ' + __import__('datetime').datetime.now().strftime('%d/%m/%Y'))

doc.add_page_break()

# === Índice ===
doc.add_heading('📌 Índice', level=1)
index = [
    "Estructura del Proyecto",
    "Características del Análisis",
    "Tecnologías Utilizadas",
    "Instalación y Uso",
    "Resultados Destacados",
    "Datos de Entrada y Salida",
    "Autor",
    "Licencia"
]
for item in index:
    doc.add_paragraph(item, style='List Bullet')

doc.add_page_break()

# === Secciones del README ===
sections = [
    ("📁 Estructura del Proyecto", """
Proyecto-final/
│
├── DATA/
│   ├── Tasa de empleo.csv          # Datos de tasa de empleo
│   └── Tasa de desempleo.csv       # Datos de tasa de desempleo
│
├── analisis_empleo_desempleo.py    # Script principal de análisis
├── datos_combinados_empleo_desempleo.csv  # Datos combinados
├── resumen_analisis.txt            # Resumen estadístico
├── requirements.txt                # Dependencias
└── README.md                       # Este archivo
    """),

    ("🚀 Características del Análisis", """
- **Combinación de datasets**: Unificación de empleo y desempleo
- **Limpieza de datos**: Conversión de comas decimales a puntos
- **Estadísticas descriptivas**: Media, desviación, máximos y mínimos
- **Visualizaciones**: 5 gráficos comparativos
- **Análisis de diferencias**: España vs UE
- **Correlaciones**: Entre empleo y desempleo
    """),

    ("🛠️ Tecnologías Utilizadas", """
- **Python 3.8+**
- **Pandas**: Manipulación de datos
- **NumPy**: Cálculos numéricos
- **Matplotlib & Seaborn**: Gráficos
- **Docx**: Generación de este documento
    """),

    ("⚙️ Instalación y Uso", """
1. Clonar el repositorio:
   git clone https://github.com/tu-usuario/empleo-desempleo-espana-ue.git
   cd empleo-desempleo-espana-ue

2. Crear entorno virtual:
   python -m venv venv
   venv\\Scripts\\activate  # Windows
   source venv/bin/activate # Linux/Mac

3. Instalar dependencias:
   pip install -r requirements.txt

4. Ejecutar el análisis:
   python analisis_empleo_desempleo.py
    """),

    ("📊 Resultados Destacados", """
- **Máximo desempleo en España**: 26.1% (2013)
- **Mínimo desempleo en España**: 8.2% (2007)
- **Tendencia positiva**: Reducción constante desde 2014
- **Brecha UE**: España tiene mayor volatilidad
- **Empleo**: España por debajo de la media de la UE
    """),

    ("📁 Estructura de Datos", """
**Datos de Entrada:**
- Ámbito geográfico: España / Unión Europea
- Periodo: Año (2006–2024)
- Total: Tasa porcentual (con coma decimal)

**Datos de Salida:**
- Tasa_Empleo: float (punto decimal)
- Tasa_Desempleo: float (punto decimal)
    """),

    ("👥 Autor", """
**Daniel**  
Curso Data Analyst  
Contacto: relojius@gmail.com  
GitHub: [relojius](https://github.com/relojius)
    """),

    ("📄 Licencia", """
Este proyecto está bajo la Licencia MIT.

Puedes usar, modificar y distribuir este código libremente.
    """)
]

for title, content in sections:
    doc.add_heading(title, level=1)
    p = doc.add_paragraph()
    for line in content.strip().split('\n'):
        line = line.strip()
        if line.startswith('- ') or line.startswith('* '):
            doc.add_paragraph(line, style='List Bullet')
        elif line.startswith('#') or line.startswith('```'):
            doc.add_paragraph(line, style='Code')
        else:
            if line:
                doc.add_paragraph(line)

# Añadir nota final
doc.add_page_break()
note = doc.add_paragraph()
note.add_run("✅ Documento generado automáticamente").bold = True
note.alignment = WD_ALIGN_PARAGRAPH.CENTER

# === Guardar el archivo ===
output_path = 'README.docx'
doc.save(output_path)

print(f"✅ Archivo '{output_path}' creado con éxito en la carpeta actual.")
print("➡️ Puedes editarlo con Word y subirlo a GitHub.")
