<div align="center">
	<h1>wp-vite-theme</h1>
	<p>Skill para crear temas de WordPress con Vite, JavaScript, Tailwind CSS y pnpm.</p>
	<p>
		<a href="https://github.com/carloscorpus/skill-wp-theme"><img src="https://img.shields.io/github/stars/carloscorpus/skill-wp-theme?style=flat-square&logo=github" alt="GitHub stars"></a>
		<a href="https://wordpress.org/"><img src="https://img.shields.io/badge/WordPress-Local%20WP-21759B?style=flat-square&logo=wordpress&logoColor=white" alt="WordPress Local WP"></a>
		<a href="https://vite.dev/"><img src="https://img.shields.io/badge/Vite-latest-646CFF?style=flat-square&logo=vite&logoColor=white" alt="Vite"></a>
		<a href="https://tailwindcss.com/"><img src="https://img.shields.io/badge/Tailwind%20CSS-latest-06B6D4?style=flat-square&logo=tailwindcss&logoColor=white" alt="Tailwind CSS"></a>
		<a href="https://pnpm.io/"><img src="https://img.shields.io/badge/pnpm-required-F69220?style=flat-square&logo=pnpm&logoColor=white" alt="pnpm"></a>
	</p>
</div>

Plantilla base para entornos locales con Local WP.

## Requisitos

- Node.js y pnpm instalados.
- Un sitio WordPress local.
- El tema debe crearse en `wp-content/themes/<slug>`.

## Instalación

Instalación para el proyecto actual:

```bash
pnpm dlx skills@latest add carloscorpus/skill-wp-theme
```

Instalación global para todos los proyectos:

```bash
pnpm dlx skills@latest add carloscorpus/skill-wp-theme -g
```

Usa `pnpm` porque el CLI lo declara en `devEngines`. Con npm/npx 11 puede aparecer `EBADDEVENGINES`.

## Uso

Desde la carpeta del tema, solicita al agente cualquiera de estas acciones:

- `inicia tema`
- `nuevo tema wp`
- `scaffold theme`
- `/wp-vite-theme`

El agente detectará el slug de la carpeta, solicitará los datos que falten y evitará sobrescribir archivos existentes sin confirmación.

## Qué genera

La estructura base incluye:

```text
style.css, functions.php, header.php, footer.php, index.php
inc/{setup,enqueue,cleanup}.php
src/css/input.css, src/js/main.js
vite.config.ts, pnpm-workspace.yaml, package.json
```

También configura el flujo de desarrollo y producción:

- `pnpm dev`: inicia Vite y crea el indicador `hot`.
- `pnpm build`: genera `dist/manifest.json` y los assets finales.
- Tailwind se carga mediante el plugin oficial de Vite.
- WordPress usa Vite en desarrollo y el manifest en producción.

## Despliegue

Ejecuta `pnpm build` con el servidor detenido. Publica `dist/` junto con los archivos PHP modificados. No publiques `hot`, `node_modules/`, `src/` ni los archivos de configuración.

## Licencia

La licencia de este repositorio está pendiente de definir. Hasta que se publique un archivo `LICENSE`, no se concede permiso explícito para redistribuirlo.
