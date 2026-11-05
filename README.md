# MolPrepare_DB 💊💻

<a href="https://colab.research.google.com/github/DACSIF-UAQ/Molprepare_DB/blob/main/MolPrepare_DB.ipynb" target="_parent"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>

Flujo de trabajo computacional automatizado para la preparación masiva de ligandos, partiendo de secuencias 2D (SMILES) hasta generar estructuras tridimensionales optimizadas en formato SDF, listas para utilizarse en acoplamiento molecular (docking). 

Este entorno está optimizado para ejecutarse íntegramente en Google Colab.

## ⚙️ Características y Flujo de Trabajo

1. **Curación Estructural (RDKit):** Estandarización de grupos funcionales, neutralización y eliminación de sales/metales y duplicados.
2. **Filtrado Fisicoquímico:** Restricción por peso molecular (configurable).
3. **Filtros Toxicológicos:** Identificación de alertas estructurales y compuestos de interferencia mediante los catálogos **PAINS, BRENK y NIH**.
4. **Viabilidad Sintética:** Cálculo del *Synthetic Accessibility Score* (SA Score) para la priorización de candidatos.
5. **Estado de Protonación (MolGpKa):** Predicción de pKa mediante redes neuronales de grafos y asignación del estado de carga al pH fisiológico (7.4) u objetivo.
6. **Geometría 3D y Minimización:** Generación conformacional con el algoritmo **ETKDG** y minimización energética mediante el campo de fuerza **MMFF94**.
7. **Empaquetado:** Exportación directa a formato único y múltiple `.sdf`, incluyendo un reporte detallado en `.csv`.

## 📥 Requisitos de Entrada

El cuaderno requiere como entrada un archivo `.csv` simple con dos columnas principales (sin importar mayúsculas o espacios):
*   `ID`: Identificador único de la molécula.
*   `SMILES`: Cadena de texto con la estructura 2D (no es necesario canonizar).

## 📖 Citas y Referencias

Este código forma parte del protocolo metodológico desarrollado para la identificación de inhibidores de MRP4/ABCC4. Si utilizas o adaptas este flujo de trabajo, por favor cita el proyecto base y las herramientas adaptadas al flujo:

**Tesis asociada:**
* Franco Chávez, B., & Urdez Rojas, L. Á. (2026). *IDENTIFICACIÓN in silico DE POTENCIALES INHIBIDORES DE MRP4/ABCC4 PARA EL TRATAMIENTO DE LA LEUCEMIA LINFOBLÁSTICA AGUDA* [Tesis de Licenciatura, Universidad Autónoma de Querétaro]. Director de tesis: Dr. Rubén Antonio Romo Mancillas. Repositorio Institucional UAQ. URI: https://ri-ng.uaq.mx/handle/123456789/13105

**Algoritmos y Herramientas integradas:**
* **RDKit:** Open-source cheminformatics. https://www.rdkit.org
* **MolGpKa:** Li, X., et al. (2021). MolGpKa: A Web Server for Small Molecule pKa Prediction Using a Graph-Convolutional Neural Network. *J. Chem. Inf. Model.*
* **ETKDG:** Wang, S., Witek, J., Landrum, G. A., & Riniker, S. (2020). Improving conformer generation for small rings and macrocycles based on distance geometry and experimental torsional-angle preferences. *J. Chem. Inf. Model.*, 60(4), 2044-2058.
* **MMFF94:** Halgren, T. A. (1996). Merck molecular force field. I. Basis, form, scope, parameterization, and performance of MMFF94. *J. Comput. Chem.*, 17(5-6), 490-519.
* **SA Score:** Ertl, P., & Schuffenhauer, A. (2009). Estimation of synthetic accessibility score of drug-like molecules based on molecular complexity and fragment contributions. *J. Cheminform.*, 1(1), 1-11.
* **PAINS:** Baell, J. B., & Holloway, G. A. (2010). New substructure filters for removal of pan assay interference compounds (PAINS)... *J. Med. Chem.*, 53(7), 2719-2740.

---
*Desarrollado por QFB. Luis Ángel Urdez Rojas en la Facultad de Química, UAQ.*
