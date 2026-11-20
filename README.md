# JDET Capital · Estrategia y parrilla de contenido

Página interactiva con el brief de marca, la estrategia de marketing, el plan de 90 días y el calendario de publicaciones (23 nov – 20 dic 2026).

## Qué se guarda
- Casillas del checklist de redes y de las tres fases del plan.
- Estado de cada publicación (Pendiente, En diseño, Programado, Publicado).
- Notas por publicación.

Sin configurar Firebase, todo se guarda solo en el navegador de quien lo usa.

## Conectar la base de datos (Firebase)
1. En https://console.firebase.google.com cree un proyecto.
2. En **Compilación > Firestore Database**, cree la base de datos.
3. En **Configuración del proyecto > Tus apps**, añada una app web y copie el bloque `firebaseConfig`.
4. Péguelo en `index.html`, donde dice `CONFIGURACIÓN DE FIREBASE`.
5. En **Firestore > Reglas**, use:

```
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /jdet/estado { allow read, write: if true; }
  }
}
```

Con esta regla, cualquier persona que tenga el enlace puede marcar casillas. Si se necesita restringir, hay que añadir inicio de sesión.

## Publicar
En GitHub: **Settings > Pages > Deploy from a branch > main / root**.
