Readme · MD
Copiar

#  NovaTech — Landing Page
 
Landing page completa desarrollada como práctica colaborativa de Git y GitHub Pages.
 
## 🌐 Enlace publicado
 
> [https://TU_USUARIO.github.io/novatech-landing](https://TU_USUARIO.github.io/novatech-landing)
 
*(Reemplaza `TU_USUARIO` con tu usuario de GitHub)*
 
---
 
##  Equipo
 
| Integrante | Rama | Sección |
|---|---|---|
| Ana Martínez | `ana/menu-principal` | Navbar + Hero Slider |
| Luis Rodríguez | `luis/servicios-equipo` | Servicios + Equipo + Misión + Contacto + Footer |
 
---
 
##  Estructura del proyecto
 
```
novatech-landing/
├── index.html     # Estructura HTML completa
├── style.css      # Estilos y diseño
└── README.md      # Este archivo
```
 
---
 
##  Flujo de trabajo Git
 
### 1. Clonar el repositorio
```bash
git clone https://github.com/TU_USUARIO/novatech-landing.git
cd novatech-landing
```
 
### 2. Configurar identidad local
```bash
git config user.name "Tu Nombre"
git config user.email "tu@correo.com"
```
 
### 3. Verificar rama principal
```bash
git branch
# → * main
```
 
### 4. Crear rama personal desde main actualizado
```bash
git checkout main
git pull origin main
git checkout -b ana/menu-principal
```
 
### 5. Trabajar y hacer commits descriptivos
```bash
# Después de editar archivos:
git add .
git commit -m "feat: agrega navbar responsivo con menú móvil"
git commit -m "feat: hero con animaciones y tarjetas flotantes"
git commit -m "fix: corrige alineación en pantallas pequeñas"
```
 
### 6. Subir rama y abrir Pull Request
```bash
git push origin ana/menu-principal
```
Luego en GitHub: **Compare & pull request → main** → asignar revisor.
 
### 7. Revisión y merge
El revisor aprueba el PR. El autor hace merge a `main`.
 
### 8. Publicar con GitHub Pages
`Settings → Pages → Branch: main → / (root) → Save`
 
---
 
##  Historial de Pull Requests
 
| PR | Rama | Revisor | Estado |
|---|---|---|---|
| #1 | `ana/menu-principal` | Luis Rodríguez | ✅ Merged |
| #2 | `luis/servicios-equipo` | Ana Martínez | ✅ Merged |
 
---
 
##  Tecnologías
 
- HTML5 semántico
- CSS3 (variables, grid, flexbox, animaciones)
- JavaScript vanilla (Intersection Observer, eventos)
- Google Fonts: Syne + DM Sans
- GitHub Pages para publicación
---
 
##  Secciones de la landing page
 
1. **Navbar** — Menú de navegación fijo con efecto scroll y versión móvil
2. **Hero** — Slider principal con animaciones y estadísticas
3. **Servicios** — Cuatro cards con servicios ofrecidos
4. **Visión y Misión** — Valores y propósito de la empresa
5. **Equipo** — Perfiles del equipo con avatares
6. **Contacto** — Formulario con validación
7. **Footer** — Pie de página con enlaces y redes sociales
---

const campo = InputValidator(config);

campo.getValue()        // → string  — valor actual
campo.isValid()         // → boolean — estado de validez
campo.setValue('texto') // → void    — establece valor y revalida
campo.validate()        // → boolean — fuerza validación y muestra errores
campo.reset()           // → void    — limpia todo

<div id="mi-email"></div>
<script src="../input-validator/index.js"></script>
<script>
  const email = InputValidator({
    containerId: 'mi-email',
    type: 'email',
    label: 'Correo electrónico',
    placeholder: 'tu@correo.com',
    required: true,
    onChange: (value, isValid) => console.log(value, isValid),
  });
</script>

const pass = InputValidator({
  containerId: 'mi-pass',
  type: 'password',
  label: 'Contraseña',
  required: true,
  minLength: 8,
  onValidate: (isValid, errors) => {
    if (!isValid) console.warn('Errores:', errors);
  },
});

const user = InputValidator({
  containerId: 'mi-usuario',
  type: 'text',
  label: 'Nombre de usuario',
  required: true,
  minLength: 3,
  maxLength: 20,
  pattern: /^[a-z0-9_]+$/,
  patternMsg: 'Solo letras minúsculas, números y _',
});

document.getElementById('btn-enviar').addEventListener('click', () => {
  if (email.validate() && pass.validate()) {
    console.log('Formulario válido ✓');
  }
});
