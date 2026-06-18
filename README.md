# Política monetaria del BCE e impacto macroeconómico en España (2022–2024)

Análisis del ciclo de subidas de tipos del Banco Central Europeo entre 2022 y 2024 y su transmisión al crédito, la inflación y el empleo en España. Los datos se obtienen directamente de la API del BCE (datasets MIR, FM, HICP y LFSI).

🔗 **[Ver app interactiva en Streamlit](https://inigoochoa-macro-spain-ecb.streamlit.app)** *(enlace disponible tras el despliegue)*

## Datos

Fuente: [API del BCE](https://data-api.ecb.europa.eu). Período de análisis: enero 2022 – diciembre 2024.

| Serie | Dataset | Descripción |
|-------|---------|-------------|
| `ecb_rates` | FM | Tipo de depósito del BCE |
| `int_hog` | MIR | Tipo de interés hogares (nuevas operaciones) |
| `int_emp` | MIR | Tipo de interés empresas (nuevas operaciones) |
| `imp_hog_hip` | MIR | Volumen de crédito hipotecario |
| `imp_hog_cons` | MIR | Volumen de crédito al consumo |
| `imp_emp` | MIR | Volumen de crédito empresarial |
| `ipc_gen_esp` | HICP | Inflación general (var. anual) |
| `ipc_sub_esp` | HICP | Inflación subyacente (var. anual) |
| `desemp_esp` | LFSI | Tasa de desempleo |

## Estructura del repositorio

```
macro-spain-ecb/
├── macro-analysis-esp.ipynb
├── app.py
├── .streamlit/
│   └── config.toml
├── environment.yml
├── requirements.txt
└── README.md
```

- **macro-analysis-esp.ipynb**: pipeline de datos, visualizaciones y análisis narrativo.
- **app.py**: app interactiva en Streamlit con los mismos gráficos y narrativa.
- **data/**: CSVs descargados de la API del BCE. Se genera automáticamente al ejecutar el notebook por primera vez.

## Cómo ejecutarlo

1. Clonar el repositorio:
    ```bash
    git clone https://github.com/inigoochoa/macro-spain-ecb.git
    ```

2. Instalar dependencias (dos opciones):

    **Con conda:**
    ```bash
    conda env create -f environment.yml
    conda activate macro-spain
    ```

    **Con pip:**
    ```bash
    pip install -r requirements.txt
    ```

3. Ejecutar el notebook:
    ```bash
    jupyter notebook macro-analysis-esp.ipynb
    ```

4. Ejecutar la app Streamlit:
    ```bash
    streamlit run app.py
    ```

La carpeta `data/` se crea automáticamente en la primera ejecución y los datos se descargan directamente de la API del BCE.
