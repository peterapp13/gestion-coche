# 🚗 Aplicación de Gestión de Vehículo

Una aplicación móvil moderna y profesional para gestionar todos los aspectos de tu vehículo: repostajes, recambios y mantenimiento.

## ✨ Características Principales

### 🔐 Autenticación
- Inicio de sesión con Google OAuth
- Datos sincronizados en la nube
- Sesiones seguras con tokens

### ⛽ Módulo de Repostajes
- Registro de repostajes con toda la información
- Cálculo automático de **KM Gastados** (diferencia con el registro anterior)
- Cálculo automático de **Consumo** (L/100km)
- Historial completo ordenado por kilometraje

**Campos:**
- Número de Factura
- Gasolinera
- Fecha
- KM Actuales
- Autonomía Antes/Después
- Litros
- Precio por Litro
- Total en Euros

### 📦 Módulo de Almacén
- Gestión de recambios comprados pero no instalados
- Estados: Pendiente / Instalado
- Información completa de cada pieza

**Campos:**
- Fecha de Compra
- Recambio
- Marca
- Coste en Euros
- Estado

### 🔧 Módulo de Taller
- Registro de trabajos de mantenimiento realizados
- Vinculación con piezas del almacén
- Actualización automática del estado de piezas a "Instalado"
- Opción de texto libre para recambios externos
- Notas técnicas para cada trabajo

**Campos:**
- Fecha de Montaje
- KM del vehículo
- Recambio instalado (del almacén o texto libre)
- Notas técnicas

### 📊 Exportación de Datos
- Exportación completa a CSV/Excel
- Tres secciones separadas (Repostajes, Almacén, Taller)
- Compatible con Google Sheets y Excel
- Descarga directa al dispositivo

## 🎨 Diseño

- **Modo Oscuro Profesional**: Interfaz elegante y moderna
- **Botones Grandes**: Optimizados para uso rápido en taller
- **Responsive**: Funciona perfectamente en iPhone y iPad
- **Navegación por Tabs**: Acceso rápido a todos los módulos

## 🛠 Tecnologías Utilizadas

### Frontend
- **Expo / React Native**: Framework móvil multiplataforma
- **Expo Router**: Navegación file-based
- **TypeScript**: Tipado estático para mayor confiabilidad
- **React Native Components**: UI nativa

### Backend
- **FastAPI**: Framework web moderno y rápido
- **MongoDB**: Base de datos NoSQL
- **Motor**: Driver asíncrono de MongoDB
- **HTTPX**: Cliente HTTP para OAuth

### Autenticación
- **Emergent Google OAuth**: Sistema de autenticación seguro
- **Session Tokens**: Tokens de sesión con 7 días de validez
- **Cookies HTTPOnly**: Almacenamiento seguro de sesiones

## 📱 Capturas de Pantalla

**Login:**
- Pantalla de bienvenida con inicio de sesión de Google

**Módulos principales:**
- Repostajes: Historial de combustible con cálculos automáticos
- Almacén: Gestión de piezas con estados
- Taller: Registro de mantenimientos con notas
- Perfil: Información del usuario y exportación

## 🚀 Cómo Usar la Aplicación

### 1. Inicio de Sesión
1. Abre la aplicación
2. Toca "Continuar con Google"
3. Selecciona tu cuenta de Google
4. ¡Listo! Tus datos están sincronizados

### 2. Registrar un Repostaje
1. Ve a la tab "Repostajes"
2. Toca el botón "+" flotante
3. Completa los datos del repostaje
4. La app calculará automáticamente:
   - KM Gastados desde el último repostaje
   - Consumo en L/100km

### 3. Añadir Recambios al Almacén
1. Ve a la tab "Almacén"
2. Toca el botón "+"
3. Registra la pieza comprada
4. Por defecto quedará como "Pendiente"

### 4. Registrar Trabajo de Taller
1. Ve a la tab "Taller"
2. Toca el botón "+"
3. Elige entre:
   - **Del Almacén**: Selecciona una pieza pendiente (se marcará automáticamente como "Instalado")
   - **Escribir Libre**: Escribe el nombre del recambio manualmente
4. Añade notas técnicas si lo deseas

### 5. Exportar tus Datos
1. Ve a la tab "Perfil"
2. Toca "Exportar a CSV/Excel"
3. Comparte o guarda el archivo
4. Abre en Google Sheets o Excel

## 🔒 Seguridad

- Autenticación OAuth con Google
- Sesiones seguras con cookies HTTPOnly
- Datos encriptados en tránsito (HTTPS)
- Base de datos con validación de usuarios
- Aislamiento de datos por usuario

## 📊 API Endpoints

### Autenticación
- `POST /api/auth/session` - Intercambiar session_id por session_token
- `GET /api/auth/me` - Obtener información del usuario actual
- `POST /api/auth/logout` - Cerrar sesión

### Repostajes
- `GET /api/repostajes` - Listar todos los repostajes
- `POST /api/repostajes` - Crear nuevo repostaje
- `DELETE /api/repostajes/{id}` - Eliminar repostaje

### Almacén
- `GET /api/almacen` - Listar todos los recambios
- `POST /api/almacen` - Crear nuevo recambio
- `DELETE /api/almacen/{id}` - Eliminar recambio

### Taller
- `GET /api/taller` - Listar todos los trabajos
- `POST /api/taller` - Crear nuevo trabajo (actualiza almacén automáticamente)
- `DELETE /api/taller/{id}` - Eliminar trabajo

### Exportación
- `GET /api/export` - Exportar todos los datos en formato JSON

## 🎯 Funcionalidades Avanzadas

### Cálculos Automáticos
- **KM Gastados**: Resta automáticamente el KM del registro anterior
- **Consumo**: Calcula (Litros / KM Gastados) × 100

### Actualización Inteligente
- Cuando instalas una pieza del almacén, su estado cambia automáticamente a "Instalado"

### Gestión de Datos
- Pull-to-refresh en todas las listas
- Confirmación antes de eliminar registros
- Feedback visual en todas las acciones

## 🌐 URLs de la Aplicación

- **Frontend**: https://car-maintenance-78.preview.emergentagent.com
- **Backend API**: https://car-maintenance-78.preview.emergentagent.com/api

## 📝 Notas Importantes

1. **Sincronización**: Todos los datos se guardan automáticamente en la nube
2. **Offline**: La app requiere conexión a internet para funcionar
3. **Seguridad**: Nunca compartas tu session token con nadie
4. **Exportación**: Los archivos CSV son compatibles con Excel y Google Sheets
5. **Privacidad**: Solo tú puedes ver tus datos

## 🎨 Paleta de Colores

- **Fondo Principal**: #0A0A0A (Negro profundo)
- **Fondo Secundario**: #1A1A1A (Gris oscuro)
- **Bordes**: #2A2A2A (Gris medio)
- **Texto Principal**: #FFFFFF (Blanco)
- **Texto Secundario**: #9CA3AF (Gris claro)
- **Acento Primario**: #4285F4 (Azul Google)
- **Éxito**: #10B981 (Verde)
- **Advertencia**: #F59E0B (Naranja)
- **Error**: #EF4444 (Rojo)

## 🚀 Próximas Mejoras Sugeridas

- [ ] Gráficos de consumo a lo largo del tiempo
- [ ] Recordatorios de mantenimiento
- [ ] Múltiples vehículos por usuario
- [ ] Fotos de facturas
- [ ] Búsqueda y filtros avanzados
- [ ] Estadísticas de gastos mensuales/anuales
- [ ] Modo offline con sincronización automática
- [ ] Notificaciones push para recordatorios

## 📄 Licencia

Aplicación desarrollada para uso personal en la gestión de vehículos.

---

**¡Disfruta gestionando tu vehículo de forma profesional! 🚗💨**
