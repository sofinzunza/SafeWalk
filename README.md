# 🚶‍♂️ SafeWalk - Sistema NaviCap

[![Flutter](https://img.shields.io/badge/Flutter-3.0%2B-02569B?logo=flutter)](https://flutter.dev/)
[![Firebase](https://img.shields.io/badge/Firebase-Enabled-FFCA28?logo=firebase)](https://firebase.google.com/)
[![Dart](https://img.shields.io/badge/Dart-3.0%2B-0175C2?logo=dart)](https://dart.dev/)
[![License](https://img.shields.io/badge/License-MIT-green)](LICENSE)

**SafeWalk** es la aplicación móvil complementaria del sistema **NaviCap**, un proyecto de asistencia tecnológica diseñado para incrementar la autonomía y seguridad de personas con discapacidad visual.

Esta aplicación se conecta vía **Bluetooth Low Energy (BLE)** a un gorro inteligente (basado en Raspberry Pi 4) para gestionar alertas de obstáculos detectados por visión artificial y proporcionar funciones vitales de emergencia.

---

## 📸 Capturas de Pantalla

| Inicio | Alertas | Conf. Avanzada | S.O.S |
|:---:|:---:|:---:|:---:|
| <img src="https://github.com/user-attachments/assets/149448dc-591e-4bbc-a3d6-a0c87662120e" width="180" alt="Inicio SafeWalk"> | <img src="https://github.com/user-attachments/assets/3257c991-6340-434f-9aa0-2eb77853e785" width="180" alt="Alertas SafeWalk"> | <img src="https://github.com/user-attachments/assets/f1f93593-949b-4970-be08-b665904c93e1" width="180" alt="Configuración SafeWalk"> | <img src="https://github.com/user-attachments/assets/144f4869-dff3-4b5f-a03b-0b12b430aa21" width="180" alt="SOS SafeWalk"> |

---

## 🚀 Características Principales

### 🔗 Conectividad y Control
* **Sincronización BLE:** Conexión automática con el gorro NaviCap para recibir telemetría en tiempo real.
* **Gestión de Hardware:** Monitoreo del estado de conexión y batería del dispositivo externo.

### 🛡️ Seguridad y Asistencia
* **Detección de Obstáculos:** Recepción de alertas auditivas (TTS) y hápticas (vibración) para objetos detectados por el gorro, tales como:
  * 🚦 Semáforos (Detección de estado Rojo/Verde).
  * 🚧 Escaleras, personas, vehículos, bicicletas y mobiliario urbano.
* **Botón S.O.S. Inteligente:** Envío inmediato de la ubicación GPS en tiempo real a contactos de emergencia predefinidos mediante **Firebase Cloud Messaging**.
* **Modo Offline:** Procesamiento de alertas críticas sin dependencia de internet (procesadas en el borde por el gorro).

### ♿ Accesibilidad y Personalización
* **100% Accesible:** Compatible nativamente con **TalkBack** (Android) y **VoiceOver** (iOS).
* **Configuración de Alertas:** Permite al usuario definir:
  * Distancia mínima y máxima de detección (ej. 1m - 4m).
  * Tipo de feedback (Voz, Vibración o Ambos).
  * Filtrado de tipos de obstáculos específicos.

---

## 🛠️ Arquitectura y Tecnologías

El sistema opera bajo una arquitectura basada en eventos, integrando los siguientes componentes:

* **Frontend:** [Flutter](https://flutter.dev/) & [Dart](https://dart.dev/).
* **Backend as a Service:** [Firebase](https://firebase.google.com/)
    * **Auth:** Gestión segura de sesiones (Google/Email).
    * **Firestore:** Almacenamiento de perfiles y contactos de emergencia.
    * **Cloud Functions & Messaging:** Lógica para alertas SOS.
* **Integraciones:**
    * **Google Maps API:** Visualización de ubicación para contactos de emergencia.
    * **Bluetooth Low Energy (BLE):** Protocolo GATT para comunicación de baja latencia con Raspberry Pi.
    * **Flutter TTS:** Motor de síntesis de voz para alertas.

---

## ⚙️ Instalación y Configuración

Sigue estos pasos para ejecutar el proyecto en tu entorno local:

### Prerrequisitos
* [Flutter SDK](https://docs.flutter.dev/get-started/install) instalado.
* Editor de código (VS Code / Android Studio).
* Dispositivo físico (recomendado para probar Bluetooth y GPS) o Emulador.

### Pasos

1.  **Clonar el repositorio:**
    ```bash
    git clone [https://github.com/sofinzunza/SafeWalk.git](https://github.com/sofinzunza/SafeWalk.git)
    cd SafeWalk
    ```

2.  **Instalar dependencias:**
    ```bash
    flutter pub get
    ```

3.  **Configuración de Firebase:**
    * Crea un proyecto en la [Consola de Firebase](https://console.firebase.google.com/).
    * Activa **Authentication** y **Firestore Database**.
    * **Android:** Descarga el `google-services.json` y colócalo en `android/app/`.
    * **iOS:** Descarga el `GoogleService-Info.plist` y colócalo en `ios/Runner/`.

4.  **Ejecutar la aplicación:**
    ```bash
    flutter run
    ```

---

## 👥 Equipo de Desarrollo

Este proyecto fue desarrollado como parte del **Proyecto de Título de Ingeniería en Informática** en **INACAP (2025)**.

* **Sofia Inzunza** - *Product Owner & Developer*
* **Amir Leiva** - *Development Team*
* **José Sandoval** - *Scrum Master*
* **Karla Castro** - *Development Team*

---

## 📄 Licencia

Este proyecto está bajo la Licencia MIT - ver el archivo [LICENSE](LICENSE) para más detalles.
