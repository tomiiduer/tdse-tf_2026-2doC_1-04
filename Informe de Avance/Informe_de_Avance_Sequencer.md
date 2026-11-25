# **Step Sequencer de Bajo Costo - Informe de Avance**

**Autores:** Joaquín Cardenas, Tomás Duer
**Padrones:** 112311, 112611
**Fecha:** 2do cuatrimestre 2026 (avance al 20/11)

A continuación se detalla el informe de avance del Trabajo Final basándose en los requisitos planteados en la Propuesta, utilizando un esquema de colores para definir el estado de cada punto:

| Estado | Descripción |
| :---: | :--- |
| 🟢 | Ya implementado / Completado |
| 🟡 | En proceso de implementación |
| 🔴 | No se implementará / Descartado o con retraso crítico |

### **1. Pantalla LCD**
| Req ID | Descripción | Estado |
| :--- | :--- | :---: |
| 1.1 | El sistema contará con una pantalla LCD para mostrar información de estado. | 🟡 |
| 1.2 | Al iniciar el sistema, se mostrará una pantalla de bienvenida por unos segundos. | 🟡 |
| 1.3 | Luego de la bienvenida, comenzará el modo "Loop principal" donde se mostrará por pantalla el BPM y el pitch. | 🟡 |
| 1.4 | Al entrar en modo "Set-up" se mostrará la nota del paso en el cual se está parado junto a la nueva nota seleccionada. | 🟡 |

### **2. Switch**
| Req ID | Descripción | Estado |
| :--- | :--- | :---: |
| 2.1 | El sistema contará con un switch que funcionará como interruptor de mute. | 🔴 |
| 2.2 | Con el switch en posición "mute", el parlante no reproducirá sonido en ningún modo. | 🔴 |
| 2.3 | Con el switch en posición "mute", el resto del sistema seguirá funcionando normalmente, lo que permite configurar cada paso en modo "Set-up" guiándose únicamente por las notas mostradas en el LCD. | 🔴 |

### **3. Potenciómetro**
| Req ID | Descripción | Estado |
| :--- | :--- | :---: |
| 3.1 | Al girar el potenciómetro se modificará el pitch de la secuencia. | 🟡 |

### **4. Encoder**
| Req ID | Descripción | Estado |
| :--- | :--- | :---: |
| 4.1 | Estando en modo "Loop principal", al presionar el Encoder el sistema cambiará de estado a modo "Set-Up". | 🟡 |
| 4.2 | Estando en modo "Set-Up", al presionar el Encoder se avanza en la lista de pasos a configurar hasta llegar al octavo paso. | 🟡 |
| 4.3 | Una vez superado el octavo paso, se guardará la configuración y volverá al modo "Loop Principal". | 🟡 |
| 4.4 | Estando en modo "Loop Principal", al girar el encoder se modificará el BPM de la secuencia. | 🟡 |
| 4.5 | Estando en modo "Set-Up", al girar el Encoder se modificará la nota del paso en el que se está parado. | 🟡 |

### **5. Interfaz LED**
| Req ID | Descripción | Estado |
| :--- | :--- | :---: |
| 5.1 | El conjunto de 8 LEDs representan los 8 pasos de la secuencia. | 🟡 |
| 5.2 | En modo "Set-Up" solo se mantendrá encendido el LED asignado al paso que esté siendo modificado en ese momento. | 🟡 |
| 5.3 | En modo "Loop Principal" se irán encendiendo los LEDs a medida que avanza la secuencia indicando en qué paso se encuentra. | 🟡 |

### **6. Parlante**
| Req ID | Descripción | Estado |
| :--- | :--- | :---: |
| 6.1 | En modo "Set-Up", una vez seleccionado el paso a modificar, irán sonando las notas a medida que se gira el encoder de selección. | 🔴 |
| 6.2 | En modo "Loop principal", sonarán las notas a medida que avanza la secuencia. | 🔴 |

### **7. Almacenamiento**
| Req ID | Descripción | Estado |
| :--- | :--- | :---: |
| 7.1 | La configuración de notas/silencios y el tempo se guardarán en la memoria flash del microcontrolador. | 🟡 |
| 7.2 | Al iniciar, el sistema recuperará la configuración guardada en la sesión anterior. | 🟡 |

### **8. Secuencia**
| Req ID | Descripción | Estado |
| :--- | :--- | :---: |
| 8.1 | Cada uno de los 8 pasos almacenará una nota o un silencio. | 🟡 |
| 8.2 | La secuencia se reproducirá en bucle, paso a paso, al tempo (BPM) configurado. | 🟡 |

### **Observaciones**

- **Parlante (6.1, 6.2):** se eliminó la implementación del parlante. Se incorporó un conector hembra MIDI DIN (`TX`: PB10); la librería MIDI está pendiente.
- **Switch de mute (2.1 a 2.3):** el switch no figura en la lista de componentes seleccionados.
- **Avance realizado:** selección de pines en `.ioc`, statecharts (display, perilla y botón del encoder, menú Set-Up), selección de bibliotecas a reutilizar, plan de desarrollo, librería de Encoder con flujo de encolado de eventos, y adaptación de la librería LCD de paralelo a I2C.
- **Pendientes próxima semana:** librería MIDI y `task_sensor`.
