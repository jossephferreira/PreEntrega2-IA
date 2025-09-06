# Prompt Engineering Educativo: Generación de materiales personalizados con IA

## 📌 Introducción
Este proyecto busca demostrar cómo la ingeniería de prompts puede ayudar a
generar materiales educativos personalizados, tanto en formato **texto** como en
**imágenes**, utilizando modelos de IA.

## 🎯 Objetivos
- Demostrar la comprensión de los principios y técnicas detrás del *Fast Prompting*.
- Experimentar con diferentes configuraciones de prompts para optimizar la eficacia.
- Preparar una demostración efectiva en **Jupyter Notebook** mostrando la POC.
- Analizar si las técnicas aprendidas permiten mejorar la propuesta planteada en la Preentrega.
- Diseñar un sistema de prompts educativos para generar materiales personalizados en texto e imagen.

## 🧩 Problemática
Los docentes carecen de tiempo y recursos para personalizar materiales
educativos, lo que genera falta de adaptación a distintos estilos de
aprendizaje, niveles educativos y contextos culturales.

## 💡 Propuesta de Solución
- **Módulo Texto-Texto**: explicaciones adaptadas, ejercicios, resúmenes.
- **Módulo Texto-Imagen**: diagramas, infografías, ilustraciones conceptuales.
- Uso de técnicas de prompting: *zero-shot, few-shot, chain-of-thought, role prompting*.

## ⚙️ Metodología
1. Investigación inicial de necesidades educativas.
2. Diseño de prompts.
3. Iteración y testing con distintos niveles.
4. Validación con retroalimentación.
5. Documentación y replicación.

## 🔧 Herramientas y Tecnologías
- Modelos: OpenAI GPT, Stable Diffusion, Midjourney.
- Lenguaje: Python.
- Entorno: Jupyter Notebook.
- Librerías: `openai`, `diffusers`, `torch`.

## 🚀 Implementación

### Ejemplo de prompt texto-texto
```python
from openai import OpenAI

client = OpenAI(api_key="TU_API_KEY")

prompt = """
Genera una explicación sobre la fotosíntesis para estudiantes de secundaria,
incluyendo:
- Definición clara
- 2 ejemplos prácticos
- 3 preguntas de comprobación
- Una analogía cotidiana
"""

response = client.chat.completions.create(
    model="gpt-4o-mini",
    messages=[{"role": "user", "content": prompt}]
)

print(response.choices[0].message.content)
```

### Ejemplo de prompt texto-imagen
```python
from diffusers import StableDiffusionPipeline
import torch

pipe = StableDiffusionPipeline.from_pretrained("CompVis/stable-diffusion-v1-4").to("cuda")

prompt = """
Infografía educativa que muestre el ciclo del agua,
con flechas claras, etiquetas descriptivas y colores suaves.
"""

image = pipe(prompt).images[0]
image.save("ciclo_agua.png")
```

## 📂 Estructura del Repositorio
```
Prompt-Engineering-Educativo/
│
├── README.md              # Documentación completa del proyecto
├── notebooks/
│   └── POC.ipynb          # Notebook con la Prueba de Concepto
├── prompts/
│   ├── texto_texto.md     # Biblioteca de prompts para generación de texto
│   └── texto_imagen.md    # Biblioteca de prompts para generación de imágenes
├── requirements.txt       # Librerías necesarias
└── docs/
    └── PreEntrega2.pdf    # Documento original entregado
```

## 🏆 Resultados Esperados
- Biblioteca de prompts educativos optimizados.
- Protocolo de validación de contenidos.
- Documentación para replicar el sistema en diferentes contextos educativos.
