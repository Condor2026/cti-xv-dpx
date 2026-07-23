# 🧠 Dossier CTI: X-VDP-X (diable'fire) — Actor que apunta a entidades francesas mediante explotación de CMS

**Autor:** El Cóndor (@Panda_Sec_Intel)  
**Fecha:** 23 de julio de 2026  
**Estado:** Análisis activo / Inteligencia de fuentes abiertas (OSINT)  
**Licencia:** Uso libre para fines defensivos y de investigación

---

## 📌 Aviso Legal / Disclaimer

> **Este dossier se basa exclusivamente en inteligencia de fuentes abiertas (OSINT), publicaciones en redes sociales públicas y plataformas de inteligencia de amenazas.**
> Está destinado a la comunidad global de ciberseguridad para comprender las TTPs, mejorar las posturas defensivas y realizar búsqueda proactiva de amenazas.
> El análisis legal proporcionado es una interpretación contextual de la ley francesa pública con fines educativos y no constituye asesoramiento legal. Todas las atribuciones se basan en reivindicaciones auto declaradas por el actor de amenazas.

---

## 📋 Resumen Ejecutivo

El presente informe documenta y analiza al actor de amenazas identificado como **X-VDP-X** (alias **diable'fire**), responsable de la reciente brecha contra **France Cyber Défense** (francecyberdefense.fr), proveedor francés especializado en ciberseguridad, ocurrida el 23 de julio de 2026.

X-VDP-X es un **actor individual o pequeño colectivo** de perfil medio-bajo, operativo principalmente desde mediados de 2026, con base autodeclarada en **París, Francia**. Su modus operandi se caracteriza por la explotación de vulnerabilidades comunes en CMS (WordPress/Joomla), **defacements** y exfiltración de bases de datos con fines de **notoriedad y posible monetización** en foros clandestinos.

**No se atribuye a ningún estado-nación** (China, Rusia, Irán, etc.) ni presenta el nivel de sofisticación característico de APT. Su actividad, aunque ruidosa y visible, representa una amenaza de **riesgo medio-bajo** para infraestructuras críticas bien protegidas, pero **alta para PYMEs, universidades y sitios web con CMS desactualizados**.

---

## 2. PERFIL DEL ACTOR

### 2.1 Identidad y Alias

| Campo | Valor |
|-------|-------|
| **Alias principal** | X-VDP-X |
| **Alias secundario** | diable'fire (también escrito "diable fire" o "diablefire") ID TELEGRAM / 6321438384 |
| **Plataformas activas** | Telegram and Twitter, group name: Team X_VDP_X: (@xvdpx6). Group telegram Id 3280873247 |
| **Ubicación autodeclarada** | París, Francia |
| **Perfil estimado** | Individuo o pequeño colectivo (2-3 personas) |
| **Nivel técnico** | Intermedio-bajo (script-kiddie avanzado / defacer) |

```
This is diable'fire 
Messaց℮ diversity 100.00% 
From 2/6/2025 to 4/24/2025 
4 messages in 2 groups 
100.00% replies 0.00% average 
Circles: 0, voice: 0 
Favorite group: 
 
ID: 6321438384 
ᴜsernames:
|
----------------------------------------------------
Palabras mas usadas en Telegram, diable'ƒire (@diablefire) often uses this words: 
├3 - 3 informations
├2 - 3 free
├1 - 2 datasec, merci

[Settings. Chanցe - /words 6321438384 1000 3] 
Messages: 4 
1. Exclude: 0 trivial words 
2. Words to print: 3
 
-------------------------------------
 
This is channel : X-VDP-X 
 
ID: 3280873247 
 
Owner : ❔ 
 
Owner (history): ❔ 
 
About: 
--- --- --- --- --- --- --- 
Team X-VDP-X 
--- --- --- --- --- --- ---
-------------------------------------
```

### 2.2 Estilo Operativo

El actor sigue un patrón consistente en todas sus operaciones:

1. **Reconocimiento** de vulnerabilidades en CMS (WordPress, Joomla) — plugins desactualizados, configuraciones débiles, credenciales por defecto.
2. **Compromiso** mediante configuración/admin mistake o intrusiones en servidor web.
3. **Defacement** de la página principal, reemplazándola con el mensaje "HACKED BY X-VDP-X".
4. **Exfiltración** de bases de datos completas, archivos de configuración (`wp-config.php`), credenciales y logs.
5. **Publicación** de pruebas (screenshots, dumps parciales) en redes sociales.
6. **Oferta de venta** de los datos en foros clandestinos o Telegram.

### 2.3 Motivación

La motivación principal parece ser **notoriedad** y **reconocimiento** dentro de la comunidad de defacers, como lo evidencia su lema recurrente: *"I just want to be the best defacer"*. Secundariamente, existe una vertiente **económica** mediante la venta de accesos y bases de datos exfiltradas. No se ha identificado una ideología política o religiosa clara.

---

## 3. VÍCTIMAS REIVINDICADAS (CRONOLOGÍA)

X-VDP-X ha reivindicado un número significativo de ataques, con un **foco predominante en Francia** y algunas víctimas internacionales. La siguiente tabla recopila las víctimas confirmadas:

| Fecha | Víctima | Dominio | Tipo | País | Proof of Concept |
|-------|---------|---------|------|------|------------------|
| **23/07/2026** | **France Cyber Défense** | francecyberdefense.fr | Defacement + Data Breach | FR | Config/admin mistake |
| **23/07/2026** | Université d'Avignon | univ-avignon.fr | Data Breach (41 subdominios, 12.496 cuentas) | FR | — |
| **21/06/2026** | Caïmans 72 | caimans72.fr | Defacement | FR | Config/admin mistake |
| **21/06/2026** | brain.lazyy.fr | brain.lazyy.fr | Defacement | FR | Config/admin mistake |
| **21/06/2026** | auth.urbanflow.lazyy.fr | auth.urbanflow.lazyy.fr | Defacement | FR | Config/admin mistake |
| **21/06/2026** | hoppscotch.lazyy.fr | hoppscotch.lazyy.fr | Defacement | FR | Config/admin mistake |
| **21/06/2026** | sonarqube.lazyy.fr | sonarqube.lazyy.fr | Defacement | FR | Config/admin mistake |
| **21/06/2026** | affine.lazyy.fr | affine.lazyy.fr | Defacement | FR | Config/admin mistake |
| **21/06/2026** | web.choaristudio.com | web.choaristudio.com | Defacement | FR | Config/admin mistake |
| **21/06/2026** | www.point-core.com | www.point-core.com | Defacement | FR | Config/admin mistake |
| **21/06/2026** | www.b742.com | www.b742.com | Defacement | FR | Config/admin mistake |
| **21/06/2026** | test2025.samclap-ufolep.fr | test2025.samclap-ufolep.fr | Defacement | FR | Config/admin mistake |
| **19/06/2026** | Université Paris 13 | urit.univ-paris13.fr | Defacement | FR | — |
| **04/07/2026** | Tech Yukon | — | Defacement | — | — |
| **04/07/2026** | Twin Towing | — | Defacement | — | — |
| **04/07/2026** | D2P Graphics | — | Defacement | — | — |
| **10/02/2026** | Water Research and Innovation Platform (WSIP) | thewsip.mwi.gov.jo | Data Breach (venta de datos) | Jordania | — |
| **03/06/2026** | newfarmliving.com | newfarmliving.com | Defacement | — | — |

### 3.1 Análisis del Patrón de Víctimas

- **Concentración geográfica:** >70% de las víctimas están en Francia, lo que sugiere que el actor opera desde territorio francés o tiene un conocimiento privilegiado del ecosistema digital francés.
- **Sectores afectados:** Universidades, empresas de tecnología, sitios gubernamentales (Jordania), clubes deportivos, estudios de diseño.
- **Vector común:** Todos los sitios comprometidos utilizan **CMS vulnerables** (WordPress, Joomla) con **configuraciones administrativas deficientes**.

---

## 4. ANÁLISIS TÉCNICO DE LA BRECHA CONTRA FRANCE CYBER DÉFENSE

### 4.1 Resumen del Incidente

El 23 de julio de 2026, el sitio web de France Cyber Défense (francecyberdefense.fr) fue comprometido por X-VDP-X. La página de inicio fue reemplazada por un mensaje que declaraba: **"HACKED BY X-VDP-X"**, con una reivindicación atribuida a diable'fire.

El actor afirma haber **infiltrado la red** y **exfiltrado datos** sensibles. Aunque estas declaraciones requieren verificación independiente, las pruebas publicadas (capturas de pantalla, listados de archivos) sugieren un compromiso **más allá del mero defacement**.

### 4.2 Servicios y Componentes Comprometidos

El sitio comprometido operaba bajo **WordPress** con múltiples extensiones y componentes:

| Componente | Función | Riesgo Asociado |
|------------|---------|-----------------|
| **WordPress** | CMS principal | Exposición de configuración y usuarios |
| **WooCommerce** | Plataforma de comercio electrónico | Datos de clientes, órdenes, sesiones |
| **Simply Schedule Appointments (SSA)** | Gestión de citas | Información de rendez-vous/clientes |
| **Slider Revolution** | Plugin de presentaciones | Posibles vulnerabilidades conocidas |
| **Rank Math SEO** | Plugin SEO | Metadatos y configuración |
| **Action Scheduler** | Gestión de tareas programadas | Logs y procesos internos |

### 4.3 Archivos Exfiltrados (Según Reivindicación)

El actor publicó una lista de archivos extraídos que incluye:

| Archivo | Contenido Potencial | Nivel de Sensibilidad |
|---------|---------------------|----------------------|
| `wp-config.php` | Configuración de WordPress, credenciales de BD | **CRÍTICO** |
| `users.txt` | Lista de usuarios WordPress | ALTO |
| `usermeta.txt` | Metadatos de usuarios | ALTO |
| `server_info.txt` | Información del servidor | MEDIO |
| `options_apikeys.txt` | Claves API | **CRÍTICO** |
| `s3_credentials.txt` | Credenciales de almacenamiento S3 | **CRÍTICO** |
| `woocommerce-sessions.txt` | Sesiones de clientes | ALTO |
| `wp_woocommerce_log.txt` | Logs de WooCommerce | MEDIO |
| `wp_wc_orders_meta.txt` | Metadatos de órdenes | ALTO |
| `ssa-appointments.txt` | Citas agendadas | ALTO |

La presencia de `s3_credentials.txt` y `options_apikeys.txt` es **particularmente preocupante**, ya que sugiere que el actor podría haber obtenido acceso a **infraestructura en la nube** y **servicios de terceros**.

### 4.4 Técnicas, Tácticas y Procedimientos (TTPs)

Basado en el análisis de los ataques de X-VDP-X, se identifican las siguientes TTPs según el marco MITRE ATT&CK:

| Táctica | Técnica | Código MITRE | Evidencia |
|---------|---------|--------------|-----------|
| **Reconocimiento** | Escaneo de vulnerabilidades | T1595 | Patrón de ataque a CMS vulnerables |
| **Acceso Inicial** | Explotación de aplicación pública | T1190 | WordPress/Joomla vulnerabilities |
| **Acceso Inicial** | Credenciales por defecto | T1078 | "Configuration/admin mistake" |
| **Persistencia** | Creación de cuenta | T1136 | Acceso a paneles admin |
| **Exfiltración** | Exfiltración a través de C2 | T1041 | Publicación de dumps en redes |
| **Impacto** | Defacement | T1491 | "HACKED BY X-VDP-X" |
| **Impacto** | Data Destruction (parcial) | T1485 | Alteración de contenido |

**Nivel de sofisticación:** **BAJO-MEDIO**. No se observan técnicas avanzadas como:
- Zero-days
- Malware personalizado
- Técnicas de evasión avanzadas
- Movimiento lateral complejo
- Ransomware

---

## 5. INDICADORES DE COMPROMISO (IOCs)

### 5.1 Direcciones IP Identificadas

| IP | Localización | Asociación |
|----|--------------|------------|
| `46.235.180.85` | Francia | Servidor Nginx (lazyy.fr) |
| `92.222.139.190` | Francia | Servidor Apache |
| `81.194.43.208` | Francia | Servidor Apache (Université Paris 13) |
| `185.125.27.212` | Suiza | Servidor Apache (lespartisans.ch) |
| `185.49.20.100` | Francia | Servidor Apache |
| `185.221.182.212` | Francia | Servidor LiteSpeed (caimans72.fr) |

### 5.2 Dominios y URLs Asociados

- **Perfil X/Twitter:** `@xvdpx6` (o variaciones `@6xvdpx`)
- **Canal Telegram:** `@diablefire`
- **URLs de defacement:**
  - `https://2025.lespartisans.ch/media/com_pagebuilderck/gfonts/hacked.html`
  - `https://urit.univ-paris13.fr/Hackedbyxvdpx.txt`

### 5.3 Patrones de Defacement

- **Mensaje característico:** "HACKED BY X-VDP-X"
- **Firma:** "diable'fire — Team: X-VDP-X"
- **Lema:** "I just want to be the best defacer"

---

## 6. EVALUACIÓN DE AMENAZA

### 6.1 Matriz de Riesgo

| Dimensión | Evaluación | Justificación |
|-----------|------------|---------------|
| **Capacidad técnica** | Baja-Media | Explota vulnerabilidades conocidas, sin malware avanzado |
| **Capacidad de impacto** | Media | Puede exfiltrar datos sensibles y causar daño reputacional |
| **Intención maliciosa** | Media | Busca notoriedad y beneficio económico |
| **Persistencia** | Media | Activo desde febrero 2026, con picos en junio-julio |
| **Alcance geográfico** | Media | Foco en Francia, con incursiones internacionales |
| **Riesgo para infraestructuras críticas** | Bajo | No ataca OIV (Operadores de Importancia Vital) |
| **Riesgo para PYMEs/universidades** | **Alto** | Son el blanco principal del actor |

### 6.2 Clasificación de Amenaza

X-VDP-X se clasifica como un **actor oportunista de nivel medio-bajo**, comparable a:

- **Defacers** de la escena underground europea
- **Script-kiddies avanzados** con conocimientos de CMS
- **Hacktivistas sin ideología definida**

**No es equiparable a:**
- APT estatales (Mustang Panda, APT28, etc.)
- Grupos de ransomware sofisticados (LockBit, BlackCat)
- Hacktivistas pro-rusos (NoName057(16), Killnet)

### 6.3 Impacto Potencial de la Brecha a France Cyber Défense

1. **Reputacional:** Una empresa de ciberseguridad comprometida genera una **pérdida de confianza** significativa entre sus clientes.
2. **Cadena de suministro:** Las credenciales y claves API exfiltradas podrían utilizarse para **ataques contra clientes** de France Cyber Défense.
3. **Regulatorio:** Posibles sanciones bajo el **GDPR** si se confirma la exposición de datos personales.
4. **Operacional:** Interrupción de servicios y necesidad de **auditoría forense** exhaustiva.

---

## 7. RECOMENDACIONES ESTRATÉGICAS

### 7.1 Para ANSSI / CERT-FR

1. **Notificación formal:** Asegurar que France Cyber Défense ha notificado el incidente a ANSSI conforme a la normativa vigente.
2. **Seguimiento activo:** Monitorear las cuentas `@xvdpx6` y `@diablefire` para identificar nuevas víctimas o publicaciones de datos.
3. **Coordinación internacional:** Contactar con CERT-JO (Jordania) por el incidente contra la plataforma gubernamental de agua.
4. **Análisis forense:** Solicitar a France Cyber Défense los logs de acceso para identificar el vector de entrada exacto.

### 7.2 Para France Cyber Défense

1. **Contención inmediata:**
   - Aislar el servidor comprometido.
   - Rotar **todas** las credenciales y claves API (especialmente las de S3).
   - Revocar sesiones activas de WordPress/WooCommerce.

2. **Investigación forense:**
   - Analizar logs de acceso para determinar el vector de entrada.
   - Identificar qué datos fueron realmente exfiltrados (no solo los reivindicados).
   - Verificar la integridad de los archivos `wp-config.php` y otros archivos de configuración.

3. **Comunicación:**
   - Notificar a los clientes afectados (transparencia).
   - Coordinar con ANSSI para la comunicación pública.

4. **Refuerzo de seguridad:**
   - Implementar **WAF** (Web Application Firewall).
   - Activar **MFA** (Multi-Factor Authentication) para todos los accesos administrativos.
   - Actualizar **todos** los plugins y el núcleo de WordPress.
   - Realizar **auditoría de seguridad** completa del código y la infraestructura.

### 7.3 Para otras organizaciones francesas

1. **Auditoría de CMS:** Verificar que todos los sitios WordPress/Joomla están actualizados.
2. **Revisión de configuraciones:** Eliminar credenciales por defecto y archivos de configuración expuestos.
3. **Monitoreo:** Buscar en logs accesos desde las IPs identificadas (`46.235.180.85`, `92.222.139.190`, etc.).
4. **Formación:** Sensibilizar al personal sobre riesgos de configuraciones administrativas débiles.

---

## 8. ANÁLISIS DE TENDENCIAS Y PROYECCIONES

### 8.1 Evolución de la Actividad

X-VDP-X muestra un **patrón de actividad creciente**:

- **Febrero 2026:** Primer ataque documentado (WSIP, Jordania)
- **Junio 2026:** Pico de actividad (>15 defacements en una semana)
- **Julio 2026:** Escalada a **data breaches** con exfiltración de bases de datos completas

Esta trayectoria sugiere que el actor está **ganando confianza y capacidades**. Es probable que continúe atacando objetivos franceses de perfil medio, con posible escalada a:

- **Instituciones educativas** (ya atacadas: Université d'Avignon, Université Paris 13)
- **PYMEs tecnológicas**
- **Sitios gubernamentales locales**

### 8.2 Potencial de Monetización

El actor ha demostrado disposición a **vender datos** en foros clandestinos. Es probable que:

1. Intente monetizar los datos de France Cyber Défense en **BreachForums** o canales de Telegram.
2. Ofrezca **accesos persistentes** a los sistemas comprometidos a otros actores.
3. Escale a **extorsión** si encuentra datos particularmente sensibles.

---

## 9. FUENTES Y REFERENCIAS

| Fuente | Enlace | Tipo |
|--------|--------|------|
| DefacerID — Cyber Attack Reports | https://www.defacer.id | Registro de defacements |
| FrenchBreaches — France Cyber Défense | https://frenchbreaches.com/alertes/france-cyber-d-fense-mrxd8ygo8ndtxqd9jt3 | Análisis de brecha |
| FrenchBreaches — Université d'Avignon | https://frenchbreaches.com/alertes/universit-d-avignon-mrxhevofqu9spqmlhu | Análisis de brecha |
| Brinztech — WSIP Breach | https://www.brinztech.com/breach-alerts/ | Alerta de venta de datos |
| OSINTxLab | https://www.osintxlab.com | Agregador de amenazas |
| ANSSI | https://cyber.gouv.fr | Agencia nacional de seguridad |

---

## 10. APÉNDICE — GLOSARIO DE TÉRMINOS

| Término | Definición |
|---------|------------|
| **Defacement** | Alteración no autorizada del contenido visual de un sitio web |
| **Data Breach** | Exfiltración no autorizada de datos sensibles |
| **CMS** | Content Management System (Sistema de Gestión de Contenidos) |
| **APT** | Advanced Persistent Threat (Amenaza Persistente Avanzada) |
| **WAF** | Web Application Firewall (Cortafuegos de Aplicaciones Web) |
| **MFA** | Multi-Factor Authentication (Autenticación Multifactor) |
| **OIV** | Opérateur d'Importance Vitale (Operador de Importancia Vital) |
| **IOC** | Indicator of Compromise (Indicador de Compromiso) |

---

## ANEXO JURÍDICO — INFORME COMPLEMENTARIO

**Delitos Potenciales Cometidos por X-VDP-X (diable'fire) según el Código Penal Francés**

**Fecha de elaboración:** 23 de julio de 2026

---

### 1. INTRODUCCIÓN Y FUNDAMENTO JURÍDICO

El marco jurídico francés para la represión de los ciberataques se articula en torno a los **artículos 323-1 a 323-8 del Código Penal** (Code pénal), resultado de la **Ley Godfrain n° 88-19 del 5 de enero de 1988**, posteriormente reforzada por sucesivas reformas —notablemente la **Ley LOPPSI 2 del 14 de marzo de 2011** y las leyes de 2014 y 2015 que ampliaron las incriminaciones y elevaron las penas.

El concepto de *sistema de tratamiento automatizado de datos* (STAD) no está definido explícitamente por la ley, lo que constituye una opción deliberada del legislador para garantizar la adaptabilidad del texto a la evolución tecnológica. La jurisprudencia retiene una **concepción amplia** que abarca todo conjunto organizado de materiales y software destinados al tratamiento de información: un servidor, una red empresarial, un sitio web, un sistema de mensajería, un objeto conectado o un smartphone.

Las cinco infracciones fundamentales que cubren el conjunto de las **atentados contra los sistemas de información** son:
1. Acceso fraudulento (art. 323-1)
2. Entorpecimiento del funcionamiento (art. 323-2)
3. Atentado contra los datos (art. 323-3)
4. Puesta a disposición de herramientas de ataque (art. 323-3-1)
5. Atentado contra sistemas de interés general (art. 323-4-1)

---

### 2. ANÁLISIS DETALLADO DE LOS DELITOS PRINCIPALES

#### 2.1 Acceso fraudulento a un sistema de tratamiento automatizado de datos (Art. 323-1)

**Texto del artículo:**
> *« Le fait d'accéder ou de se maintenir, frauduleusement, dans tout ou partie d'un système de traitement automatisé de données est puni de trois ans d'emprisonnement et de 100 000 euros d'amende. »*

**Elementos constitutivos:**
- **Acceso o mantenimiento:** El autor debe haber accedido o permanecido en el sistema. La permanencia fraudulenta puede producirse incluso cuando el acceso inicial fue legítimo (ej. un empleado que continúa accediendo tras su cese).
- **Fraudulento:** El acceso debe realizarse sin autorización o mediante maniobras engañosas (suplantación de identidad, uso de credenciales robadas, explotación de vulnerabilidades).
- **Sistema de tratamiento automatizado de datos (STAD):** Concepto amplio que incluye servidores, sitios web, redes, etc.

**Agravante (Art. 323-1, al. 2):**
> La pena se eleva a **cinco años de prisión y 150.000 € de multa** cuando la infracción ha causado la destrucción, alteración o deterioro de datos, o una perturbación del funcionamiento del sistema.

**Aplicación al caso X-VDP-X:**
- Acceso a los paneles de administración de WordPress/Joomla de France Cyber Défense, Université d'Avignon y demás víctimas.
- Mantenimiento en los sistemas para extraer bases de datos completas (usuarios, WooCommerce, citas).
- Uso de credenciales robadas o explotación de vulnerabilidades (« configuration/admin mistake »).
- **Calificación recomendada:** Art. 323-1, alínea 2 (agravado por extracción y alteración de datos).

**Jurisprudencia relevante:**
La jurisprudencia ha aplicado el artículo 323-1 a casos de intrusión en servidores, pirateo de cuentas de correo electrónico y accesos no autorizados a sistemas de información empresariales. El simple hecho de conectarse a un sistema sin autorización constituye la infracción, independientemente de que se haya causado un daño adicional.

---

#### 2.2 Entorpecimiento o falseamiento del funcionamiento de un STAD (Art. 323-2)

**Texto del artículo:**
> *« Le fait d'entraver ou de fausser le fonctionnement d'un système de traitement automatisé de données est puni de cinq ans d'emprisonnement et de 150 000 euros d'amende. »*

**Elementos constitutivos:**
- **Entorpecimiento o falseamiento:** Toda acción que perturbe el funcionamiento normal del sistema, incluyendo la denegación de servicio, la inyección de código malicioso, o la modificación de la configuración.
- **Carácter fraudulento:** La acción debe ser intencional y sin autorización.

**Aplicación al caso X-VDP-X:**
- **Defacements** de las páginas de inicio (reemplazo del contenido por « HACKED BY X-VDP-X »).
- Modificación de archivos del CMS que alteran la presentación y funcionalidad del sitio.
- Posible inyección de scripts o código malicioso en los sitios comprometidos.

**Jurisprudencia relevante:**
La jurisprudencia asimila al entorpecimiento del funcionamiento toda modificación no autorizada que afecte a la disponibilidad, integridad o confidencialidad del sistema. El simple defacement constituye una infracción tipificada en este artículo.

---

#### 2.3 Introducción, extracción, supresión o modificación fraudulenta de datos (Art. 323-3)

**Texto del artículo:**
> *« Le fait d'introduire frauduleusement des données dans un système de traitement automatisé ou de supprimer ou de modifier frauduleusement les données qu'il contient est puni de cinq ans d'emprisonnement et de 150 000 euros d'amende. »*

**Evolución legislativa:**
El **vol de datos informáticos** solo ha sido considerado específicamente por el artículo 323-3 desde **2014**. Anteriormente, el texto solo sancionaba la introducción, supresión o modificación de datos. La reforma de 2014 añadió explícitamente la **extracción** de datos.

**Texto actual completo (art. 323-3):**
> *« Le fait d'introduire frauduleusement des données dans un système de traitement automatisé, **d'extraire, de détenir, de reproduire, de transmettre,** de supprimer ou de modifier frauduleusement les données qu'il contient est puni de cinq ans d'emprisonnement et de 150 000 euros d'amende. »*

**Elementos constitutivos:**
- **Introducción fraudulenta:** Inserción de datos falsos o no autorizados.
- **Extracción:** Copia o traslado de datos fuera del sistema (exfiltración).
- **Detención:** Posesión de los datos extraídos.
- **Reproducción/Transmisión:** Duplicación o difusión de los datos.
- **Supresión/Modificación:** Alteración o eliminación de datos existentes.

**Aplicación al caso X-VDP-X:**
- **Extracción** de bases de datos completas (usuarios, WooCommerce, citas, configuraciones).
- **Detención** de los archivos exfiltrados (`wp-config.php`, `users.txt`, `s3_credentials.txt`, etc.).
- **Transmisión** mediante publicación en redes sociales y oferta de venta en Telegram.
- **Modificación** de archivos del sitio (defacement).
- **Calificación recomendada:** Art. 323-3 (infracción principal, dado el volumen y naturaleza de los datos exfiltrados).

**Nota importante:** La extracción de datos **sin autorización** constituye la infracción, independientemente de que los datos sean confidenciales o no. La calificación se agrava cuando los datos son de naturaleza personal o sensible.

---

#### 2.4 Agravantes generales (Arts. 323-4, 323-4-1, 323-6)

##### 2.4.1 Banda organizada (Art. 323-4-1)

**Texto:**
> *« Lorsque les infractions prévues aux articles 323-1 à 323-3-1 ont été commises en bande organisée, la peine est portée à dix ans d'emprisonnement et à 300 000 euros d'amende. »*

**Definición de « banda organizada » (Art. 132-71):**
> Toda asociación, cualquiera que sea su duración, establecida con vistas a la preparación de una o varias infracciones, caracterizada por uno o varios hechos materiales.

**Aplicación al caso X-VDP-X:**
- Si se demuestra que X-VDP-X actúa con uno o varios cómplices (colectivo).
- La prueba puede basarse en la pluralidad de atacantes, la coordinación de las acciones, o la existencia de una estructura organizada (canal Telegram, reparto de tareas).

##### 2.4.2 Atentado contra los intereses fundamentales de la Nación (Art. 323-6)

**Texto:**
> *« Les infractions prévues aux articles 323-1 à 323-5 sont punies des peines portées à dix ans d'emprisonnement et à 1 000 000 d'euros d'amende lorsqu'elles ont porté atteinte à un système de traitement automatisé de données intéressant la défense nationale, la sûreté de l'État ou la sécurité publique, ou dont la violation est de nature à compromettre la souveraineté nationale. »*

**Aplicación al caso X-VDP-X:**
- France Cyber Défense es un **prestador de servicios de ciberseguridad** que puede tener contratos con entidades gubernamentales o militares.
- Si la brecha afecta a sistemas que contienen datos sensibles para la defensa nacional o la seguridad del Estado, esta agravante podría ser aplicable.
- La calificación requerirá una investigación para determinar la naturaleza exacta de los datos comprometidos.

##### 2.4.3 Atentado contra sistemas de interés general (Art. 323-4-1)

**Texto:**
> Cuando las infracciones previstas en los artículos 323-1 a 323-3-1 se cometen contra un sistema de tratamiento automatizado de datos de un **operador de servicios esenciales** (OSE) o de un **operador de importancia vital** (OIV), la pena se eleva a **siete años de prisión y 300.000 € de multa**.

**Aplicación al caso:**
- France Cyber Défense, en su calidad de prestador de ciberseguridad, podría ser calificado como OSE u OIV.
- Las universidades (Avignon, Paris 13) pueden estar vinculadas a servicios esenciales (educación, investigación).

---

### 3. OTROS DELITOS POTENCIALMENTE APLICABLES

#### 3.1 Violación de datos personales y privacidad (Arts. 226-1 a 226-7 + RGPD + Ley Informatique et Libertés)

**Art. 226-16 del Código Penal:**
> *« Le fait, y compris par négligence, de procéder ou de faire procéder à des traitements de données à caractère personnel sans qu'aient été respectées les […] prévues par la loi est puni de cinq ans d'emprisonnement et de 300 000 euros d'amende. »*

**Aplicación al caso X-VDP-X:**
- **Recogida fraudulenta:** Extracción de datos personales (nombres, correos electrónicos, información de clientes) sin consentimiento.
- **Detención y difusión:** Posesión de los datos y publicación de pruebas en redes sociales.
- **Transmisión:** Oferta de venta de bases de datos en canales Telegram.

**Sanciones administrativas adicionales (CNIL):**
La CNIL puede imponer sanciones administrativas por violación del RGPD, que pueden alcanzar:
- **10 millones de euros** o **2 % del volumen de negocios anual mundial** (para empresas).
- **Hasta 300.000 €** para personas físicas.

#### 3.2 Receptación de bienes obtenidos mediante delito (Art. 321-1)

**Texto:**
> *« Le fait de receler, de détenir, de transmettre ou d'utiliser des biens provenant d'un délit ou d'un crime est puni de cinq ans d'emprisonnement et de 375 000 euros d'amende. »*

**Aplicación al caso:**
- Posesión y transmisión de datos exfiltrados (bases de datos, archivos de configuración, credenciales).
- Oferta de venta de los datos en foros clandestinos o canales de Telegram.

#### 3.3 Extorsión o tentativa de extorsión (Art. 313-1 y ss.)

**Texto:**
> *« L'extorsion est le fait d'obtenir par violence, menace de violence ou contrainte, soit une signature, un engagement ou une renonciation, soit la remise d'un bien, soit des fonds, des valeurs ou un bien quelconque. »*

**Aplicación al caso:**
- Si X-VDP-X exige un pago a cambio de no publicar los datos exfiltrados o para restaurar el sitio.
- La prueba de la extorsión puede basarse en mensajes o comunicaciones del actor.

#### 3.4 Daños informáticos (Art. 322-1 y ss.)

**Aplicación al caso:**
- Si el actor ha causado daños materiales (pérdida de datos, costes de restauración, interrupción de la actividad).
- El perjuicio económico para las víctimas puede ser evaluado y reclamado en sede civil.

---

### 4. CUADRO RESUMEN DE PENAS

| Infracción | Artículo | Pena base | Agravante (banda organizada) | Agravante (intereses nacionales) |
|------------|----------|-----------|------------------------------|----------------------------------|
| Acceso fraudulento | 323-1 | 3 años / 100.000 € | 10 años / 300.000 € | 10 años / 1.000.000 € |
| Acceso fraudulento con daño | 323-1 al.2 | 5 años / 150.000 € | 10 años / 300.000 € | 10 años / 1.000.000 € |
| Entorpecimiento del funcionamiento | 323-2 | 5 años / 150.000 € | 10 años / 300.000 € | 10 años / 1.000.000 € |
| Atentado contra datos (extracción, etc.) | 323-3 | 5 años / 150.000 € | 10 años / 300.000 € | 10 años / 1.000.000 € |
| Puesta a disposición de herramientas | 323-3-1 | 5 años / 150.000 € | 10 años / 300.000 € | 10 años / 1.000.000 € |
| Violación de datos personales | 226-16 | 5 años / 300.000 € | — | — |
| Receptación | 321-1 | 5 años / 375.000 € | — | — |
| Extorsión | 313-1 | 7 años / 100.000 € | — | — |

**Fuente:** Elaboración propia a partir de los arts. 323-1 a 323-6 del Código Penal.

---

### 5. AUTORIDADES COMPETENTES Y PROCEDIMIENTO

#### 5.1 Autoridades de investigación y persecución

| Autoridad | Competencia | Contacto |
|-----------|-------------|----------|
| **OCLCTIC** (Office Central de Lutte contre la Criminalité liée aux Technologies de l'Information et de la Communication) | Investigación de delitos informáticos a nivel nacional | 101 rue des Trois Fontanot, 92000 Nanterre |
| **OFAC** (Office Anti-Cybercriminalité) | Nueva denominación de la OCLCTIC | Misma dirección |
| **Section Cybercriminalité du Parquet de Paris** | Instrucción y persecución de delitos cibernéticos | Tribunal Judicial de París |
| **JIRS** (Juridictions Interrégionales Spécialisées) | Competencia para casos complejos de criminalidad organizada | Varias sedes en Francia |
| **ANSSI** (Agence Nationale de la Sécurité des Systèmes d'Information) | Alerta técnica, asistencia a víctimas, certificación | cyber.gouv.fr |
| **CERT-FR** | Centro de respuesta a incidentes de seguridad | CERT-FR |

#### 5.2 Procedimiento recomendado

1. **Depósito de denuncia:** La víctima (France Cyber Défense) debe presentar denuncia ante el fiscal del Tribunal Judicial de París o ante la OCLCTIC.

2. **Aseguramiento de pruebas:**
   - Capturas de pantalla de las reivindicaciones en X (@xvdpx6) y Telegram (@diablefire).
   - Registro de los defacements y archivos modificados.
   - Logs de acceso al servidor comprometido.
   - Análisis forense del sistema para determinar el vector de entrada.

3. **Notificaciones obligatorias:**
   - **CNIL:** En caso de violación de datos personales (dentro de las 72 horas siguientes al conocimiento del incidente).
   - **ANSSI:** Para incidentes que afecten a operadores de servicios esenciales (NIS2).

4. **Cooperación internacional:** Si el actor opera desde Francia (como parece indicar su ubicación autodeclarada en París), la cooperación con las autoridades francesas será directa. Si se descubre que opera desde el extranjero, será necesaria la cooperación judicial internacional (MLAT, Eurojust).

---

### 6. ANÁLISIS DE LA CALIFICACIÓN JURÍDICA RECOMENDADA PARA EL CASO FRANCE CYBER DÉFENSE

#### 6.1 Infracciones principales

| N° | Infracción | Artículo | Fundamento |
|----|------------|----------|------------|
| 1 | Acceso y mantenimiento fraudulento | 323-1 al.2 | Acceso a los paneles de administración y mantenimiento para extraer datos |
| 2 | Extracción fraudulenta de datos | 323-3 | Exfiltración de bases de datos completas (usuarios, WooCommerce, configuraciones) |
| 3 | Modificación fraudulenta de datos | 323-3 | Defacement y alteración de archivos del sitio |
| 4 | Entorpecimiento del funcionamiento | 323-2 | Defacement que afecta a la disponibilidad del sitio |

#### 6.2 Circunstancias agravantes potenciales

- **Banda organizada (Art. 323-4-1):** Si se demuestra que X-VDP-X actúa con cómplices.
- **Atentado contra sistema de interés general (Art. 323-4-1):** France Cyber Défense, como prestador de ciberseguridad, puede ser calificado como OSE u OIV.
- **Atentado contra intereses fundamentales de la Nación (Art. 323-6):** Si los datos comprometidos afectan a la defensa nacional o la seguridad del Estado.

#### 6.3 Infracciones secundarias

- **Violación de datos personales (Art. 226-16):** Exfiltración de datos personales de usuarios y clientes.
- **Receptación (Art. 321-1):** Posesión y transmisión de los datos exfiltrados.
- **Extorsión (Art. 313-1):** Si se demuestra que el actor exige un pago.

#### 6.4 Penas máximas acumulables

En aplicación del principio de **acumulación de penas** (concours réel d'infractions), las penas previstas para cada infracción pueden acumularse, dentro del límite del **máximo legal** (art. 132-2 del Código Penal). En el caso de X-VDP-X, la acumulación de las infracciones principales y agravantes podría resultar en una pena de **hasta 10 años de prisión y 1.000.000 € de multa** (o más en caso de extorsión).

---

### 7. REFERENCIAS LEGALES

| Texto | Referencia | Contenido |
|-------|------------|-----------|
| Código Penal, art. 323-1 | LEGIARTI000030939438 | Acceso fraudulento a STAD |
| Código Penal, art. 323-2 | LEGIARTI000030939443 | Entorpecimiento del funcionamiento |
| Código Penal, art. 323-3 | LEGIARTI000030939448 | Atentado contra datos |
| Código Penal, art. 323-4-1 | LEGIARTI000030939453 | Agravante de banda organizada |
| Código Penal, art. 323-6 | LEGIARTI000030939463 | Agravante de intereses nacionales |
| Código Penal, art. 226-16 | LEGIARTI000030939438 | Violación de datos personales |
| Ley Godfrain n° 88-19 | 5 de enero de 1988 | Ley fundacional sobre delitos informáticos |
| Ley LOPPSI 2 | 14 de marzo de 2011 | Refuerzo de las sanciones |
| RGPD (UE) 2016/679 | 27 de abril de 2016 | Protección de datos personales |

---

### 8. GLOSARIO JURÍDICO

| Término | Definición |
|---------|------------|
| **STAD** | Système de Traitement Automatisé de Données — Sistema de tratamiento automatizado de datos |
| **OIV** | Opérateur d'Importance Vitale — Operador de importancia vital (infraestructura crítica) |
| **OSE** | Opérateur de Services Essentiels — Operador de servicios esenciales (NIS2) |
| **OCLCTIC** | Office Central de Lutte contre la Criminalité liée aux Technologies de l'Information et de la Communication |
| **OFAC** | Office Anti-Cybercriminalité (nueva denominación de la OCLCTIC) |
| **JIRS** | Juridiction Interrégionale Spécialisée — Jurisdicción interregional especializada |
| **CNIL** | Commission Nationale de l'Informatique et des Libertés — Autoridad de protección de datos |
| **ANSSI** | Agence Nationale de la Sécurité des Systèmes d'Information — Agencia nacional de seguridad de sistemas de información |
| **CERT-FR** | Computer Emergency Response Team France — Centro de respuesta a incidentes |
| **Concours réel d'infractions** | Acumulación real de infracciones — Pluralidad de delitos cometidos por el mismo autor |

---

**Fin del Anexo Jurídico**

*El presente documento constituye un análisis jurídico preliminar basado en el Código Penal francés vigente y las fuentes jurisprudenciales y doctrinales disponibles. La calificación definitiva de los hechos corresponde a las autoridades judiciales competentes tras la instrucción del caso.*

---

**Fin del Informe**

*Este documento ha sido elaborado con información de fuentes abiertas (OSINT) y análisis de inteligencia de amenazas. La verificación independiente de las reivindicaciones del actor está pendiente de confirmación forense.*

---

## 📝 Registro de Actualizaciones

- **v1.0 (23/07/2026):** Publicación inicial. Incluye perfil del actor, TTPs, listas de IOCs y contexto legal para la brecha de France Cyber Défense.

---

**El Cóndor**  
*"El conocimiento es el único arma que mejora con el uso. Mantente vigilante, mantente informado."*

---
