# Instalar tu presentación de GitHub

## Qué se ha preparado

- Cabecera azul con tu nombre y detalles de código, música, IA y ajedrez.
- Presentación en español, tecnologías y seis proyectos con enlaces.
- Enlace al portafolio y a su CV descargable.
- Tarjetas de estadísticas públicas y distribución de lenguajes generadas por GitHub Actions.
- Una sección breve de música, ajedrez, creatividad, fe y servicio.

Este repositorio es la presentación de tu perfil de GitHub. Tu página web continúa en su repositorio actual y conserva su dirección.

## 1. Crear el repositorio especial

Abre https://github.com/new y elige estos valores:

- Owner: enzoaldhairfuentesapaza
- Repository name: enzoaldhairfuentesapaza
- Description: Perfil de Enzo Fuentes · Desarrollo de software, IA y proyectos.
- Visibility: Public
- Add README: desactivado
- Sin plantilla de .gitignore ni licencia inicial.

Pulsa Create repository. Debe quedar en:
https://github.com/enzoaldhairfuentesapaza/enzoaldhairfuentesapaza

El nombre coincide exactamente con tu usuario. GitHub mostrará el README en tu perfil automáticamente cuando lo subas; no debes configurar GitHub Pages.

## 2. Preparar la carpeta en Windows

Crea D:\ENZO\PerfilGitHub y coloca allí Perfil_GitHub_Enzo_Fuentes.zip.

Abre PowerShell y ejecuta:

~~~powershell
Set-Location "D:\ENZO\PerfilGitHub"
Expand-Archive -LiteralPath ".\Perfil_GitHub_Enzo_Fuentes.zip" -DestinationPath "." -Force
Get-ChildItem -Force
~~~

README.md, assets, profile y .github deben quedar directamente en D:\ENZO\PerfilGitHub, sin una carpeta adicional que los contenga. No realices estos pasos en D:\ENZO\CV: esa carpeta corresponde a tu página web.

## 3. Subir los archivos

Ejecuta estos comandos desde D:\ENZO\PerfilGitHub. El repositorio remoto del paso 1 debe estar vacío.

~~~powershell
Set-Location "D:\ENZO\PerfilGitHub"
git init -b main
git remote add origin https://github.com/enzoaldhairfuentesapaza/enzoaldhairfuentesapaza.git
git add -A
git status
git commit -m "Personaliza perfil con presentación y tarjetas de actividad"
git push -u origin main
~~~

Ejecuta los comandos en orden. Si alguno falla, detente en ese paso. El ZIP se excluye automáticamente mediante .gitignore.

## 4. Activar las tarjetas reales

La subida de README.md y del workflow inicia la generación. Abre:

https://github.com/enzoaldhairfuentesapaza/enzoaldhairfuentesapaza/actions

Debe aparecer Actualizar tarjetas del perfil. Espera a que finalice correctamente.

Si no se inició, elige ese workflow en la izquierda y pulsa Run workflow sobre main. El workflow usa GITHUB_TOKEN, proporcionado por GitHub; no debes crear un token personal para esta configuración de estadísticas públicas.

Si GitHub pide habilitar Actions para este repositorio, habilítalo. Si la política de tu cuenta impide escribir con GitHub Actions, revisa Settings → Actions → General → Workflow permissions. El workflow solicita contents: write para guardar las imágenes en este mismo repositorio.

Antes de la primera ejecución, las tarjetas incluyen mensajes de espera, sin cifras inventadas. Tras la ejecución se reemplazan por las tarjetas con los datos de GitHub. El workflow está preparado para volver a ejecutarse diariamente a las 06:17 de Perú; GitHub puede retrasar las ejecuciones programadas. En repositorios públicos sin actividad, GitHub puede desactivar las programaciones tras 60 días; se pueden reactivar desde Actions.

La ejecución completa solo podrá verificarse cuando el repositorio exista y se ejecute el workflow en tu cuenta.

## 5. Completar los datos del perfil

En https://github.com/settings/profile:

- Name: Enzo Aldhair Fuentes Apaza
- Bio: Estudiante de Ciencia de la Computación @ UCSP | Desarrollo web e IA explicable | Soluciones adaptadas al dominio | Arequipa, Perú
- Location: Arequipa, Perú
- Website: https://enzoaldhairfuentesapaza.github.io/

Name es tu nombre visible. Mantén tu Username actual para conservar las direcciones de tu cuenta y de tu página.

En tu perfil, pulsa Customize your pins y destaca estos seis repositorios:

1. DH-DM-Maquinarias-Web
2. Sistema-almacenamiento-inteligente
3. Implementacion-de-metodos-post-hoc-de-interpretabilidad-en-la-segmentacion-3D-de-tumores-cerebrales
4. Repositorio-de-Planes-de-Trabajo-CEDHI
5. DistributedNeuralNetUDP
6. LPGuitarHero

## Personalización futura

- Edita README.md para ajustar el contenido.
- assets/banner.svg y assets/technologies.svg son archivos vectoriales editables.
- .github/workflows/profile-stats.yml configura las tarjetas y la frecuencia.
- profile/stats.svg y profile/top-langs.svg son los archivos que actualiza GitHub Actions.
- Los porcentajes de lenguajes describen código detectado en repositorios; no equivalen al nivel de habilidad.
- Puedes retirar esta guía del repositorio después de instalarlo.

## Referencias

- README de perfil: https://docs.github.com/en/account-and-profile/how-tos/profile-customization/managing-your-profile-readme
- Tarjetas y configuración: https://github.com/stats-organization/github-readme-stats-action
- Repositorios fijados: https://docs.github.com/en/account-and-profile/how-tos/profile-customization/pinning-items-to-your-profile
