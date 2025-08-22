# Ciberlac LLM Security Practices 

## Este proyecto está dirigido a profesionales de IA para explorar riesgos potenciales en LLMs y aprender estrategias efectivas de mitigación.

## Resumen

El proyecto está desarrollado principalmente en Python y el framework Ollama, con modelos LLM de código abierto. Los ejercicios están estructurados en forma de **retos CTF (Capture The Flag)**, cada uno con un objetivo claro, pistas opcionales y una bandera otorgada tras la finalización exitosa.

## Primeros pasos

Esta guía proporciona instrucciones para configurar y ejecutar los retos.

### Requisitos previos

* Python 3.10 o superior  
* pip (instalador de paquetes de Python)  
* framework ollama  

### Configuración

#### 1. Clonar el repositorio.
```bash
git https://github.com/spachec0/ciberlac_practices.git
```

#### 2. Ir al directorio del reto.
```bash
cd ciberlac_practices
```

#### 3. Instalar las dependencias.
```bash
pip install -r requirements.txt
```

#### 4. Descargar y ejecutar Ollama

Descarga Ollama según tu sistema operativo desde [https://ollama.com/download](https://ollama.com/download)  

```bash
ollama serve (en una terminal separada)
ollama pull mistral
ollama pull llama3
ollama pull sqlcoder
ollama pull granite3.1-moe:1b
ollama pull granite3-guardian
```

#### 5. Acceder a la aplicación
```bash
python main.py
```
Accede a la aplicación en: [http://127.0.0.1:5000](http://127.0.0.1:5000)  

#### 6. Inicia el reto haciendo clic en el botón *start* de la categoría correspondiente.  

---

# Retos

Encuentra la bandera y aplica una estrategia de mitigación.

## 1. Prompt Injection

Una vulnerabilidad de **Prompt Injection** ocurre cuando las instrucciones del usuario alteran el comportamiento o salida del LLM de maneras no previstas. Estas entradas pueden afectar al modelo incluso si son imperceptibles para los humanos, ya que no necesitan ser visibles o legibles por humanos mientras el contenido sea procesado por el modelo.

Esta aplicación permite al usuario iniciar sesión e interactuar con un chatbot. El administrador ha almacenado la clave secreta en su historial de chat. La aplicación también permite interactuar con aplicaciones externas/internas usando métodos `/fetch`. 

### Objetivo del Reto 1
Usar técnicas de **Prompt Injection/Jailbreak** para obtener la clave secreta del administrador.  

URL de la aplicación: [http://127.0.0.1:5001](http://127.0.0.1:5001)  

**Pista:** La función de URL externa puede ayudar  

---

## 2. Data and Model Poisoning

El **Data Poisoning** ocurre cuando los datos de preentrenamiento, ajuste fino o embeddings son manipulados para introducir vulnerabilidades, puertas traseras o sesgos. Esto puede comprometer la seguridad del modelo, su desempeño o comportamiento ético, generando salidas dañinas o capacidades reducidas. Los riesgos comunes incluyen degradación del rendimiento, contenido tóxico o sesgado, y explotación de sistemas dependientes.

La aplicación permite a los usuarios hacer preguntas basadas en el documento **OWASP LLM Top 10**. Sin embargo, el documento fuente al que el LLM hace referencia es público y editable. Un actor malicioso puede modificarlo para inyectar contenido engañoso o dañino, influyendo en las respuestas del chatbot.

### Objetivo del Reto 2
Los participantes deben identificar cómo el comportamiento del modelo ha sido envenenado con datos manipulados y explotarlo para modificar las entradas del **LLM Top 10**, de forma que reemplace **LLM01**.  

URL de la aplicación: [http://127.0.0.1:5004](http://127.0.0.1:5004)  

**Pista:** Identifica la fuente  

---

## 3. Improper Output Handling

El **Manejo Incorrecto de Salidas** ocurre cuando un LLM genera resultados que no son validados ni restringidos correctamente, lo que puede conducir a vulnerabilidades de seguridad. Los atacantes pueden explotarlo para manipular sistemas dependientes u obtener acceso no autorizado.

Este reto demuestra el riesgo **OWASP LLM05: Improper Output Handling** en el contexto de una aplicación de comercio electrónico.  
Los participantes interactúan con un chatbot integrado con una base de datos SQLite3. Al registrarse, los usuarios reciben 0 créditos. Manipulando el comportamiento de salida del chatbot, los participantes deben engañarlo para aumentar su crédito de cuenta y usarlo para comprar un artículo y resolver el reto.

### Objetivo del Reto 3
Una vez registrado, inicias sesión con 0 créditos. Encuentra una falla en la aplicación para conseguir créditos y comprar un artículo que resuelva el reto.  

URL de la aplicación: [http://127.0.0.1:5005](http://127.0.0.1:5005)  

**Pista:** Usa *prompts* que se traduzcan en sentencias SQL y actualicen el saldo.  

---

## Compatibilidad 

Este proyecto actualmente soporta sistemas macOS y Linux.
