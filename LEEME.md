# Inventario CSIRC UGR — App de escritorio

Esta carpeta convierte tu herramienta HTML en una aplicación de escritorio
real (Electron), con un instalador `.exe` que puedes llevar en un pendrive
e instalar en cualquier PC con Windows, sin necesidad de tener el navegador
abierto ni depender de un servidor.

No puedo compilar el `.exe` directamente aquí (mi entorno bloquea la
descarga del binario de Electron), así que te dejo **dos formas** de
conseguirlo, elige la que te resulte más cómoda.

---

## Opción A (recomendada): que GitHub lo compile por ti — gratis, 5 minutos

No necesitas instalar nada en tu PC.

1. Crea un repositorio nuevo en GitHub (puede ser privado): https://github.com/new
2. Sube TODO el contenido de esta carpeta a ese repositorio (arrastrando los
   archivos desde la web de GitHub, o con `git push` si usas Git).
3. Ve a la pestaña **Actions** del repositorio. Se lanzará solo el flujo
   "Compilar instalador Windows" (o pulsa **Run workflow** si no se lanza
   solo).
4. Espera 2-3 minutos a que termine (verás un ✅ verde).
5. Entra en esa ejecución y descarga el artefacto
   **Inventario-CSIRC-UGR-Windows**: es un .zip que contiene el instalador
   `Inventario CSIRC UGR Setup 1.0.0.exe`.
6. Ese `.exe` ya es tu instalador definitivo: cópialo a un pendrive y
   ejecútalo en cualquier PC con Windows. Crea acceso directo en escritorio
   y en el menú inicio, y se puede desinstalar desde "Aplicaciones".

Cada vez que cambies `index.html` (tu inventario), vuelve a subir el
archivo al repositorio y GitHub generará un `.exe` nuevo automáticamente.

## Opción B: compilarlo tú mismo en un Windows con Node.js

1. Instala Node.js (LTS) desde https://nodejs.org si no lo tienes.
2. Copia esta carpeta completa a ese PC.
3. Abre una terminal (CMD o PowerShell) dentro de la carpeta y ejecuta:
   ```
   npm install
   npm run dist
   ```
4. Cuando termine, el instalador estará en `dist\Inventario CSIRC UGR Setup 1.0.0.exe`.
5. Copia ese único archivo `.exe` donde quieras: es autocontenido y sirve
   para instalar la app en cualquier otro PC con Windows (no hace falta
   repetir estos pasos en cada equipo, solo en el que lo compila).

---

## Qué instala la app

- Se ejecuta como programa de escritorio normal (ventana propia, icono en
  granate UGR, acceso directo en escritorio/menú inicio).
- Los datos se guardan igual que ahora (localStorage), por PC. Para
  sincronizar entre equipos sigue usando la exportación/importación JSON
  que ya tiene la herramienta.
- El menú (Ver → recargar, zoom, etc.) está oculto por defecto; se despliega
  pulsando `Alt`.

## Actualizar la app más adelante

Si vuelves a pedirme cambios en el HTML, solo tienes que sustituir el
`index.html` de esta carpeta por el nuevo y repetir la Opción A o B para
generar un instalador actualizado.
