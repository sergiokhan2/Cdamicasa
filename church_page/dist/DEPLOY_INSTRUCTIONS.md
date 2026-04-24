# Instrucciones para Subir a Azure

Has preparado con éxito el paquete para subir la página de **CDA Mi Casa** a Azure. Aquí tienes los pasos recomendados para realizar el despliegue:

## Opción 1: Azure Static Web Apps (Recomendado)

Esta es la forma más rápida y económica de alojar sitios estáticos:

1.  **Copiar la carpeta**: Copia la carpeta `dist` que acabamos de crear a tu Escritorio o Carpeta de Despliegue.
2.  **Azure Portal**: Ve a [portal.azure.com](https://portal.azure.com) y busca "Static Web Apps".
3.  **Crear**: Haz clic en "Create".
4.  **Configuración**:
    *   **Resource Group**: Selecciona uno existente o crea uno nuevo.
    *   **Name**: `cdamicasa-site` (o el que prefieras).
    *   **Plan**: Selecciona "Free" para uso personal.
    *   **Deployment Source**: Si no usas GitHub, selecciona **"Other"**.
5.  **Subir archivos**: Una vez creada la instancia, puedes usar la extensión de **Azure Static Web Apps** en VS Code o la herramienta **SWA CLI** para subir el contenido de la carpeta `dist`.

## Opción 2: Azure App Service (Windows/Linux)

Si prefieres usar un App Service tradicional:

1.  Usa un cliente FTP (como FileZilla) para conectarte a tu instancia de Azure.
2.  Sube **todo el contenido** dentro de la carpeta `dist` al directorio `site/wwwroot/`.

---

### Archivos Incluidos en `dist`:
- `index.html`: La página principal automatizada y optimizada.
- `css/`: Estilos unificados y responsivos.
- `assets/`: Todas las imágenes, videos y fuentes optimizadas.
- `staticwebapp.config.json`: Configuración de navegación, CSP y caché para Azure.

> [!TIP]
> Si deseas automatizar esto en el futuro, te recomiendo vincular esta carpeta a un repositorio de **GitHub**. Azure detectará cada cambio y actualizará la página automáticamente.
