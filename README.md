# Proyecto final

En este repositorio se encuentra un programa que sirve para jugar el juego del ahorcado.
Este juego tiene ciertas características, como por ejemplo:
* Soporta hasta 3 idiomas (Español, inglés y alemán).
* Tiene 3 niveles de dificultad por cada idioma (Fácil, medio, difícil).

¿Bajo qué criterios se maneja el nivel de dificultad?

* Fácil: El usuario tiene 7 intentos para adivinar la palabra, y sólo saldrán palabras con una longitud de menos de 6 caracteres.
* Medio: El usuario tiene 7 intentos para adivinar la palabra, y sólo saldrán palabras con una longitud de entre 6 y 7 caracteres.
* Difícil: El usuario tiene 5 intentos para adivinar la palabra, y sólo saldrán palabras de más de 7 caracteres.

Aplica el mismo nivel de dificultad para los 3 idiomas.

Este programa tiene una base de datos de 884 palabras en español, 275 en inglés y 241 en alemán, para un total de 1400 palabras.

```python
import random ##Importante para seleccionar aleatoriamente una palabra de las listas y diccionarios dados.
##Instrucciones del programa.
def instrucciones(): ##Esta función sirve para indicarle las reglas al usuario.
    print("¡Hola, vamos a jugar al ahorcado!")
    print("===========================================================================================================================================")
    print("Antes de iniciar, le voy a mencionar las reglas del juego.")
    print("===========================================================================================================================================")
    print("1. Este juego se puede configurar en 3 idiomas (Español, alemán o inglés).")
    print("2. Cada idioma tendrá 3 niveles de dificultad (Fácil, medio y difícil).")
    print("   En el nivel fácil usted tendrá 7 intentos para adivinar la palabra y sólo saldrán palabras de 5 letras o menos.")
    print("   En el nivel medio, usted tendrá 6 intentos para adivinar la palabra y sólo saldrán palabras de 6 o 7 letras.")
    print("   En el nivel difícil, usted tendrá 5 intentos para adivinar la palabra y sólo saldrán palabras de más de 7 letras.")

def idioma(): ##Esta función se encarga de almacenar la lista de palabras en español, y los diccionarios de palabras en inglés y alemán.
    ##Además, esta función sirve para que el usuario escoja en qué idioma desea jugar.
    palabras_ingles = {
    "arise": "surgir, levantarse",
    "awake": "despertar",
    "be": "ser/estar",
    "bear": "soportar/llevar",
    "beat": "golpear/vencer",
    "become": "convertirse en",
    "begin": "empezar",
    "bend": "doblar",
    "bet": "apostar",
    "bid": "ofrecer/pujar",
    "bind": "atar/unir",
    "bite": "morder",
    "bleed": "sangrar",
    "blow": "soplar",
    "break": "romper",
    "breed": "criar",
    "bring": "traer",
    "build": "construir",
    "burn": "quemar",
    "burst": "estallar",
    "buy": "comprar",
    "cast": "lanzar/echar",
    "catch": "atrapar",
    "choose": "elegir",
    "cling": "aferrarse",
    "come": "venir",
    "cost": "costar",
    "creep": "arrastrarse",
    "cut": "cortar",
    "deal": "tratar",
    "dig": "cavar",
    "do": "hacer",
    "draw": "dibujar",
    "dream": "soñar",
    "drink": "beber",
    "drive": "conducir",
    "eat": "comer",
    "fall": "caer",
    "feed": "alimentar",
    "feel": "sentir",
    "fight": "pelear/luchar",
    "find": "encontrar",
    "fit": "encajar/ajustar",
    "flee": "huir",
    "fling": "lanzar",
    "fly": "volar",
    "forbid": "prohibir",
    "forecast": "predecir",
    "forget": "olvidar",
    "forgive": "perdonar",
    "forsake": "abandonar",
    "freeze": "congelar",
    "get": "obtener",
    "give": "dar",
    "go": "ir",
    "grind": "moler",
    "grow": "crecer",
    "hang": "colgar",
    "have": "tener",
    "hear": "escuchar/oir",
    "hide": "esconderse",
    "hit": "golpear",
    "hold": "sostener/agarrar",
    "hurt": "lastimar",
    "keep": "mantener",
    "kneel": "arrodillarse",
    "knit": "tejer",
    "know": "saber/conocer",
    "lay": "poner",
    "lead": "llevar/guía",
    "lean": "inclinarse/apoyar",
    "leap": "saltar",
    "learn": "aprender",
    "leave": "dejar/abandonar",
    "lend": "prestar",
    "let": "permitir/dejar",
    "lie": "mentir/recostarse",
    "light": "encender/iluminar",
    "lose": "perder",
    "make": "hacer/fabricar",
    "mean": "significar",
    "meet": "encontrar/conocer",
    "mow": "cortar (césped)",
    "pay": "pagar",
    "put": "poner/colocar",
    "read": "leer",
    "rid": "librar/desembarazarse",
    "ride": "montar/pasear",
    "ring": "llamar/sonar",
    "rise": "elevarse",
    "run": "correr",
    "saw": "serrar",
    "say": "decir",
    "see": "ver",
    "seek": "buscar",
    "sell": "vender",
    "send": "enviar",
    "set": "establecer/fijar",
    "shake": "agitar",
    "shave": "afeitar",
    "shear": "esquilar",
    "shed": "derramar",
    "shine": "brillar",
    "shoe": "calzar",
    "shoot": "disparar",
    "show": "mostrar",
    "shrink": "encoger",
    "shut": "cerrar",
    "sing": "cantar",
    "sink": "hundir",
    "sit": "sentarse",
    "slay": "matar",
    "sleep": "dormir",
    "slide": "deslizar",
    "sling": "lanzar",
    "slink": "deslizarse/escabullirse",
    "slit": "cortar/rasgar",
    "smell": "oler",
    "sneak": "espiar/acechar",
    "sow": "sembrar",
    "speak": "hablar",
    "speed": "acelerar",
    "spell": "deletrear",
    "spend": "gastar/pasar",
    "spill": "derramar",
    "spin": "girar/hilvanar",
    "spit": "escupir",
    "split": "partir/dividir",
    "spoil": "estropear/arruinar",
    "spread": "extender/difundir",
    "spring": "saltar",
    "stand": "estar de pie",
    "steal": "robar",
    "stick": "pegar",
    "sting": "picar",
    "stink": "apestar",
    "strew": "esparcir",
    "stride": "andar a zancadas",
    "strike": "golpear/atacar",
    "string": "atar/enlazar",
    "strive": "esforzarse",
    "swear": "jurar/maldecir",
    "sweep": "barrer",
    "swell": "hinchar/aumentar",
    "swim": "nadar",
    "swing": "balancear",
    "take": "tomar",
    "teach": "enseñar",
    "tear": "rasgar",
    "tell": "decir/contar",
    "think": "pensar",
    "thrive": "prosperar",
    "throw": "lanzar/tirar",
    "thrust": "empujar/embestir",
    "tread": "pisar",
    "understand": "entender/comprender",
    "wake": "despertar",
    "wear": "usar/llevar",
    "weave": "tejer",
    "wed": "casarse",
    "weep": "llorar",
    "wet": "mojar",
    "win": "ganar",
    "wind": "enrollar",
    "withdraw": "retirar",
    "withhold": "retener",
    "withstand": "resistir/aguantar",
    "wring": "exprimir/torcer",
    "write": "escribir",
    "abide": "permanecer",
    "beget": "engendrar",
    "behold": "contemplar",
    "bereave": "despojar",
    "beseech": "suplicar",
    "beset": "asediar",
    "bespeak": "indicar/encargar",
    "broadcast": "transmitir",
    "can": "poder",
    "able": "tener el poder, habilidad o medios para hacer algo",
    "acidic": "tener un pH menor que 7, sabor agrio",
    "adorable": "inspirar gran afecto; encantador",
    "adventurous": "dispuesto a correr riesgos o probar nuevos métodos, ideas o experiencias",
    "aggressive": "listo o propenso a atacar o enfrentar; caracterizado por o resultante de la agresión",
    "agreeable": "agradable; agradable",
    "alert": "vigilante y listo para actuar o reaccionar",
    "alive": "tener vida; vivo; no muerto",
    "amused": "entretenido o encontrar algo divertido",
    "amazing": "causando gran sorpresa o asombro; asombroso",
    "angry": "tener fuertes sentimientos de desagrado o hostilidad",
    "annoyed": "leve enfado; irritado",
    "annoying": "causar irritación o molestia",
    "anxious": "sentirse preocupado, nervioso o inquieto",
    "arrogant": "tener un sentido exagerado de la propia importancia o habilidades",
    "ashamed": "sentir vergüenza o culpa; avergonzado o arrepentido",
    "attractive": "agradar a los sentidos o la mente; atractivo; encantador",
    "average": "típico; normal; no destacado o especial",
    "awful": "muy malo o desagradable; terrible",
    "bad": "no bueno; pobre; desfavorable",
    "beautiful": "agradar a los sentidos o la mente; atractivo; encantador",
    "better": "de un tipo o calidad más excelente o efectiva",
    "bewildered": "completamente desconcertado o confundido",
    "big": "de considerable tamaño, extensión o intensidad",
    "bitter": "tener un sabor o olor agudo y punzante; resentido o cínico",
    "black": "del color más oscuro debido a la ausencia o absorción completa de luz",
    "blue": "tener el color del cielo claro o del mar profundo",
    "boiling": "extremadamente caliente; en proceso de ebullición",
    "bold": "mostrar disposición para correr riesgos; confiado y valiente",
    "bored": "sentirse cansado e interesado por la falta de cambio o emoción",
    "boring": "no interesante o estimulante; aburrido y tedioso",
    "brave": "listo para enfrentar y soportar peligros o dolor; valiente",
    "bright": "emitiendo o reflejando mucha luz; inteligente y perspicaz",
    "busy": "tener mucho que hacer; ocupado o concentrado en algo",
    "calm": "no mostrar o sentir nerviosismo, ira u otras emociones",
    "careful": "ejercer precaución o prestar atención a los detalles",
    "cautious": "cuidadoso para evitar problemas o peligros potenciales",
    "charming": "agradable o atractivo; encantador",
    "cheerful": "notablemente feliz y optimista",
    "chilly": "incómodamente fresco o frío",
    "clean": "libre de suciedad, marcas o manchas",
    "clear": "fácil de percibir, entender o interpretar",
    "clever": "rápido para entender, aprender y idear o aplicar ideas; inteligente",
    "cloudy": "cubierto u oscurecido por nubes",
    "clumsy": "torpe en movimiento o en manejar cosas",
    "colorful": "tener mucho o variado color; brillante y llamativo",
    "combative": "listo o ansioso por pelear o discutir",
    "comfortable": "proporcionar comodidad física y relajación",
    "concerned": "preocupado, preocupado o ansioso",
    "condemned": "fuertemente desaprobado; condenado a un destino particular",
    "confused": "incapaz de pensar claramente o entender",
    "cooperative": "involucrar asistencia mutua o trabajar juntos hacia un objetivo común",
    "courageous": "no disuadido por peligro o dolor; valiente",
    "crazy": "mentalmente trastornado; extremadamente entusiasta",
    "creepy": "causando una desagradable sensación de miedo o malestar",
    "crowded": "lleno de gente o cosas, dejando poco o ningún espacio para el movimiento",
    "cruel": "causar intencionalmente dolor o sufrimiento a otros, o no sentir preocupación por ello",
    "curious": "ansioso por saber o aprender algo",
    "cute": "atractivo de una manera bonita o entrañable",
    "dangerous": "capaz o probable de causar daño o lesiones",
    "dark": "tener muy poca o ninguna luz",
    "dead": "no vivo",
    "defeated": "derrotado en una competencia o lucha",
    "defiant": "mostrar desafío",
    "delightful": "muy agradable o entretenido",
    "depressed": "en un estado de infelicidad general o desesperación",
    "determined": "haber tomado una decisión firme y estar resuelto a no cambiarla",
    "disgusted": "sentir repulsión o desaprobación profunda",
    "distinct": "reconociblemente diferente en la naturaleza de algo más de un tipo similar",
    "disturbed": "habiendo tenido su patrón o función normal interrumpida",
    "dizzy": "tener una sensación de vértigo y una tendencia a caer o tambalearse",
    "doubtful": "sentirse incierto sobre algo",
    "drab": "carecer de brillo o interés; aburrido",
    "dull": "carecer de interés o emoción",
    "eager": "querer hacer o tener algo mucho",
    "easy": "logrado sin gran esfuerzo; presentar pocos problemas",
    "elated": "extremadamente feliz y emocionado",
    "elegant": "agradablemente elegante y con estilo en apariencia o manera",
    "embarrassed": "sentirse incómodo, cohibido o avergonzado",
    "enchanting": "encantadoramente encantador o atractivo",
    "encouraging": "dar apoyo, confianza o esperanza a alguien",
    "energetic": "mostrar o involucrar una gran actividad o vitalidad",
    "enthusiastic": "mostrar un disfrute, interés o aprobación intenso y ansioso",
    "envious": "sentir o mostrar envidia",
    "evil": "profundamente inmoral y malévolo",
    "excited": "muy entusiasta y ansioso",
    "expensive": "costar mucho dinero",
    "exuberant": "lleno o caracterizado por una energía y emoción animada",
    "fair": "tratar a las personas de manera equitativa sin favoritismo o discriminación",
    "faithful": "leal, constante y firme",
    "famous": "conocido por muchas personas",
    "fancy": "elaborado en estructura o decoración",
    "fantastic": "extraordinariamente bueno o atractivo",
    "fierce": "tener o mostrar una agresividad violenta o feroz",
    "filthy": "asquerosamente sucio",
    "fine": "de muy alta calidad; muy bueno de su tipo",
    "foolish": "falta de buen sentido o juicio"
}
    
    palabras_español = [
    "hola", "casa", "perro", "gato", "amarillo", "azul", "rojo", "verde", "naranja", "jugar",
    "correr", "saltar", "nadar", "montaña", "playa", "ciudad", "campo", "bosque", "desierto",
    "flor", "árbol", "planta", "sol", "luna", "estrella", "nube", "lluvia", "viento", "nieve",
    "fuego", "agua", "tierra", "aire", "calor", "frío", "luz", "oscuridad", "feliz", "triste",
    "enojado", "asustado", "sorpresa", "cansado", "hambriento", "sediento", "grande", "pequeño",
    "alto", "bajo", "largo", "corto", "rápido", "lento", "nuevo", "viejo", "bueno", "malo",
    "bonito", "feo", "limpio", "sucio", "alegre", "triste", "amor", "odio", "familia", "amigo",
    "viaje", "aventura", "fantasía", "realidad", "historia", "libro", "escuela", "universidad",
    "aprender", "enseñar", "estudiar", "trabajar", "descansar", "vacaciones", "fiesta", "celebrar",
    "juego", "música", "arte", "pintura", "escultura", "danza", "teatro", "película", "televisión",
    "internet", "computadora", "teléfono", "redes", "sociales", "tecnología", "innovación", "futuro",
    "pasado", "presente", "mañana", "tarde", "noche", "día", "hora", "minuto", "segundo", "reloj",
    "calendario", "mes", "año", "siglo", "decada", "ciclo", "número", "forma", "color", "tamaño",
    "peso", "altura", "ancho", "largo", "profundidad", "superficie", "volumen", "figura", "circulo",
    "cuadrado", "triángulo", "rectángulo", "hexágono", "octágono", "esfera", "cubo", "pirámide",
    "cilindro", "cono", "estrella", "planeta", "galaxia", "universo", "humano", "animal", "planta",
    "insecto", "mamífero", "reptil", "ave", "pez", "ser humano", "niño", "niña", "hombre", "mujer",
    "adulto", "anciano", "joven", "adolescente", "infancia", "juventud", "vejez", "vida", "muerte",
    "nacer", "crecer", "envejecer", "morir", "vivir", "respirar", "comer", "beber", "dormir",
    "soñar", "despertar", "trabajar", "descansar", "divertirse", "aprender", "enseñar", "comprender",
    "pensar", "sentir", "emoción", "razón", "instinto", "intuición", "conocimiento", "ignorancia",
    "verdad", "mentira", "realidad", "fantasía", "imaginación", "creatividad", "arte", "ciencia",
    "matemáticas", "física", "química", "biología", "geografía", "historia", "lenguaje", "literatura",
    "poesía", "filosofía", "religión", "cultura", "tradición", "costumbre", "valor", "ética", "moraleja",
    "justicia", "paz", "guerra", "conflicto", "problema", "solución", "desafío", "éxito", "fracaso",
    "logro", "objetivo", "meta", "camino", "destino", "viaje", "aventura", "desarrollo", "cambio",
    "transformación", "revolución", "evolución", "progreso", "crecimiento", "mejora", "deterioro",
    "destrucción", "construcción", "innovación", "descubrimiento", "exploración", "viaje", "espacio",
    "tiempo", "mundo", "naturaleza", "sociedad", "cultura", "economía", "política", "tecnología",
    "globalización", "comunicación", "interacción", "relación", "amor", "odio", "amistad", "enemistad",
    "pasión", "interés", "indiferencia", "emoción", "sentimiento", "pensamiento", "acción", "reacción",
    "elección", "decisión", "libertad", "responsabilidad", "derecho", "deber", "obligación", "ética",
    "moral", "ética", "virtud", "vicio", "belleza", "fealdad", "armonía", "caos", "orden", "desorden",
    "equilibrio", "desequilibrio", "sorpresa", "rutina", "normalidad", "excepción", "riesgo", "seguridad",
    "peligro", "azar", "destino", "azar", "casualidad", "fortuna", "suerte", "infortunio", "misterio",
    "secreto", "revelación", "conocimiento", "ignorancia", "aprendizaje", "enseñanza", "maestro",
    "alumno", "educación", "instrucción", "aprendizaje", "conocimiento", "sabiduría", "ignorancia",
    "error", "acertijo", "enigma", "puzzle", "duda", "certeza", "verdad", "montaña", "río", "oceano", "isla", "continente", "país", "nación", "frontera", "límite", "territorio",
    "naturaleza", "biodiversidad", "ecosistema", "ciclo", "ecología", "sostenibilidad", "contaminación",
    "reciclaje", "reutilización", "renovable", "energía", "biología", "fisiología", "anatomía", "célula",
    "orgánulo", "tejido", "órgano", "sistema", "nutrición", "respiración", "circulación", "digestión",
    "excreción", "sistema", "inmunológico", "hormonas", "genética", "ADN", "ARN", "gen", "herencia",
    "mutación", "evolución", "adaptación", "especie", "reproducción", "sexual", "asexual", "embrión",
    "feto", "infancia", "niñez", "adolescencia", "juventud", "adultez", "vejez", "longevidad", "vida",
    "muerte", "nacimiento", "maternidad", "paternidad", "crianza", "educación", "escuela", "colegio",
    "universidad", "aprendizaje", "enseñanza", "maestro", "profesor", "alumno", "estudiante", "examen",
    "prueba", "conocimiento", "ciencia", "investigación", "descubrimiento", "invención", "tecnología",
    "innovación", "progreso", "cambio", "transformación", "revolución", "avance", "logro", "éxito",
    "fracaso", "error", "acierto", "acierto", "talento", "habilidad", "destreza", "capacidad", "aptitud",
    "competencia", "talento", "creatividad", "imaginación", "pensamiento", "razonamiento", "lógica",
    "inteligencia", "intuición", "sentido", "propósito", "meta", "objetivo", "plan", "estrategia",
    "acción", "realización", "ejecución", "logro", "éxito", "fracaso", "obstáculo", "desafío", "esfuerzo",
    "perseverancia", "dedicación", "pasión", "compromiso", "voluntad", "determinación", "valentía",
    "coraje", "miedo", "temor", "ansiedad", "esperanza", "optimismo", "pesimismo", "confianza", "duda",
    "seguridad", "inseguridad", "certeza", "incertidumbre", "expectativa", "sorpresa", "asombro",
    "maravilla", "rutina", "normalidad", "comodidad", "confort", "incomodidad", "disconfort", "presión",
    "estrés", "relajación", "calma", "serenidad", "tranquilidad", "paz", "conflicto", "tensión", "calor",
    "frío", "temperatura", "clima", "estación", "verano", "otoño", "invierno", "primavera", "nublado",
    "soleado", "lluvioso", "nevado", "ventoso", "tormentoso", "húmedo", "seco", "fresco", "cálido",
    "caluroso", "frío", "helado", "habitación", "espacio", "lugar", "casa", "hogar", "vivienda", "edificio",
    "estructura", "arquitectura", "diseño", "construcción", "renovación", "reparación", "mantenimiento",
    "decoración", "mobiliario", "mueble", "objeto", "artículo", "utensilio", "herramienta", "instrumento",
    "equipo", "aparato", "máquina", "mecanismo", "motor", "generador", "energía", "electricidad", "luz",
    "sonido", "ruido", "silencio", "ruido", "ritmo", "melodía", "música", "canción", "instrumento",
    "composición", "interpretación", "presentación", "espectáculo", "actuación", "teatro", "danza",
    "baile", "coreografía", "director", "actor", "actriz", "danza", "bailarín", "bailarina", "público",
    "audiencia", "espectador", "televisión", "radio", "cine", "película", "serie", "programa", "anuncio",
    "publicidad", "documental", "información", "noticia", "reportaje", "entrevista", "debate", "conversación",
    "charla", "diálogo", "monólogo", "discusión", "opinión", "pensamiento", "idea", "concepto", "término",
    "palabra", "lenguaje", "idioma", "alfabeto", "gramática", "vocabulario", "diccionario", "significado",
    "traducción", "interpretación", "comunicación", "mensaje", "texto", "escritura", "lectura", "autor",
    "escritor", "poeta", "novelista", "periodista", "editor", "copia", "original", "copia", "versión",
    "edición", "libro", "publicación", "periódico", "revista", "prensa", "editorial", "imprenta", "papel",
    "tinta", "pluma", "lápiz", "bolígrafo", "rotulador", "marcador", "cuaderno", "libreta", "agenda",
    "archivos", "carpeta", "documento", "expediente", "informe", "información", "datos", "estadísticas",
    "gráficos", "diagrama", "tabla", "índice", "resumen", "apéndice", "anexo", "referencia", "ítem",
    "punto", "tema", "asunto", "título", "encabezado", "introducción", "desarrollo", "conclusión", "fin",
    "inicio", "principio", "final", "parte", "sección", "capítulo", "párrafo", "oración", "palabra",
    "letra", "espacio", "signo", "puntuación", "mayúscula", "minúscula", "acentuación", "ortografía",
    "gramática", "sintaxis", "semántica", "fonética", "fonología", "pronunciación", "entendimiento",
    "comprensión", "interpretación", "interpretación", "comprensión", "entendimiento", "significado",
    "conocimiento", "ignorancia", "aprendizaje", "enseñanza", "instrucción", "educación", "pedagogía",
    "didáctica", "maestro", "profesor", "alumno", "estudiante", "examen", "prueba", "evaluación",
    "calificación", "nota", "grado", "aprobado", "reprobado", "sobresaliente", "suficiente", "insuficiente",
    "promedio", "media", "desviación", "variación", "progresión", "regresión", "avance", "retroceso",
    "mejora", "deterioro", "desarrollo", "cambio", "transformación", "revolución", "evolución", "adaptación",
    "evolución", "mutación", "selección", "selección", "selección", "genética", "variabilidad", "variación",
    "modificación", "conformación", "comportamiento", "conducta", "acción", "reacción", "interacción",
    "comunicación", "relación", "asociación", "vinculación", "alianza", "asociación", "relación", "relación",
    "correlación", "correspondencia", "conexión", "integración", "interconexión", "independencia",
    "dependencia", "interdependencia", "autonomía", "independencia", "libertad", "soberanía", "autoridad",
    "control", "poder", "dominio", "influencia", "dominio", "administración", "gobierno", "gestión",
    "dirección", "liderazgo", "autoridad", "mandato", "regulación", "normativa", "control", "control",
    "manejo", "ejecución", "cumplimiento", "aplicación", "realización", "práctica", "ejercicio", "hábito",
    "costumbre", "rutina", "normalidad", "excepción", "excepción", "novedad", "originalidad", "singularidad",
    "diferencia", "diversidad", "variedad", "multitud", "abundancia", "plurales", "pluralidad", "totalidad",
    "integración", "conjunto", "suma", "total", "comunidad", "sociedad", "colectividad", "población",
    "demografía", "grupo", "equipo", "banda", "tribu", "familia", "clan", "linaje", "ancestros", "ancestro",
    "descendencia", "herencia", "herederos", "heredero", "sucesión", "legado", "patrimonio", "tradición",
    "costumbre", "ritual", "ceremonia", "ritual", "celebración", "fiesta", "evento", "acontecimiento",
    "incidente", "situación", "ocasión", "circunstancia", "condición", "contexto", "entorno", "ambiente",
    "atmósfera", "clima", "clima", "estado", "condición", "naturaleza", "esencia", "carácter", "identidad",
    "esencia", "carácter", "identidad", "personalidad", "individuo", "persona", "ser", "entidad", "existencia",
    "existencia", "vida", "alma", "mente", "cuerpo", "espíritu", "corazón", "mente", "cabeza", "conciencia",
    "subconsciente", "conocimiento", "sabiduría", "conocimiento", "verdad", "realidad", "fantasticamente"
]
    
    palabras_aleman = {
    "haben": "tener",
    "sein": "ser/estar",
    "werden": "convertirse",
    "können": "poder",
    "machen": "hacer",
    "sagen": "decir",
    "geben": "dar",
    "kommen": "venir",
    "wollen": "querer",
    "gehen": "ir",
    "sehen": "ver",
    "lassen": "dejar",
    "stehen": "estar de pie",
    "finden": "encontrar",
    "liegen": "yacer",
    "bleiben": "quedarse",
    "bringen": "traer",
    "halten": "mantener",
    "denken": "pensar",
    "nehmen": "tomar",
    "tun": "hacer",
    "sollen": "deber",
    "führen": "llevar",
    "müssen": "deber (necesidad)",
    "sprechen": "hablar",
    "glauben": "creer",
    "leben": "vivir",
    "arbeiten": "trabajar",
    "fahren": "viajar/conducir",
    "spielen": "jugar",
    "bekommen": "recibir",
    "scheinen": "parecer",
    "lesen": "leer",
    "bedeuten": "significar",
    "folgen": "seguir",
    "erhalten": "obtener",
    "heißen": "llamarse",
    "beginnen": "empezar",
    "verstehen": "entender",
    "setzen": "poner",
    "mögen": "gustar",
    "gewinnen": "ganar",
    "verlieren": "perder",
    "entwickeln": "desarrollar",
    "zeigen": "mostrar",
    "interessieren": "interesar",
    "fragen": "preguntar",
    "brauchen": "necesitar",
    "wissen": "saber",
    "laufen": "correr",
    "bleiben": "quedarse",
    "ändern": "cambiar",
    "handeln": "actuar",
    "besuchen": "visitar",
    "schreiben": "escribir",
    "versuchen": "intentar",
    "treffen": "encontrarse",
    "hoffen": "esperar",
    "fühlen": "sentir",
    "verbinden": "conectar",
    "verlassen": "abandonar",
    "lernen": "aprender",
    "entscheiden": "decidir",
    "erklären": "explicar",
    "erinnern": "recordar",
    "gestalten": "dar forma",
    "verstärken": "reforzar",
    "halten": "sostener",
    "bewegen": "mover",
    "erzählen": "contar",
    "untersuchen": "investigar",
    "freuen": "alegrarse",
    "schaffen": "crear",
    "erfüllen": "cumplir",
    "verstehen": "comprender",
    "brauchen": "necesitar",
    "funktionieren": "funcionar",
    "vorstellen": "presentar",
    "teilnehmen": "participar",
    "aufhören": "parar",
    "steigen": "subir",
    "prüfen": "examinar",
    "verändern": "cambiar",
    "genießen": "disfrutar",
    "ergänzen": "complementar",
    "vergleichen": "comparar",
    "entschuldigen": "disculpar",
    "aussehen": "parecer",
    "sichern": "asegurar",
    "behalten": "conservar",
    "übernehmen": "asumir",
    "gründen": "fundar",
    "vorbeugen": "prevenir",
    "schließen": "cerrar",
    "einladen": "invitar",
    "überzeugen": "convencer",
    "entspannen": "relajarse",
    "beantworten": "responder",
    "ersetzen": "reemplazar",
    "verhindern": "prevenir",
    "beobachten": "observar",
    "übersetzen": "traducir",
    "ausdrücken": "expresar",
    "kosten": "costar",
    "ergreifen": "tomar",
    "zusammenarbeiten": "trabajar juntos",
    "stecken": "meter",
    "sichern": "asegurar",
    "empfehlen": "recomendar",
    "verstehen": "entender",
    "abschließen": "terminar",
    "erzielen": "lograr",
    "schneiden": "cortar",
    "wechseln": "cambiar",
    "akzeptieren": "aceptar",
    "kennen": "conocer",
    "anbieten": "ofrecer",
    "abhalten": "celebrar",
    "verbringen": "pasar (tiempo)",
    "einstellen": "contratar",
    "zählen": "contar",
    "auswählen": "seleccionar",
    "unterstützen": "apoyar",
    "umsetzen": "implementar",
    "einsetzen": "utilizar",
    "versorgen": "proveer",
    "feiern": "celebrar",
    "überwinden": "superar",
    "tragen": "llevar/vestir",
    "überprüfen": "verificar",
    "hören": "escuchar",
    "anfangen": "empezar",
    "erwarten": "esperar",
    "bedienen": "servir/manejar",
    "verstärken": "reforzar",
    "versprechen": "prometer",
    "abbrechen": "cancelar",
    "veröffentlichen": "publicar",
    "erscheinen": "aparecer",
    "vergleichen": "comparar",
    "einrichten": "instalar",
    "beschreiben": "describir",
    "aufzeigen": "demostrar",
    "diskutieren": "discutir",
    "abbilden": "representar",
    "teilen": "compartir/dividir",
    "vorbeikommen": "pasar por",
    "begegnen": "encontrarse con",
    "erarbeiten": "elaborar",
    "umgehen": "manejar",
    "ergänzen": "complementar",
    "beeinflussen": "influir",
    "zusammenkommen": "reunirse",
    "verbessern": "mejorar",
    "erweitern": "expandir",
    "schützen": "proteger",
    "unterscheiden": "distinguir",
    "abgeben": "entregar",
    "wählen": "elegir",
    "zurechtkommen": "arreglárselas",
    "schützen": "proteger",
    "sichern": "asegurar",
    "ankommen": "llegar",
    "zusammenführen": "unir",
    "ausführen": "ejecutar",
    "bewerten": "evaluar",
    "zusammenstellen": "compilar",
    "vereinbaren": "acordar",
    "beinhalten": "incluir",
    "bewahren": "preservar",
    "durchführen": "realizar",
    "aufnehmen": "grabar",
    "bezeichnen": "designar",
    "ersetzen": "reemplazar",
    "austauschen": "intercambiar",
    "abstimmen": "votar",
    "ausführen": "realizar",
    "erfüllen": "cumplir",
    "ausgeben": "gastar",
    "entstehen": "originar",
    "bestehen": "existir",
    "umfassen": "abarcar",
    "beeinflussen": "influir",
    "begleiten": "acompañar",
    "aufbauen": "construir",
    "verbinden": "conectar",
    "bilden": "formar",
    "abgeben": "entregar",
    "abfahren": "partir",
    "bedecken": "cubrir",
    "anpassen": "adaptar",
    "bezeichnen": "denominar",
    "sichern": "asegurar",
    "berücksichtigen": "tener en cuenta",
    "bewegen": "mover",
    "betreiben": "operar",
    "abgeben": "entregar",
    "abstellen": "apagar",
    "befolgen": "seguir",
    "befassen": "ocuparse de",
    "abgeben": "emitir",
    "erstellen": "crear",
    "anpassen": "ajustar",
    "beraten": "asesorar",
    "abfragen": "consultar",
    "abbrechen": "cancelar",
    "abholen": "recoger",
    "abkürzen": "acortar",
    "absagen": "cancelar",
    "abstimmen": "coordinar",
    "abwickeln": "gestionar",
    "anbieten": "ofrecer",
    "ankündigen": "anunciar",
    "anmelden": "inscribirse",
    "anpassen": "ajustar",
    "anrufen": "llamar",
    "antworten": "responder",
    "ausfüllen": "rellenar",
    "auslösen": "desencadenar",
    "ausschließen": "excluir",
    "auswählen": "seleccionar",
    "auswirken": "afectar",
    "beantragen": "solicitar",
    "bedauern": "lamentar",
    "bedecken": "cubrir",
    "befassen": "tratar",
    "befolgen": "seguir",
    "befragen": "consultar",
    "befreien": "liberar",
    "befriedigen": "satisfacer",
    "begleiten": "acompañar",
    "begründen": "justificar",
    "begutachten": "evaluar",
    "behaupten": "afirmar",
    "beherbergen": "alojar",
    "beherrschen": "dominar",
    "behalten": "mantener",
    "behindern": "obstaculizar",
    "beifügen": "adjuntar",
    "begeistern": "entusiasmar",
    "behalten": "conservar",
    "begrüßen": "saludar",
    "begreifen": "comprender",
    "begegnen": "encontrar",
    "beenden": "terminar",
    "befürchten": "temer",
    "befürworten": "apoyar",
    "begehren": "desear",
    "beeinflussen": "influir",
    "beeinträchtigen": "afectar",
    "beenden": "finalizar",
    "beenden": "cerrar",
    "begegnen": "enfrentar",
    "begegnen": "encontrarse con",
    "begleiten": "asistir",
    "begleiten": "acompañar",
    "begrenzen": "limitar",
    "beherbergen": "albergar",
    "beibehalten": "mantener",
    "beibringen": "enseñar",
    "beifügen": "añadir",
    "beilegen": "adjuntar",
    "beinhalten": "contener",
    "beitragen": "contribuir",
    "bejahen": "afirmar",
    "bejubeln": "aclamar",
    "bekämpfen": "combatir",
    "bekennen": "confesar",
    "bekehren": "convertir",
    "beklagen": "quejarse",
    "bekräftigen": "confirmar",
    "bekränzen": "adornar",
    "beleben": "revitalizar",
    "belästigen": "molestar",
    "belauschen": "espiar",
    "beleidigen": "ofender",
    "bemängeln": "criticar",
    "bemerken": "notar",
    "bemühen": "esforzarse",
    "benehmen": "comportarse",
    "benutzen": "utilizar",
    "beobachten": "observar",
    "beraten": "aconsejar",
    "berechnen": "calcular",
    "bereden": "discutir",
    "berichten": "informar",
    "berücksichtigen": "considerar",
    "beruhigen": "calmar",
    "berücksichtigen": "tener en cuenta",
    "beschädigen": "dañar"
}

    while True: ##Ciclo while sólo por si el usuario se equivoca o no ingresa una cadena válida.
        lenguaje = input("Ingrese el idioma en el cual desea jugar (Español/Inglés/Alemán): ").lower()
        if lenguaje == "español" or lenguaje == "espanol":
            return palabras_español
        elif lenguaje == "ingles" or lenguaje == "inglés":
            return palabras_ingles
        elif lenguaje == "aleman" or lenguaje == "alemán":
            return palabras_aleman
        else:
                print("Seleccione un idioma válido (Español, alemán o inglés).")

def dificultad(palabras): ##Esta función sirve para seleccionar la dificultad dependiendo del idioma que haya escogido el usuario.
    while True: ##Ciclo while nuevamente por si el usuario se equivoca o ingresa una cadena inválida.
        nivel = input("Seleccione el nivel de dificultad, siendo 1 nivel fácil, 2 nivel medio y 3 nivel difícil: ")
        if nivel == "1":
            palabra_secreta = random.choice([word for word in palabras if len(word) <= 5])
            return palabra_secreta
        elif nivel == "2":
            palabra_secreta = random.choice([word for word in palabras if 6 <= len(word) <= 7])
            return palabra_secreta
        elif nivel == "3":
            palabra_secreta = random.choice([word for word in palabras if len(word) >= 8])
            return palabra_secreta
        else:
            print("Seleccione un nivel válido.")

def mostrar_letras_adivinadas(palabra_secreta, letras_adivinadas): ##Esta función sirve para reemplazar cada letra de la palabra que se haya escogido ya sea por guiones bajos o una letra que se haya adivinado.
    for letra in palabra_secreta:
        if letra in letras_adivinadas:
            print(letra, end=" ")
        else:
            print("_", end=" ")
    print()

def obtener_intento(letras_probadas, palabra_secreta): ##Esta función sirve para obtener y retornar la letra que haya ingresado el usuario.
    while True:
        intento = input("Ingrese una letra: ").lower()
        
        if len(intento) > 1 and intento.isalpha():
            if intento == palabra_secreta:
                return intento
            else:
                print("Ingrese una sola letra.")
        elif len(intento) == 1 and intento in letras_probadas:
            print("Ya adivinó esa letra, intente nuevamente.")
        elif len(intento) == 1 and intento.isalpha():
            return intento
        else:
            print("Ingrese sólo letras, y una sola letra.")

def jugar_de_nuevo():
    while True:
        respuesta = input("¿Le gustaría jugar de nuevo? (si/no): ")
        respuesta = respuesta.lower()
        
        if respuesta == "si" or respuesta == "sí":
            return True
        elif respuesta == "no":
            return False
        else:
            print("Responda con 'si' o 'no'.")

def dibujar_ahorcado_facil(letras_incorrectas):
    if len(letras_incorrectas) == 1:
        print("  +---+")
        print("  |   |")
        print("      |")
        print("      |")
        print("      |")
        print("      |")
        print("=========")
    elif len(letras_incorrectas) == 2:
        print("  +---+")
        print("  |   |")
        print("  O   |")
        print("      |")
        print("      |")
        print("      |")
        print("=========")
    elif len(letras_incorrectas) == 3:
        print("  +---+")
        print("  |   |")
        print("  O   |")
        print("  |   |")
        print("      |")
        print("      |")
        print("=========")
    elif len(letras_incorrectas) == 4:
        print("  +---+")
        print("  |   |")
        print("  O   |")
        print(" /|   |")
        print("      |")
        print("      |")
        print("=========")
    elif len(letras_incorrectas) == 5:
        print("  +---+")
        print("  |   |")
        print("  O   |")
        print(" /|\  |")
        print("      |")
        print("      |")
        print("=========")
    elif len(letras_incorrectas) == 6:
        print("  +---+")
        print("  |   |")
        print("  O   |")
        print(" /|\  |")
        print(" /    |")
        print("      |")
        print("=========")
    elif len(letras_incorrectas) == 7:
        print("  +---+")
        print("  |   |")
        print("  O   |")
        print(" /|\  |")
        print(" / \  |")
        print("      |")
        print("=========")

def dibujar_ahorcado_medio(letras_incorrectas):
    if len(letras_incorrectas) == 1:
        print("  +---+")
        print("  |   |")
        print("  O   |")
        print("      |")
        print("      |")
        print("      |")
        print("=========")
    elif len(letras_incorrectas) == 2:
        print("  +---+")
        print("  |   |")
        print("  O   |")
        print("  |   |")
        print("      |")
        print("      |")
        print("=========")
    elif len(letras_incorrectas) == 3:
        print("  +---+")
        print("  |   |")
        print("  O   |")
        print(" /|   |")
        print("      |")
        print("      |")
        print("=========")
    elif len(letras_incorrectas) == 4:
        print("  +---+")
        print("  |   |")
        print("  O   |")
        print(" /|\  |")
        print("      |")
        print("      |")
        print("=========")
    elif len(letras_incorrectas) == 5:
        print("  +---+")
        print("  |   |")
        print("  O   |")
        print(" /|\  |")
        print(" /    |")
        print("      |")
        print("=========")
    elif len(letras_incorrectas) == 6:
        print("  +---+")
        print("  |   |")
        print("  O   |")
        print(" /|\  |")
        print(" / \  |")
        print("      |")
        print("=========")

def dibujar_ahorcado_dificil(letras_incorrectas):
    if len(letras_incorrectas) == 1:
        print("  +---+")
        print("  |   |")
        print("  O   |")
        print("  |   |")
        print("      |")
        print("      |")
        print("=========")
    elif len(letras_incorrectas) == 2:
        print("  +---+")
        print("  |   |")
        print("  O   |")
        print(" /|   |")
        print("      |")
        print("      |")
        print("=========")
    elif len(letras_incorrectas) == 3:
        print("  +---+")
        print("  |   |")
        print("  O   |")
        print(" /|\  |")
        print("      |")
        print("      |")
        print("=========")
    elif len(letras_incorrectas) == 4:
        print("  +---+")
        print("  |   |")
        print("  O   |")
        print(" /|\  |")
        print(" /    |")
        print("      |")
        print("=========")
    elif len(letras_incorrectas) == 5:
        print("  +---+")
        print("  |   |")
        print("  O   |")
        print(" /|\  |")
        print(" / \  |")
        print("      |")
        print("=========")


def jugar_ahorcado():
    palabras = idioma()
    palabra_secreta = dificultad(palabras)
    palabra_secreta = palabra_secreta.lower()
    palabra_secreta = palabra_secreta.replace("á", "a").replace("é", "e").replace("í", "i").replace("ó", "o").replace("ú", "u").replace("ä", "a").replace("ë", "e").replace("ï", "i").replace("ö", "o").replace("ü", "u").replace("ß", "b")
    
    letras_adivinadas = ""
    letras_incorrectas = ""
    
    if len(palabra_secreta) <= 6:
        while True:
            mostrar_letras_adivinadas(palabra_secreta, letras_adivinadas)
            intento = obtener_intento(letras_adivinadas, palabra_secreta + letras_incorrectas)

            if intento in palabra_secreta:
                letras_adivinadas += intento
                dibujar_ahorcado_facil(letras_incorrectas)
                print(f"Letras adivinadas: {letras_adivinadas}")
                print(f"Letras incorrectas: {letras_incorrectas}")
            else:
                letras_incorrectas += intento
                dibujar_ahorcado_facil(letras_incorrectas)
                print(f"Letras adivinadas: {letras_adivinadas}")
                print(f"Letras incorrectas: {letras_incorrectas}")

            if len(letras_incorrectas) == 7:
                print("¡Perdió! La palabra era:", palabra_secreta)
                break

            if all(letra in letras_adivinadas for letra in palabra_secreta):
                print("¡Ganó! La palabra era:", palabra_secreta)
                break
    elif len(palabra_secreta) > 6 and len(palabra_secreta) < 8:
        while True:
            mostrar_letras_adivinadas(palabra_secreta, letras_adivinadas)
            intento = obtener_intento(letras_adivinadas, palabra_secreta + letras_incorrectas)

            if intento in palabra_secreta:
                letras_adivinadas += intento
                dibujar_ahorcado_medio(letras_incorrectas)
                print(f"Letras adivinadas: {letras_adivinadas}")
                print(f"Letras incorrectas: {letras_incorrectas}")
            else:
                letras_incorrectas += intento
                dibujar_ahorcado_medio(letras_incorrectas)
                print(f"Letras adivinadas: {letras_adivinadas}")
                print(f"Letras incorrectas: {letras_incorrectas}")

            if len(letras_incorrectas) == 6:
                print("¡Perdió! La palabra era:", palabra_secreta)
                break

            if all(letra in letras_adivinadas for letra in palabra_secreta):
                print("¡Ganó! La palabra era:", palabra_secreta)
                break
    elif len(palabra_secreta) >= 8:
        while True:
            mostrar_letras_adivinadas(palabra_secreta, letras_adivinadas)
            intento = obtener_intento(letras_adivinadas, palabra_secreta + letras_incorrectas)

            if intento in palabra_secreta:
                letras_adivinadas += intento
                dibujar_ahorcado_dificil(letras_incorrectas)
                print(f"Letras adivinadas: {letras_adivinadas}")
                print(f"Letras incorrectas: {letras_incorrectas}")
            else:
                letras_incorrectas += intento
                dibujar_ahorcado_dificil(letras_incorrectas)
                print(f"Letras adivinadas: {letras_adivinadas}")
                print(f"Letras incorrectas: {letras_incorrectas}")

            if len(letras_incorrectas) == 5:
                print("¡Perdió! La palabra era:", palabra_secreta)
                break

            if all(letra in letras_adivinadas for letra in palabra_secreta):
                print("¡Ganó! La palabra era:", palabra_secreta)
                break
            

    if jugar_de_nuevo():
        jugar_ahorcado()

if __name__ == "__main__": ##Función principal.
    instrucciones()
    jugar_ahorcado()
```

  
