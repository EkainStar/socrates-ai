---
title: Sócrates AI
emoji: 🏛️
colorFrom: yellow
colorTo: orange
---

# 🏛️ Sócrates AI — La Academia

Un chatbot filosófico basado en el método mayéutico de Sócrates. Disponible en **español e inglés**.

## ✨ Características

- 🔐 Autenticación por email/contraseña (Firebase)
- 🗝️ Hasta **20 claves API de Groq** por usuario con rotación automática
- 🧠 **User Belief Model (UBM)** — detecta nivel filosófico, contradicciones y tesis
- 🌍 **Bilingüe** — ES / EN
- ✨ Diseño inmersivo estilo Academia griega

## 🚀 Despliegue en GitHub Pages

1. Sube los archivos a tu repositorio de GitHub
2. Ve a **Settings → Pages**
3. Source: `Deploy from a branch` → `main` → `/ (root)`
4. Tu app estará en: `https://ekainstar.github.io/socrates-ai/`

## 🔧 Configuración Firebase necesaria

En la consola de Firebase:

### Authentication
- Habilitar **Email/Password**

### Firestore Rules
```
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /users/{userId} {
      allow read, write: if request.auth != null && request.auth.uid == userId;
    }
  }
}
```

### Authorized Domains
En Authentication → Settings → Authorized domains, añade tu dominio de GitHub Pages:
`ekainstar.github.io`

## 🗝️ Cómo obtener claves Groq gratuitas

1. Ve a [console.groq.com](https://console.groq.com)
2. Crea una cuenta gratuita
3. API Keys → Create API Key
4. Pega la clave en la app (⚙️ → Claves API)

Cada clave tiene **100,000 tokens/día** gratuitos. Con 20 claves tienes hasta **2,000,000 tokens/día**.

## 🛡️ Seguridad

- Las claves API se encriptan con XOR+base64 usando el UID del usuario antes de guardarse en Firestore
- Las reglas de Firestore garantizan que cada usuario solo accede a sus propios datos
- No hay backend: las llamadas a Groq se hacen directamente desde el navegador

## 📚 Stack técnico

- HTML/CSS/JS puro — sin frameworks
- Firebase (Auth + Firestore)
- Groq API (Llama 3.3 70B)
- GitHub Pages (hosting gratuito)