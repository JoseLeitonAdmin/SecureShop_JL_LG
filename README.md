# SecureShop_JL_LG

# Taller 1: Análisis de Seguridad y Activos - SecureShop

## Activos de SecureShop

1. Datos personales de clientes
2. Hashes de contraseñas
3. Historial de pedidos
4. Información de pago y facturación
5. Catálogo de productos
6. Tokens de sesión y JWT
7. Claves criptográficas y secretos
8. Cuentas con privilegios administrativos
9. API Gateway
10. Código fuente y repositorio
11. Respaldos de bases de datos
12. Imágenes de contenedores y dependencias
13. Logs y registros de auditoría

## Clasificación de Activos
Clasificación de cada activo según las categorías: **información**, **software**, **servicio**, **infraestructura**, **datos**.

| # | Activo | Tipo |
|---|---|---|
| 1 | Datos personales de clientes | datos |
| 2 | Hashes de contraseñas | datos |
| 3 | Historial de pedidos | datos |
| 4 | Información de pago y facturación | información |
| 5 | Catálogo de productos | datos |
| 6 | Tokens de sesión y JWT | datos |
| 7 | Claves criptográficas y secretos | información |
| 8 | Cuentas con privilegios administrativos | servicio |
| 9 | API Gateway | software |
| 10 | Código fuente y repositorio | software |
| 11 | Respaldos de bases de datos | infraestructura |
| 12 | Imágenes de contenedores y dependencias | software |
| 13 | Logs y registros de auditoría | información |

---

## Análisis de Consecuencias (Acceso, Modificación o Indisponibilidad)
| Activo | Tipo | Consecuencia de ser accedido, modificado o quedar indisponible |
|---|---|---|
| **Datos personales de clientes** | datos | **Accedido:** Violación de privacidad (PII), pérdida de reputación, riesgo de phishing dirigido y sanciones legales.<br>**Modificado:** Envíos a direcciones erróneas y perfiles inconsistentes.<br>**Indisponible:** Imposibilidad de despachar pedidos o validar la identidad de los clientes. |
| **Hashes de contraseñas** | datos | **Accedido:** Ataques de fuerza bruta offline o diccionario para descifrar credenciales y tomar el control de cuentas.<br>**Modificado:** Bloqueo masivo del inicio de sesión de usuarios legítimos.<br>**Indisponible:** Fallo total en el proceso de autenticación en User Service. |
| **Historial de pedidos** | datos | **Accedido:** Exposición de hábitos de consumo de los clientes y montos transaccionados.<br>**Modificado:** Alteración en el estado de despachos, anulación no autorizada de compras o duplicidad de entregas.<br>**Indisponible:** Imposibilidad de gestionar devoluciones, garantías o consultas de compras pasadas. |
| **Información de pago y facturación** | información | **Accedido:** Fraude financiero, robo de datos bancarios/fiscales y severas multas regulatorias.<br>**Modificado:** Desvío de fondos o emisión de comprobantes fiscales con datos adulterados.<br>**Indisponible:** Imposibilidad de facturar y conciliar los pagos de las órdenes realizadas. |
| **Catálogo de productos** | datos | **Accedido:** Fuga de estrategias de precios o costos antes de lanzamientos.<br>**Modificado:** Manipulación maliciosa de precios (ej. productos a $0), cambio de stock o descripciones falsas.<br>**Indisponible:** Los clientes no pueden ver productos ni agregar ítems al carrito, paralizando las ventas. |
| **Tokens de sesión y JWT** | datos | **Accedido:** Secuestro de sesión activa (Account Takeover) saltándose la autenticación.<br>**Modificado:** Escalación de privilegios si el token no está correctamente firmado.<br>**Indisponible:** Cierre forzado de sesiones y fallos continuos de autorización hacia los microservicios. |
| **Claves criptográficas y secretos** | información | **Accedido:** Compromiso total de la confidencialidad del sistema; el atacante puede firmar JWTs falsos y desencriptar datos en reposo.<br>**Modificado:** Corrupción criptográfica que impide descifrar datos existentes o validar firmas.<br>**Indisponible:** Fallo generalizado en servicios que requieran cifrado o validación de tokens. |
| **Cuentas con privilegios administrativos** | servicio | **Accedido:** Acceso total al panel de administración y control completo de la plataforma.<br>**Modificado:** Alteración de roles, permisos y políticas de acceso.<br>**Indisponible:** Incapacidad operativa para gestionar incidentes, soporte o dar mantenimiento al sistema. |
| **API Gateway** | software | **Accedido:** Intercepción de solicitudes entrantes y reconfiguración de endpoints.<br>**Modificado:** Enrutamiento del tráfico de clientes hacia servidores atacantes (Man-in-the-Middle).<br>**Indisponible:** Caída absoluta de SecureShop, ya que ningún cliente externo podrá comunicarse con los microservicios. |
| **Código fuente y repositorio** | software | **Accedido:** Detección de vulnerabilidades de día cero y exposición de lógica interna del negocio.<br>**Modificado:** Inyección de backdoors o código malicioso directamente en el flujo de integración continua.<br>**Indisponible:** Paralización del equipo de desarrollo y bloqueo de despliegues o correcciones urgentes. |
| **Respaldos de bases de datos** | infraestructura | **Accedido:** Robo masivo de información histórica del negocio y usuarios.<br>**Modificado:** Corrupción intencional para evitar la recuperación ante incidentes.<br>**Indisponible:** Incapacidad de restaurar el sistema ante caídas críticas, ataques de Ransomware o desastres. |
| **Imágenes de contenedores y dependencias** | software | **Accedido:** Descubrimiento de componentes desactualizados y librerías vulnerables.<br>**Modificado:** Inyección de paquetes maliciosos en la cadena de suministro de software.<br>**Indisponible:** Imposibilidad de compilar, escalar o desplegar nuevos contenedores en el entorno. |
| **Logs y registros de auditoría** | información | **Accedido:** Fuga indirecta de información sensible presente en trazas y headers de peticiones.<br>**Modificado:** Manipulación o borrado de pistas forenses tras un ataque para garantizar impunidad.<br>**Indisponible:** Ceguera operativa; incapacidad para detectar anomalías, auditar intrusiones o depurar fallos. |
```[cite: 2]

