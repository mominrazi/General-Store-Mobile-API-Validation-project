# 📱 General Store Mobile & API Validation Suite (Appium, REST Assured, Postman)

A unified Quality Assurance automation suite combining **Mobile UI Automation** and **RESTful API Validation**. Built using **Appium**, **Java**, **TestNG**, **REST Assured**, and **Postman**, this project automates native Android e-commerce workflows and touch gestures on the *General Store* mobile application while validating backend API contracts, authentication tokens, JSON schemas, and CRUD operations.

---

## 🚀 Key Features

### 📲 Mobile Automation (Appium & UiAutomator2)
* **Native App End-to-End Flows:** Automates country selection, user profile entry, product catalog browsing, cart calculations, and checkout validation on the **General Store** Android APK.
* **Advanced Mobile Touch Gestures:** Implements W3C Actions and `UiScrollable` / `JavascriptExecutor` gestures including **long press**, **scroll-to-text**, **swipe**, and **tap** interactions.
* **Hybrid Context Switching:** Handles seamless transitions between **NATIVE_APP** and **WEBVIEW** contexts during checkout flows.
* **Emulator & Real Device Execution:** Configured with dynamic `UiAutomator2Options` for execution across Android Virtual Devices (AVDs) and physical devices via ADB.

### 🌐 API Validation (REST Assured & Postman)
* **End-to-End CRUD Testing:** Automates `GET`, `POST`, `PUT`, and `DELETE` requests to verify data persistence, status codes (`200`, `201`, `204`, `400`, `401`), and response payloads.
* **Authentication & Token Chaining:** Extracts Bearer/JWT tokens dynamically from authentication endpoints and injects them into subsequent protected API requests.
* **JSON Schema & Payload Validation:** Enforces strict contract compliance using REST Assured `JsonSchemaValidator` and TestNG assertions.
* **Structured Postman Collections:** Includes modular Postman collections with environment variables, pre-request scripts, and automated JavaScript test assertions for CLI execution via **Newman**.

---

## 🛠️ Tech Stack

* **Language:** Java (JDK 11+)
* **Mobile Automation:** Appium 2.x (`io.appium:java-client`), UiAutomator2 Driver, Android SDK / ADB
* **API Automation:** REST Assured (`io.rest-assured`), JSON Schema Validator
* **API Manual & Collection Runner:** Postman & Newman CLI
* **Test Framework:** TestNG
* **Build & Dependency Management:** Maven

---

## 📂 Project Structure

```text
api-project/
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   ├── mobile/pages/        # Mobile Page Object classes (FormPage, ProductCatalogue, CartPage)
│   │   │   ├── mobile/utils/        # Appium gesture utilities (scroll, longPress, swipe)
│   │   │   └── api/utils/           # REST Assured RequestSpecBuilder & token helpers
│   │   └── resources/
│   │       ├── General-Store.apk    # Android application binary under test
│   │       └── schemas/             # JSON Schema definitions for contract validation
│   └── test/
│       └── java/
│           ├── mobile/tests/        # Appium TestNG mobile gesture & checkout suites
│           └── api/tests/           # REST Assured CRUD, auth & schema test suites
├── postman/
│   ├── GeneralStore_API.postman_collection.json   # Exported Postman collection
│   └── QA_Environment.postman_environment.json    # Postman environment variables
├── testng.xml                       # Unified TestNG execution suite
└── pom.xml                          # Maven dependencies (Appium, REST Assured, TestNG)
```

---

## ⚙️ Prerequisites & Setup

### 1. Prerequisites
* **Java Development Kit (JDK)** 11 or higher
* **Maven** installed
* **Node.js & Appium Server 2.x** (`npm install -g appium` and `appium driver install uiautomator2`)
* **Android Studio / Android SDK** with an active Emulator or USB-debugging enabled real device
* **Postman** (or **Newman** CLI: `npm install -g newman`)

### 2. Clone the Repository
```bash
git clone https://github.com
cd api-project
```
*(Note: Update the repository slug in the URL above if you host this under a separate repository name.)*

### 3. Run Mobile Automation Tests
1. Start the Android Emulator or connect a physical device (`adb devices`).
2. Start the local Appium server:
   ```bash
   appium
   ```
3. Execute the mobile test suite:
   ```bash
   mvn test -Dtest=MobileStoreTest
   ```

### 4. Run API Automation Tests
Execute the REST Assured test suite via Maven:
```bash
mvn test -Dtest=ApiValidationTest
```
Or run the Postman collection via Newman CLI:
```bash
newman run postman/GeneralStore_API.postman_collection.json -e postman/QA_Environment.postman_environment.json
```

---

## 👤 Author

**Momin Razi**
* GitHub: [@mominrazi](https://github.com)
* LinkedIn: [Momin Razi](https://linkedin.com)
