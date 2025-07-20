### **Objetivo** 
El alumno implementara bases de datos no relacionales en la nube a través de las herramientas no SQL, para integrarlas con aplicaciones multiplataforma.

-  Unidad 1 - Conceptos de bases de datos no relacionales orientadas a objetos y a documentos
-  Unidad 2 - Sistemas gestores de bases de datos no SQL
-  Unidad 3 - Administración de bases de datos no SQL
-  Unidad 4 - Introducción a las bases de datos avanzadas

### **Actividad 1**

| Estructurado          | No estructurado  |
| --------------------- | ---------------- |
| Código de barras      | Blogs            |
| Directorio telefónico | Fotos            |
| Factura de agua       | Musica           |
| Pagina web            | Tuits            |
| Archivo CSV           | Presentación PPT |
|                       | Archivo PDF      |

### **Actividad 2** 
#### **¿Qué es una base de datos?**
Es el lugar en donde se almacenan los registros o datos para poder ser administrados

#### **Elementos de una Base de Datos**
Tablas, Datos, Llave primaria, Llave foránea 

#### **Tipos de relaciones**

- 1 a 1
- 1 a muchos
- muchos a muchos

### **Actividad 3**
Investigar Bases de datos relacionales 
Ventajas: Experiencia y madurez, Atomicidad, Estandarización, Estructura simple
Desventajas: Dificultad de crecimiento, Cambios en la estructura, Complejidad de instalación 

### **Ventajas de las Bases de Datos Relacionales**

1. **Experiencia y Madurez**:
    - Llevan décadas en el mercado, con un sólido historial de uso en diversas industrias.
    - Amplio soporte por parte de comunidades, proveedores y estándares globales como SQL.
2. **Atomicidad (Propiedades ACID)**:
    - Garantizan transacciones seguras y confiables a través de las propiedades ACID:
        - **Atomicidad**: Las transacciones se completan por completo o no se aplican.
        - **Consistencia**: El sistema permanece en un estado válido después de las transacciones.
        - **Aislamiento**: Las transacciones no interfieren entre sí.
        - **Durabilidad**: Los datos confirmados persisten incluso tras fallos del sistema.
3. **Estandarización**:
    - Uso de SQL, un lenguaje estándar ampliamente aceptado y documentado.
    - Compatible con herramientas y aplicaciones en múltiples plataformas.
4. **Estructura Simple**:
    - Almacenan datos en tablas, un formato intuitivo que se asemeja a hojas de cálculo.
    - Ideal para datos altamente estructurados con relaciones claras.
### **Desventajas de las Bases de Datos Relacionales**

1. **Dificultad de Crecimiento**:
    - Escalabilidad limitada en comparación con bases de datos NoSQL.
    - La escalabilidad vertical.
    - No están diseñadas para manejar grandes volúmenes de datos distribuidos.
2. **Cambios en la Estructura**:
    - La modificación del esquema (como agregar columnas o relaciones) puede ser compleja y costosa, especialmente en sistemas grandes.
    - Puede requerir reestructuración de tablas y migración de datos.
3. **Complejidad de Instalación y Configuración**:
    - La implementación inicial puede requerir configuraciones avanzadas y experiencia técnica.
    - Su mantenimiento (como optimización de consultas o administración de índices) demanda conocimientos especializados.
#### **Actividad 4**
Investigar Bases de datos no relacionales 
Ventajas: Versatilidad, Crecimiento horizontal, Bajos requerimientos  Flexibilidad esquema

### **Ventajas de las Bases de Datos No Relacionales**

1. **Versatilidad**:
    
    - Pueden manejar diversos tipos de datos, como documentos JSON, grafos, matrices, pares clave-valor, entre otros.
    - Ideales para aplicaciones modernas, como redes sociales, análisis en tiempo real, IoT y big data.
2. **Crecimiento Horizontal**:
    
    - Diseñadas para escalar de forma horizontal, es decir, distribuyendo datos entre varios servidores en lugar de depender de un único servidor más potente.
    - Mejora el rendimiento y la capacidad sin grandes inversiones en hardware.
3. **Bajos Requerimientos**:
    
    - No necesitan un hardware sofisticado o especializado, lo que reduce los costos iniciales.
    - Los sistemas distribuidos permiten usar servidores más económicos.
4. **Flexibilidad en el Esquema**:
    
    - No requieren un esquema predefinido, lo que facilita agregar nuevos campos o tipos de datos sin afectar el rendimiento o requerir migraciones complicadas.
    - Ideal para proyectos con datos dinámicos o en constante evolución.

### **Desventajas de las Bases de Datos No Relacionales**

1. **Consistencia Relativa**:
    
    - Algunas bases NoSQL priorizan la disponibilidad y la partición sobre la consistencia (según el teorema CAP). Esto puede generar resultados no actualizados en entornos distribuidos.
2. **Curva de Aprendizaje**:
    
    - La falta de estandarización (como SQL en relacionales) puede dificultar el aprendizaje y la migración entre diferentes tecnologías NoSQL.
3. **Menor Soporte para Transacciones Complejas**:
    
    - No son ideales para aplicaciones que requieren operaciones altamente transaccionales, como sistemas bancarios.
4. **Gestión Avanzada Requerida**:
    
    - La configuración, particionamiento y sincronización de datos distribuidos puede ser compleja y demandar conocimientos avanzados.

