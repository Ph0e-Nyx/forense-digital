<div align="center">
  <br>

  <h1><img src="https://img.icons8.com/ios/256/FFFFFF/detective.png" width="35" valign="middle">&nbsp; GUÍA MAESTRA DE INFORMÁTICA FORENSE Y RESPUESTA A INCIDENTES</h1>

  <p><strong>Tu referencia definitiva para herramientas, técnicas y procedimientos en DFIR.</strong></p>

  <img src="https://img.shields.io/badge/DFIR-Expert-000000?style=for-the-badge&logo=linux&logoColor=white" alt="DFIR" />
  <img src="https://img.shields.io/badge/Forensics-Investigation-000000?style=for-the-badge&logo=windows&logoColor=white" alt="Forensics" />
  <img src="https://img.shields.io/badge/Security-Blue_Team-000000?style=for-the-badge&logo=security&logoColor=white" alt="Security" />
  
</div>

<br><br>


<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=rect&color=ffffff&text=ÍNDICE%20DE%20CONTENIDOS&fontColor=000000&height=40&fontSize=22" width="100%"/>
</div>
<br>

1. [Sistemas Operativos y Distribuciones](#1-sistemas-operativos-y-distribuciones)
2. [Adquisición de Evidencia (Copia Forense)](#2-adquisición-de-evidencia-copia-forense)
3. [Respuesta a Incidentes (First Responder)](#3-respuesta-a-incidentes-first-responder)
4. [Análisis Forense: General y Triage](#4-análisis-forense-general-y-triage)
5. [Análisis Específico: Windows y macOS](#5-análisis-específico-windows-y-macos)
6. [Análisis de Memoria y Metadatos](#6-análisis-de-memoria-y-metadatos)
7. [Recuperación de Datos (Data Recovery)](#7-recuperación-de-datos-data-recovery)
8. [Suite de Herramientas "DBX" (Utilidades Ligeras)](#8-suite-de-herramientas-dbx-utilidades-ligeras)
9. [Recursos y Mejores Prácticas](#9-recursos-y-mejores-prácticas)

<br><br>


<a name="1-sistemas-operativos-y-distribuciones"></a>
<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=rect&color=ffffff&text=1.%20SISTEMAS%20OPERATIVOS%20Y%20DISTRIBUCIONES&fontColor=000000&height=40&fontSize=22" width="100%"/>
</div>
<br>

¿Por qué usar una Distro Forense Linux?

Permiten acceder a un PC y a sus datos sin alterar el estado original de la evidencia y sin arrancar el sistema operativo nativo del sospechoso, garantizando la integridad de la prueba (Write-blocking por software).

### <img src="https://img.icons8.com/ios/256/FFFFFF/linux.png" width="22" valign="middle"> Distribuciones Linux Recomendadas

* **CSI Linux:** Enfocada en investigación cibernética completa.
* **CAINE (Computer Aided Investigative Environment):** Estándar de la industria, interfaz amigable y fuerte en bloqueo de escritura.
* **Tsurugi Linux:** Excelente para DFIR (Digital Forensics & Incident Response) y análisis de malware.
* **SANS SIFT Workstation:** La distribución de facto para análisis profundo y cursos SANS.
* **Kali Linux / Parrot Security OS:** Aunque ofensivas, tienen modos forenses (Forensic Mode) útiles.
* **Tails:** Para privacidad y anonimato extremo durante investigaciones OSINT.
* **AthenaOS / Predator-OS:** Alternativas emergentes en el sector.
* **Paladin Edge:** Basada en bootable USB, ideal para triage rápido.

<br><br>


<a name="2-adquisición-de-evidencia-copia-forense"></a>
<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=rect&color=ffffff&text=2.%20ADQUISICIÓN%20DE%20EVIDENCIA%20(COPIA%20FORENSE)&fontColor=000000&height=40&fontSize=22" width="100%"/>
</div>
<br>

**Concepto:** La copia forense (imagen _bit-stream_) es la adquisición de datos que genera un duplicado exacto (bit a bit) de un dispositivo de almacenamiento a otro, asegurando que la evidencia original no se modifique.

### <img src="https://img.icons8.com/ios/256/FFFFFF/hdd.png" width="22" valign="middle"> Herramientas de Imagen de Disco

* **FTK Imager:** El estándar gratuito en Windows. Permite crear imágenes, montar discos y visualizar contenido.
* **Guymager:** La mejor herramienta gráfica para Linux (rápida y robusta).
* **DC3DD / DCFLDD:** Versiones forenses del comando `dd` de Linux con hashing y logs de seguridad.
* **Fuji (Forensic Unattended Juicy Imaging):** Para automatizar imágenes.

### <img src="https://img.icons8.com/ios/256/FFFFFF/globe--v1.png" width="22" valign="middle"> Adquisición Web (OSINT y Preservación)

* **FAW (Forensic Acquisition of Websites):** Navegador forense para capturar páginas web con valor legal.
* **Httrack:** Para descargar sitios web completos.
* **Browser History Capturer / Chrome Cache View:** Herramientas de NirSoft para extraer historiales locales.

<br><br>


<a name="3-respuesta-a-incidentes-first-responder"></a>
<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=rect&color=ffffff&text=3.%20RESPUESTA%20A%20INCIDENTES%20(FIRST%20RESPONDER)&fontColor=000000&height=40&fontSize=22" width="100%"/>
</div>
<br>

El rol del First Responder:

Es el primero en intervenir en la escena. Debe seguir protocolos estrictos para no alterar la situación (ni destruir pruebas, ni añadir rastros). Su objetivo es preservar la volatilidad de los datos.

### <img src="https://img.icons8.com/ios/256/FFFFFF/ambulance.png" width="22" valign="middle"> Herramientas de Triage y Recolección en Vivo

* **Velociraptor / GRR Rapid Response:** Para caza de amenazas y monitoreo remoto a gran escala.
* **OSQuery:** Convierte el sistema operativo en una base de datos relacional para hacer consultas SQL sobre su estado.
* **UAC (Unix-like Artifacts Collector):** Recolector de artefactos para sistemas Linux/Unix.
* **MIG (Mozilla InvestiGator):** Plataforma de investigación remota.

<br><br>


<a name="4-análisis-forense-general-y-triage"></a>
<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=rect&color=ffffff&text=4.%20ANÁLISIS%20FORENSE:%20GENERAL%20Y%20TRIAGE&fontColor=000000&height=40&fontSize=22" width="100%"/>
</div>
<br>

El análisis implica la conversión, extracción e interpretación de datos para reconstruir la cronología: _quién, cómo, cuándo y qué_.

### <img src="https://img.icons8.com/ios/256/FFFFFF/search--v1.png" width="22" valign="middle"> Suites de Análisis

* **Autopsy:** La interfaz gráfica de _The Sleuth Kit_. La herramienta open source más completa.
* **IPED (Indexador y Procesador de Evidencias Digitales):** Muy potente, usada por la policía federal de Brasil. Excelente para grandes volúmenes de datos.
* **Turbinia:** Automatización de análisis forense en la nube.
* **DFF (Digital Forensics Framework):** Entorno modular de análisis.

<br><br>


<a name="5-análisis-específico-windows-y-macos"></a>
<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=rect&color=ffffff&text=5.%20ANÁLISIS%20ESPECÍFICO:%20WINDOWS%20Y%20MACOS&fontColor=000000&height=40&fontSize=22" width="100%"/>
</div>
<br>

### <img src="https://img.icons8.com/ios/256/FFFFFF/windows8.png" width="22" valign="middle"> Windows Forensics

Es el campo más consolidado, enfocado en recuperar artefactos de usuario, registro y sistema en entornos corporativos.

* **NirSoft Tools:** Suite esencial de pequeñas utilidades.
* **PowerForensics:** Framework de análisis basado en PowerShell.

### <img src="https://img.icons8.com/ios/256/FFFFFF/mac-os.png" width="22" valign="middle"> Mac Forensics

Requiere conocimiento profundo del sistema de archivos APFS y estructuras de Apple.

* **mac_apt (macOS Artifact Parsing Tool):** Imprescindible para parsear artefactos.
* **APFS Fuse:** Driver para montar discos APFS en Linux.
* **OSXAuditor / OSX Collect:** Herramientas de auditoría y recolección.
* **MacLocationsScraper / macMRUParser:** Para geolocalización y listas de archivos recientes.

<br><br>


<a name="6-análisis-de-memoria-y-metadatos"></a>
<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=rect&color=ffffff&text=6.%20ANÁLISIS%20DE%20MEMORIA%20Y%20METADATOS&fontColor=000000&height=40&fontSize=22" width="100%"/>
</div>
<br>

**Análisis de Metadatos:** Los "datos sobre los datos". Revelan la historia del archivo (creación, modificación, acceso, autoría).

### <img src="https://img.icons8.com/ios/256/FFFFFF/brain.png" width="22" valign="middle"> Memoria RAM y Procesos

* **Volatility:** El framework líder para analizar volcados de memoria RAM (detectar malware, contraseñas, conexiones).
* **Rekall:** Fork de Volatility, enfocado en análisis de memoria.
* **MemProcFS:** Visualiza la memoria física como un sistema de archivos virtual.

### <img src="https://img.icons8.com/ios/256/FFFFFF/clipboard.png" width="22" valign="middle"> Metadatos y Hashing

* **Hashlookup:** Servicio para verificar hashes contra bases de datos de archivos conocidos (NSRL).
* **Laika BOSS:** Escáner de objetos y archivos intrusivos.

<br><br>


<a name="7-recuperación-de-datos-data-recovery"></a>
<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=rect&color=ffffff&text=7.%20RECUPERACIÓN%20DE%20DATOS%20(DATA%20RECOVERY)&fontColor=000000&height=40&fontSize=22" width="100%"/>
</div>
<br>

Herramientas para recuperar archivos borrados o de discos dañados (File Carving).

* **PhotoRec / TestDisk:** Open source, muy potentes para recuperar particiones y archivos crudos.
* **R-Studio:** (Comercial) Considerado uno de los mejores para recuperación lógica compleja.
* **Recuva:** Básico, bueno para recuperaciones sencillas en Windows.
* **DiskGenius / EaseUS:** Suites "todo en uno" para gestión de discos y recuperación.

<br><br>


<a name="8-suite-de-herramientas-dbx-utilidades-ligeras"></a>
<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=rect&color=ffffff&text=8.%20SUITE%20DE%20HERRAMIENTAS%20DBX&fontColor=000000&height=40&fontSize=22" width="100%"/>
</div>
<br>

_Colección de herramientas especializadas para tareas rápidas y precisas._

| Herramienta | Descripción y Funcionalidad |
| :--- | :--- |
| **dbxScreenshot** | **Captura Forense de Pantalla.** Captura con metadatos detallados (Timestamp UTC, Hash MD5/SHA, usuario, ID dispositivo) para preservar la cadena de custodia visual. |
| **dbxCsvViewer** | **Visor CSV Avanzado.** Soporta delimitadores complejos, carga rápida, ordenamiento y exportación directa a Excel (.xlsx). Ideal para logs masivos. |
| **dbxMetadata** | **Analizador de Atributos.** Muestra info del sistema de archivos (MAC times) y metadatos internos de diversos formatos. |
| **dbxSeqCheck** | _(En desarrollo)_ **Verificador de Secuencias.** Detecta huecos, duplicados o desorden en secuencias numéricas (útil para facturas, logs ID, etc.). |
| **dbxHashFile** | **Calculadora de Hashing.** Cálculo rápido y paralelo de hashes (MD5, SHA1, SHA256, etc.) para verificar integridad de ficheros. |

<br><br>


<a name="9-recursos-y-mejores-prácticas"></a>
<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=rect&color=ffffff&text=9.%20RECURSOS%20Y%20MEJORES%20PRÁCTICAS&fontColor=000000&height=40&fontSize=22" width="100%"/>
</div>
<br>

### <img src="https://img.icons8.com/ios/256/FFFFFF/books.png" width="22" valign="middle"> Guías y Protocolos (Must Read)

* **ENISA Digital Forensics Handbook:** La biblia europea de procedimientos.
* **SWGDE Best Practices:** Estándares del grupo de trabajo científico sobre evidencia digital.
* **Interpol Guidelines:** Guía para primeros intervinientes (First Responders).
* **RFC 3227:** Guía para la recolección de evidencia y orden de volatilidad.

### <img src="https://img.icons8.com/ios/256/FFFFFF/toolbox.png" width="22" valign="middle"> Herramientas Comerciales (Nivel Enterprise)

Si el presupuesto lo permite, estas son las herramientas estándar en cuerpos policiales y grandes firmas:

* **Cellebrite UFED:** Líder mundial en forense móvil.
* **Magnet AXIOM:** Excelente correlación de artefactos (móvil + PC + nube).
* **EnCase Forensic:** El software clásico de la industria, muy usado en entornos judiciales.

<br><br>

<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=ffffff&height=120&section=footer&text=The%20truth%20is%20in%20the%20data&fontSize=25&fontColor=000000&animation=twinkling&fontAlignY=70" width="100%"/>
</div>

<div align="center">
  <br>
  <sub>Desarrollado por <strong>Ph0e-Nyx</strong></sub>
  <br><br>
  <a href="#"><img src="https://img.shields.io/badge/Volver_al_inicio-000000?style=for-the-badge&logo=up-arrow&logoColor=white"></a>
</div>
