# 🛒 Proyecto End-to-End: Microsoft Fabric & E-Commerce

Bienvenido al repositorio de datos fuente para el proyecto final del curso de Ingeniería de Datos con **Microsoft Fabric**. 

Este repositorio actúa como nuestro **Sistema de Origen (Source System)** simulando un entorno de extracción externa. Contiene el dataset público de e-commerce brasileño "Olist".

## 📁 Contenido de los Datos
En la ruta `data/raw/` encontrarás los 9 archivos en formato CSV que conforman el modelo transaccional del negocio:

1. `olist_customers_dataset.csv`: Datos demográficos de clientes.
2. `olist_geolocation_dataset.csv`: Coordenadas y códigos postales.
3. `olist_order_items_dataset.csv`: Detalle de productos por pedido.
4. `olist_order_payments_dataset.csv`: Métodos de pago y montos.
5. `olist_order_reviews_dataset.csv`: Reseñas de los compradores.
6. `olist_orders_dataset.csv`: Cabeceras de los pedidos y fechas (Hechos principales).
7. `olist_products_dataset.csv`: Catálogo de productos.
8. `olist_sellers_dataset.csv`: Información de los vendedores.
9. `product_category_name_translation.csv`: Traducción de categorías al inglés.

---

## 🚀 Instrucciones para la Ingesta (Fase Bronze)

Para la fase de ingesta de datos hacia nuestro Lakehouse en Microsoft Fabric, utilizaremos **Data Factory Pipelines** con el conector **HTTP**.

### ⚠️ Importante: Cómo obtener la URL correcta
Data Factory no puede leer la página web visual de GitHub. Necesita el archivo plano. Para obtener la URL de descarga directa, debes hacer lo siguiente:

1. Navega dentro de la carpeta `data/raw/` en este repositorio.
2. Haz clic en cualquiera de los archivos CSV (por ejemplo, `olist_orders_dataset.csv`).
3. En la esquina superior derecha del cuadro de código, haz clic en el botón **`Raw`** (Crudo).
4. Se abrirá una nueva pestaña en el navegador con texto plano. **Copia esa URL**.

La URL base (Base URL) que debes configurar en tu conexión HTTP en Fabric debe verse similar a esto:
`https://raw.githubusercontent.com/TuUsuario/TuRepositorio/main/data/raw/`

*(Nota: Dejamos la URL base hasta la carpeta `raw/`. El nombre específico del archivo se pasará dinámicamente usando la actividad ForEach y la expresión `@item()` en el pipeline).*

---
*Dataset original provisto por Olist en Kaggle bajo licencia pública.*
