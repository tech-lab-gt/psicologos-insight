# Plataforma del Psicólogo · Insight — Guía de despliegue

**Versión:** 1.0 · **Fecha:** 1-may-2026

Cinco páginas HTML personalizadas (una por psicóloga) listas para subir a internet. Cada psicóloga recibe SU URL única; cero autenticación; abren en celular o computadora.

---

## 1. Lo que hay en esta carpeta

```
Plataforma_Psicologos/
├── index.html              ← página de bienvenida (solo para Emerson)
├── README.md               ← este archivo
├── libertad/
│   └── index.html          ← plataforma de Libertad
├── amanda/
│   └── index.html
├── krista/
│   └── index.html
├── astrid/
│   └── index.html
└── ana-gabriela/
    └── index.html
```

---

## 2. Antes de empezar — revisión local (10 min)

Antes de subir a internet, **abrir cada index.html en tu navegador local** para validar que se ve bien:

1. Doble click en `index.html` (la principal). Se abre Chrome/Edge.
2. Click en cada psicóloga, navegar las 5 pestañas (Resumen, Pacientes, Formación, Protocolo, Mis notas).
3. Probar que las flashcards del Protocolo navegan con los botones Anterior/Siguiente.
4. Si algo no se ve bien, decímelo y lo ajusto antes de subir.

---

## 3. Subir a GitHub Pages (15-20 min)

GitHub Pages es **gratis** y da una URL pública estable. Es la opción recomendada.

### 3.1 · Crear cuenta GitHub (si no tenés)

1. Ir a [github.com/signup](https://github.com/signup)
2. Crear cuenta con tu correo (recomiendo `psicologiaclinicagtt@gmail.com` para que quede en cuenta de la clínica).
3. Plan **gratis** alcanza.

### 3.2 · Crear el repositorio

1. Una vez con cuenta, click en `+` arriba a la derecha → `New repository`.
2. Nombre del repo: `psicologos-insight` (o el que prefieras).
3. Descripción: `Plataforma del psicólogo · Insight Psicología Clínica`.
4. Seleccionar: **Public** (es necesario para GitHub Pages gratis).
5. Marcar: **Add a README file**.
6. Click en `Create repository`.

### 3.3 · Subir los archivos

**Opción A — Drag & drop (más fácil):**

1. En el repo recién creado, click en `Add file` → `Upload files`.
2. Arrastrar TODA la carpeta `Plataforma_Psicologos` (incluyendo sus subcarpetas `libertad/`, `amanda/`, etc.) al área de upload.
3. Esperar a que suban todos.
4. En la parte de abajo, en "Commit changes":
   - Mensaje: `Plataforma del psicólogo v1.0`
   - Click en `Commit changes`.

**Opción B — Git desde la terminal (si te manejás):**

```bash
cd "C:\Users\vidal\Documents\Claude\Projects\Optimizacion clinica de psicologia insight\Plataforma_Psicologos"
git init
git add .
git commit -m "Plataforma del psicólogo v1.0"
git branch -M main
git remote add origin https://github.com/TUUSUARIO/psicologos-insight.git
git push -u origin main
```

### 3.4 · Activar GitHub Pages

1. En el repositorio, ir a `Settings` (arriba a la derecha).
2. En el menú lateral izquierdo, click en `Pages`.
3. En "Source", seleccionar: `Deploy from a branch`.
4. En "Branch", seleccionar: `main` y carpeta `/ (root)`.
5. Click en `Save`.
6. Esperar 1-2 minutos. Aparecerá un mensaje verde con la URL: algo como `https://TUUSUARIO.github.io/psicologos-insight/`.

### 3.5 · Las 5 URLs finales

Una vez activa GitHub Pages, las URLs serán:

```
Index general (solo para vos):
https://TUUSUARIO.github.io/psicologos-insight/

Por psicóloga:
https://TUUSUARIO.github.io/psicologos-insight/libertad/
https://TUUSUARIO.github.io/psicologos-insight/amanda/
https://TUUSUARIO.github.io/psicologos-insight/krista/
https://TUUSUARIO.github.io/psicologos-insight/astrid/
https://TUUSUARIO.github.io/psicologos-insight/ana-gabriela/
```

Reemplazá `TUUSUARIO` por tu nombre de usuario de GitHub.

---

## 4. Cómo se las pasás a las psicólogas

**Por WhatsApp (lo más simple):**

```
Hola [nombre], te paso el link de tu plataforma personal de Insight.

[URL]

Acá vas a ver:
- Tus números (retención, pacientes activos, ranking)
- Tu próxima reunión con Allan
- El protocolo de cierre obligatorio (con flashcards para repasar antes de cada S1)
- Espacio para tus notas

Lo abrís desde tu celular y queda guardado. Cualquier cosa me decís.

Gracias.
```

**Recomendación:** que Allan se las pase a cada una en su 1-a-1 inaugural. Así el momento del "te enseño cómo funciona" se vuelve parte del ritual de arranque del plan de formación.

---

## 5. Datos importantes a tener en cuenta

### 5.1 · Confidencialidad

Las URLs de GitHub Pages son **públicas**. Cualquiera con el link puede ver la página. Por eso:

- Los nombres de pacientes están **abreviados a iniciales** (M.G.C.J., R.J.C.V., etc.). NO publicar nombres completos.
- Compartir las URLs solo con la psicóloga correspondiente y con Allan.
- Si alguna psicóloga pide cambiar algo de su perfil, decimelo y ajusto.

### 5.2 · Las notas no persisten

Por ahora, el campo "Mis notas" de la pestaña final NO guarda lo que escriben (al recargar se borra). Está marcado en la página. Es limitación de la versión inicial.

**En la próxima iteración** (después de 2 semanas de uso, si validamos adopción): agregamos guardado real (puede ser con localStorage del navegador, o conectándolo a un Google Sheet por psicóloga).

### 5.3 · Datos del 18-26 abril

Los pacientes activos que se muestran son de la ventana 18-26 abril (S02 weekend + S03). Para Krista y Astrid, Floww no registró citas validadas en esa semana — la plataforma lo muestra honestamente con una nota pidiéndoles que confirmen a Gaby si fueron días libres o vacaciones.

### 5.4 · Actualización de datos

Esta versión tiene los datos **hardcodeados** (estáticos). Para actualizarla con datos nuevos cada mes, vamos a tener que regenerar los HTML (yo lo hago en 10 min cuando me digas).

**Próxima iteración propone:** cuando se valide la adopción, conectar la plataforma a un Google Sheet vivo que Gaby actualiza semanalmente. Así los números se mueven solos.

---

## 6. Plan de validación (próximas 2 semanas)

### Semana 1 (4-10 may)
- Allan muestra la plataforma a las 5 psicólogas en sus 1-a-1.
- Cada una usa su URL al menos 1 vez.
- Pedir feedback verbal: ¿qué les gusta? ¿qué no entienden? ¿qué cambiarían?

### Semana 2 (11-17 may)
- Tracking pasivo: ¿abren la plataforma sin que se les pida? (esto se mide con Google Analytics si lo agregamos, o pidiéndoles directamente).
- Feedback escrito: cada psicóloga llena el campo de "mis notas" con su versión del protocolo de cierre. Las que sí llenen → adoptaron.

### Decisión 18-may

Si **3 de las 5 lo abrieron al menos 2 veces sin que se les pida**, validamos demanda y pasamos a v2 (datos vivos + persistencia + escalado a los 25 psicólogos).

Si **menos de 3 lo usaron**, hay que entender por qué antes de invertir más.

---

## 7. Si algo no funciona

- **Si las URLs no cargan** después de activar GitHub Pages: esperá 5-10 minutos más. La primera vez tarda.
- **Si una psicóloga no puede abrir su URL en el celular**: probablemente WiFi o cache. Que lo pruebe con 4G o en otro navegador.
- **Si el navegador dice "No es seguro"**: GitHub Pages usa HTTPS por defecto. Si aparece advertencia, el link probablemente está mal escrito (revisar mayúsculas).

Cualquier otra cosa, decímelo y lo resuelvo.

---

*Documento generado el 1-may-2026. Para revisar plataforma o pedir cambios: avisar al asistente con qué psicóloga + qué cambiar.*
