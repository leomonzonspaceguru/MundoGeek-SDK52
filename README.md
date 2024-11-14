# MundoGeek-SDK52


## 🚀 Actualizaciones Principales
- Migración a Expo SDK 52
- Implementación de la Nueva Arquitectura de React Native
- Actualización de expo-sqlite (eliminación de legacy)

## 🛠 Proceso de Actualización a SDK 52

1. **Actualizar Expo**
    ```
    npx expo install expo@^52.0.0 --fix
    ```
2. **Verificar dependencias**
    ```
    npx expo-doctor
    npx expo install --check
    ```

3. **Configurar Nueva Arquitectura**
Actualizar `app.json`:

    ```
    {
        "expo": {
           ...
           "newArchEnabled": true
       }
    }
    ```

4. **Actualización de Base de Datos**
Migración de expo-sqlite/legacy a expo-sqlite:


 ### Antes (legacy)

    import * as SQLite from 'expo-sqlite/legacy';

 ### Ahora
 
    import * as SQLite from 'expo-sqlite';

### Nuevos Métodos SQLite

Abrir base de datos
 ```
const db = SQLite.openDatabaseSync("mundogeek.db");
 ```
Ejecutar consultas
 ```
await db.execAsync(CREATE TABLE IF NOT EXISTS ...);
 ```
  ```
await db.runAsync('INSERT INTO ...', [params]);
 ```
  ```
await db.getAllAsync('SELECT FROM ...');
 ```

## 📚 Documentación Adicional
- [Expo SDK 52 Documentación](https://expo.dev/changelog/2024/11-12-sdk-52)
- [Expo-sqlite Documentación](https://docs.expo.dev/versions/latest/sdk/sqlite/)
