# Practica08-Laberinto-VR
```
CONSEJO ACADÉMICO Aprobación: 2016 / 04 / 06
```
```
Formato: Guía de Práctica de Laboratorio / Talleres / Centros de Simulación
```
## PRÁCTICA DE LABORATORIO

# CARRERA: COMPUTACION ASIGNATURA: PROGRAMACIÓN

## HIPERMEDIAL

## NRO. PRÁCTICA: 8 TÍTULO PRÁCTICA: Desarrollo de una aplicación de realidad

## virtual usando la herramienta Unity y desplegada en un dispositivo

## móvil Android.

## OBJETIVO ALCANZADO:

## • Experimenta con aplicaciones de realidad virtual.

## • Experimenta con aplicaciones de realidad aumentada.

## • Distingue la diferencia entre tecnologías de realidad virtual y realidad aumentada.

## ACTIVIDADES DESARROLLADAS

## 1. Crear un repositorio en GitHub con el nombre “Practica08 – Laberinto VR”

## 2. Realizar un commit y push por cada requerimiento de los puntos antes descritos.

## a. Ignorar las carpetas Temp y Library

## b. Agregar el archivo apk comprimido en .zip

## 3. Luego, se debe crear el archivo README del repositorio de GitHub.

## 4. Generar informe de los resultados en el formato de prácticas. Debe incluir:

## a) El desarrollo de cada uno de los requerimientos antes descritos.

## b) La evidencia del correcto diseño de la escena

## c) La evidencia del correcto funcionamiento de la aplicación

## d) El informe debe incluir conclusiones apropiadas.

## e) En el informe se debe incluir la información de GitHub (usuario y URL del repositorio de la práctica)

## f) En el informe se debe incluir la firma digital de los estudiantes

## 5. En el archivo README del repositorio debe constar la misma información del informe de resultados de la

## práctica que se indica en el punto anterior

## Este proyecto es una oportunidad para que combine y practique todo lo que aprendió en el capítulo de Realidad

## Virtual. Creará una experiencia de realidad virtual totalmente interactiva en forma de laberinto.

## Esto le brinda la oportunidad de aplicar lo que ha aprendido con las secuencias de comandos para brindar una

## experiencia audiovisual completa.

## Crear la GVR Camera Rig

## Durante este paso, crearemos la cámara VR incluyendo el GvrEditorEmulator en la escena y configurando la cámara.


```
CONSEJO ACADÉMICO Aprobación: 2016 / 04 / 06
```
```
Formato: Guía de Práctica de Laboratorio / Talleres / Centros de Simulación
```
## 1. Agregue el objeto prefab GvrEditorEmulator a la escena.

## 2. Convierta el objeto Main Camera en un elemento hijo del objeto GvrEditorEmulator.

## 3. Restablece el componente Transformar del objeto Main Camera

## 4. Mueva el objeto GvrEditorEmulator a una ubicación conveniente para el desarrollo, por ejemplo, Posición: 0, 3, 35

## y Rotación: 0, 180, 0.

## 5. Ingrese al modo de juego y use Alt + Mouse y Ctrl + Mouse para rotar e inclinar el ángulo de visión de la cámara.

## Preparando la escena para la interacción

## Durante este paso, prepararemos la escena para la interacción configurando el puntero, el emisor de rayos y el

## sistema de eventos, y luego probaremos el sistema de punto de referencia incluido (waypoint).

## 1. Agregue el objeto prefab GvrReticlePointer a la escena como elemento secundario del objeto del Main Camera.

## 2. Aumente el valor de Distancia máxima de retícula para el GvrReticlePointer del valor predeterminado de 10 a 20.

## 3. Agregue el script GvrPointerPhysicsRaycaster como componente en el objeto

## Main Camera.

## 4. Agregue el objeto prefab GvrEventSystem a la escena.

## 5. Ingrese al modo de juego y navegue por la escena haciendo clic en los puntos de referencia.

## Hacer que los objetos del juego sean interactivos

## Durante este paso haremos que la Moneda, la Llave y la Puerta sean interactivas añadiéndoles componentes de

## disparadores y eventos.

## 1. Localiza y selecciona el objeto Coin en la jerarquía.

## 2. Verifique que tenga un componente Collider.

## 3. Agregue el script Coin proporcionado como componente.

## 4. Agregue un dispardor de evento (Event Trigger) como componente.

## 5. Agregue el evento PointerClick al componente Event Trigger.

## 6. Asigne el componente del script Coin al campo de objeto del evento Pointer Click.

## 7. Asigne el método Coin.OnCoinClicked () como la función para el evento Pointer Click.

## 8. Ingrese al modo de juego, haga clic en la moneda y verifique que el mensaje 'Coin.OnCoinClicked ()' esté impreso

## en la ventana de la consola.

## 9. Repita el mismo proceso para el objeto del juego Key pero use el script Key y el método Key.OnKeyClicked ().

## 10. Repita el mismo proceso para el primer objeto principal del juego de Puerta, pero use el script de Puerta y el

## método Door.OnDoorClicked ().

## Hacer la interfaz de usuario interactiva


```
CONSEJO ACADÉMICO Aprobación: 2016 / 04 / 06
```
```
Formato: Guía de Práctica de Laboratorio / Talleres / Centros de Simulación
```
## Durante este paso, haremos que el objeto SignPost sea interactivo al agregarle componentes de disparadores y

## eventos. El proceso es casi idéntico al que hicimos con la moneda, la llave y la puerta en el paso anterior, pero no

## necesitamos un colisionador para interactuar con los objetos del juego de la interfaz de usuario. En su lugar, debemos

## verificar que el objeto del juego Canvas tenga un componente Graphic Raycaster, y debido a que estamos usando

## GVR, reemplazaremos el Graphic Raycaster de Unity con el GvrPointerGraphicRaycaster de Google VR.

## 1. Localiza y selecciona el objeto del juego SignPost en la jerarquía.

## 2. Elimine el componente Graphic Raycaster que se agrega automáticamente al crear un nuevo objeto.

## 3. Agregue el script GvrPointerGraphicRaycaster como componente.

## 4. Agregue el script SignPost proporcionado como componente.

## 5. Agregue un Event Trigger como componente.

## 6. Agregue el evento PointerClick al componente Event Trigger.

## 7. Asigne el componente script SignPost al campo de objeto del evento Pointer Click.

## 8. Asigne el método SignPost.ResetScene () como la función para el evento Pointer Click.

## 9. Ingrese al modo de juego, haga clic en SignPost y verifique que el mensaje 'SignPost.ResetScene ()' esté impreso

## en la ventana de la consola.

## Programando el comportamiento de la moneda (coin)

## Durante este paso, programaremos el comportamiento de la moneda para que, cuando se haga clic en una moneda

## (coin), se reproduzca un sonido, muestre un efecto de "poof" y desaparezca.

## 1. Hay un mínimo de cinco monedas en el laberinto. Cuando se hace clic en una moneda, se reproduce un efecto de

## sonido en la ubicación de esa moneda.Cuando se hace clic en una moneda, esa moneda se elimina de la jerarquía

## de la escena.

## 2. Abra el script de Coin y lea todo el script, incluidos todos los comentarios.

## 3. Dedique un tiempo a comprender el comportamiento del objeto prefab CoinPoof proporcionado. Puede hacer esto,

## por ejemplo, ingresando al modo de juego y arrastrando un objeto prefab CoinPoof a la escena.

## 4. Programe el comportamiento de la moneda completando todos los comentarios

## TODO en el script.

## Programando el comportamiento de la llave (key)

## Durante este paso, programaremos el comportamiento de la llave (key) para que, cuando se haga clic en la llave,

## reproduzca un sonido, muestre un efecto de "poof" y desaparezca.

## 1. Hay un mínimo de una llave en el laberinto. Cuando se hace clic en la llave, se reproduce un efecto de sonido en

## la ubicación de la llave. Cuando se hace clic en la llave, la llave se elimina de la jerarquía de la escena. Cuando se

## hace clic en la llave, la puerta se desbloquea.

## 2. Abra el script key y lea completo, incluidos todos los comentarios.


```
CONSEJO ACADÉMICO Aprobación: 2016 / 04 / 06
```
```
Formato: Guía de Práctica de Laboratorio / Talleres / Centros de Simulación
```
## 3. Dedique un tiempo a comprender el comportamiento del objeto prefab KeyPoof proporcionado. Puede hacer esto,

## por ejemplo, ingresando al modo de juego y arrastrando un objeto prefab KeyPoof a la escena.

## 4. Programe el comportamiento key completando todos los comentarios TODO en el script

## Programando el comportamiento de la puerta (door)

## Durante este paso, programaremos el comportamiento de la puerta (door) para que cuando se haga clic en la llave

## (key), la Puerta se desbloquee y cuando se haga clic en la

## Puerta, se escuche un sonido y comience a girar a una posición de apertura.

## 1. La puerta evita que el usuario navegue al objeto SignPost hasta que se haya abierto. Cuando comienza el juego,

## la puerta está bloqueada y cerrada. La puerta no se puede abrir cuando está bloqueada. La puerta solo puede

## desbloquearse haciendo clic en la llave. Cuando se hace clic y se desbloquea la puerta, la puerta comienza a abrirse.

## Cuando la puerta comienza a abrirse, se reproduce un efecto de sonido en la ubicación de la puerta. La puerta se

## anima a una posición de abierta solo por código, es decir, no mediante el uso de animación y controlador de animador.

## 2. Abra el script Door y lea todo el script, incluidos todos los comentarios.

## 3. Agregue un componente AudioSource al primer objeto padre Door y desactive la propiedad Play On Awake.

## 4. Asigne el audio Door_Opening al campo AudioClip.

## 5. Programe el comportamiento de la puerta completando todos los comentarios

## TODO en el script.

## Programando el comportamiento del SignPost

## Durante este paso, programaremos el comportamiento de SignPost para que cuando se haga clic en SignPost se

## reinicie el juego.

## 1. El SignPost no se puede ver ni interactuar antes de que se abra la puerta. Cuando se hace clic en SignPost, la

## escena se restablece a su estado inicial para que el juego se pueda volver a jugar.

## 2. Abra el script SignPost y lea todo el script, incluidos todos los comentarios.

## 3. Programe el comportamiento SignPost completando todos los comentarios TODO en el script.

## Crear la funcionalidad del juego

## Durante este paso, armaremos todo y convertiremos nuestro proyecto en un juego real.

## Laberinto

- El laberinto está diseñado de tal manera que el usuario no puede identificar una ruta a la llave desde la posición de

## inicio.

## Waypoints

- Los puntos de referencia se colocan en todo el laberinto de tal manera que los usuarios pueden navegar desde la

## posición inicial a todos los objetos del juego con los que se puede interactuar, es decir, todas las monedas, la llave,

## la puerta y el SignPost.


```
CONSEJO ACADÉMICO Aprobación: 2016 / 04 / 06
```
```
Formato: Guía de Práctica de Laboratorio / Talleres / Centros de Simulación
```
## Monedas

## • Hay un mínimo de cinco monedas en el laberinto.

## Llave

## • Hay un mínimo de una clave en el laberinto.

## Puerta

## 1. La puerta evita que el usuario navegue hasta SignPost hasta que se haya abierto.

## SignPost

## • El cartel no se puede ver ni interactuar antes de que se abra la puerta.

## 1. Use los objetos de juego Maze para diseñar un laberinto.

## 2. Mueva el jugador, es decir, el objeto del juego GvrEditorEmulator, a la ubicación de inicio deseada.

## 3. Agregue más Waypoints para que el jugador pueda navegar a todas las partes del Laberinto.

## 4. Agrega más monedas para que el jugador tenga muchas monedas para coleccionar.

## 5. Mueva la llave a una ubicación para que sea un tanto difícil para el jugador encontrarla.

## 6. Agregue paredes (cubos) para asegurarse de que los usuarios tengan que navegar para encontrar la llave y las

## monedas.

## RESULTADO(S) OBTENIDO(S):

# 1. Repositorio Github

# 2. Archivo README

# 3. Capturas de la aplicación

## La siguiente captura demuestra la estructura del laberinto con los prefabs de las monedas, la llave, las puertas, el

## sign post y con sus pilares que dan la forma al laberinto.


```
CONSEJO ACADÉMICO Aprobación: 2016 / 04 / 06
```
```
Formato: Guía de Práctica de Laboratorio / Talleres / Centros de Simulación
```
## Para la estructura de la moneda se utilizo el modelo prefab que se tenia en la parte de Arts, Prefabs, Coin, la moneda

## tiene un script programado para que cuando se seleccione se realice la animación que desaparece.

## Además, tiene un collider para que la moneda realice una acción a través del pointerclick el cual es el puntero de la

## camara VR, basado en el método OnCoinClicked.

using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class Coin : MonoBehaviour {

// TODO: Create variables to reference the game objects we need access to
// Declare a GameObject named 'coinPoofPrefab' and assign the 'CoinPoof' prefab to the field
in Unity
public GameObject coinPoofPrefab;

void Update () {
// OPTIONAL-CHALLENGE: Animate the coin rotating
// TIP: You could use a method from the Transform class
}

public void OnCoinClicked () {


```
CONSEJO ACADÉMICO Aprobación: 2016 / 04 / 06
```
```
Formato: Guía de Práctica de Laboratorio / Talleres / Centros de Simulación
```
/// Called when the 'Coin' game object is clicked
/// - Displays a poof effect (handled by the 'CoinPoof' prefab)
/// - Plays an audio clip (handled by the 'CoinPoof' prefab)
/// - Removes the coin from the scene

// Prints to the console when the method is called
Debug.Log ("'Coin.OnCoinClicked()' was called");

// TODO: Display the poof effect and remove the coin from the scene
// Use Instantiate() to create a clone of the 'CoinPoof' prefab at this coin's position
and with the 'CoinPoof' prefab's rotation
// Use Destroy() to delete the coin after for example 0.5 seconds

coinPoofPrefab = Object.Instantiate(coinPoofPrefab, transform.position, Quaternion.Euler(-
90, 0, 0));

Object.Destroy(gameObject);
}
}

## Para la estructura de la llave se utilizó el modelo prefab que se tenía en la parte de Arts, Prefabs, Key, la llave tiene

## un script programado para que cuando se seleccione se realice la animación que desaparece.

## Cuando no se selecciona la llave el estado locked de la puerta permanece activado mientras que si se recoge la llave

## el estado de bloqueo desaparece.


```
CONSEJO ACADÉMICO Aprobación: 2016 / 04 / 06
```
```
Formato: Guía de Práctica de Laboratorio / Talleres / Centros de Simulación
```
## Además, tiene un collider para que la moneda realice una acción a través del pointerclick el cual es el puntero de la

## camara VR, basado en el método OnCoinClicked.

## Como adición el prefab de la puerta debe ser añadido sino no obtendrá ningún estado de abierto o cerrado de la

## puerta.

using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class Key : MonoBehaviour {

// TODO: Create variables to reference the game objects we need access to
// Declare a GameObject named 'keyPoofPrefab' and assign the 'KeyPoof' prefab to the field in
Unity
// Declare a Door named 'door' and assign the top level 'Door' game object to the field in
Unity
public GameObject keyPoofPrefab;
public Door door;

void Update () {
// OPTIONAL-CHALLENGE: Animate the key rotating
// TIP: You could use a method from the Transform class
}

public void OnKeyClicked () {
/// Called when the 'Key' game object is clicked
/// - Unlocks the door (handled by the Door class)
/// - Displays a poof effect (handled by the 'KeyPoof' prefab)
/// - Plays an audio clip (handled by the 'KeyPoof' prefab)
/// - Removes the key from the scene
Object.Instantiate(keyPoofPrefab, gameObject.transform.position, Quaternion.Euler(-90, 0,
0));

// Prints to the console when the method is called
Debug.Log ("'Key.OnKeyClicked()' was called");

// TODO: Unlock the door, display the poof effect, and remove the key from the scene
// Use 'door' to call the Door.Unlock() method
// Use Instantiate() to create a clone of the 'KeyPoof' prefab at this coin's position and
with the 'KeyPoof' prefab's rotation
// Use Destroy() to delete the key after for example 0.5 seconds
Door doorScript = door.GetComponent<Door>();
doorScript.Unlock();

Object.Destroy(gameObject);
}
}


```
CONSEJO ACADÉMICO Aprobación: 2016 / 04 / 06
```
```
Formato: Guía de Práctica de Laboratorio / Talleres / Centros de Simulación
```
## Como ultimo punto la puerta rota según el estado en el que se encuentra la llave: Bloqueado y Abierto, si la llave esta

## en el estado bloqueado se reproducirá un sonido de bloqueo, al contrario del abierto que pasará un audio de una

## puerta abierta.

## Para que cada puerta sea abierta se debe añadir al componente principal de la puerta la parte de la derecha y la

## parte de la izquierda junto con su controlador del audio que viene en la parte de los componentes.

## Finalmente, las puertas rotan según su posición de donde se encuentra con el método rotatio, y el método Quaternion

## para darle eje para que se mueva la puerta.

using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class Door : MonoBehaviour {

// TODO: Create variables to reference the game objects we need access to
// Declare a GameObject named 'leftDoor' and assign the 'Left_Door' game object to the field
in Unity
// Declare a GameObject named 'rightDoor' and assign the 'Right_Door' game object to the field
in Unity
public GameObject leftDoor;
public GameObject rightDoor;

// TODO: Create variables to reference the components we need access to
// Declare an AudioSource named 'audioSource' and get a reference to the audio source in
Start()
public AudioSource audioSource;
public AudioClip doorLocked;
public AudioClip doorOpen;

// TODO: Create variables to track the gameplay states


```
CONSEJO ACADÉMICO Aprobación: 2016 / 04 / 06
```
```
Formato: Guía de Práctica de Laboratorio / Talleres / Centros de Simulación
```
// Declare a boolean named 'locked' to track if the door has been unlocked and initialize it
to 'true'
// Declare a boolean named 'opening' to track if the door is opening and initialize it to
'false'
public bool locked = true;
public bool opening = false;

// TODO: Create variables to hold rotations used when animating the door opening
// Declare a Quaternion named 'leftDoorStartRotation' to hold the start rotation of the
'Left_Door' game object
// Declare a Quaternion named "leftDoorEndRotation" to hold the end rotation of the
'Left_Door' game object
// Declare a Quaternion named 'rightDoorStartRotation' to hold the start rotation of the
'Right_Door' game object
// Declare a Quaternion named 'rightDoorEndRotation' to hold the end rotation of the
'Right_Door' game object
public Quaternion leftDoorStartRotation;
public Quaternion leftDoorEndRotation;
public Quaternion rightDoorStartRotation;
public Quaternion rightDoorEndRotation;

// TODO: Create variables to control the speed of the interpolation when animating the door
opening
// Declare a float named 'timer' to track the Quaternion.Slerp() interpolation and initialize
it to for example '0f'
// Declare a float named 'rotationTime' to set the Quaternion.Slerp() interpolation speed and
initialize it to for example '10f'
public float timer = 0f;
public float rotationTime = 10f;

void Start () {
// TODO: Get a reference to the audio source
// Use GetComponent<>() to get a reference to the AudioSource component and assign it to
the 'audioSource'
audioSource = GetComponent<AudioSource>();

// TODO: Set start and end rotation values used when animating the door opening
// Use 'leftDoor' to get the start rotation of the 'Left_Door' game object and assign it
to 'leftDoorStartRotation'
// Use 'leftDoorStartRotation' and Quaternion.Euler() to set the end rotation of the
'Left_Door' game object and assign it to 'leftDoorEndRotation'
// Use 'rightDoor' to get the start rotation of the 'Right_Door' game object and assign it
to 'rightDoorStartRotation'
// Use 'rightDoorStartRotation' and Quaternion.Euler() to set the end rotation of the
'Right_Door' game object and assign it to 'rightDoorEndRotation'

leftDoorStartRotation = Quaternion.Euler(270, 0, 180);
leftDoorEndRotation = leftDoorStartRotation * Quaternion.Euler(0f, 0f, 2f);
rightDoorStartRotation = Quaternion.Euler(270, 0, 180);
rightDoorEndRotation = rightDoorStartRotation * Quaternion.Euler(0f, 0f, 2f);
}


```
CONSEJO ACADÉMICO Aprobación: 2016 / 04 / 06
```
```
Formato: Guía de Práctica de Laboratorio / Talleres / Centros de Simulación
```
void Update () {
// TODO: If the door is opening, animate the 'Left_Door' and 'Right_Door' game objects
rotating open
// Use 'opening' to check if the door is opening...
// ... use Quaternion.Slerp() to interpolate from 'leftDoorStartRotation' to
'leftDoorEndRotation' by the interpolation time 'timer / rotationTime' and assign it to the
'leftDoor' rotation
// ... use Quaternion.Slerp() to interpolate from 'rightDoorStartRotation' to
'rightDoorEndRotation' by the interpolation time 'timer / rotationTime' and assign it to the
'leftDoor' rotation
// ... use Time.deltaTime to increment 'timer'

if (opening == true)
{
leftDoor.transform.rotation = Quaternion.Slerp(leftDoorStartRotation,
leftDoorEndRotation, timer / rotationTime);
rightDoor.transform.rotation = Quaternion.Slerp(rightDoorStartRotation,
rightDoorEndRotation, timer / rotationTime);
timer += Time.deltaTime;
}

### }

public void OnDoorClicked () {
/// Called when the 'Left_Door' or 'Right_Door' game object is clicked
/// - Starts opening the door if it has been unlocked
/// - Plays an audio clip when the door starts opening

// Prints to the console when the method is called
Debug.Log ("'Door.OnDoorClicked()' was called");

// TODO: If the door is unlocked, start animating the door rotating open and play a sound
to indicate the door is opening
// Use 'locked' to check if the door is locked and ...
// ... start the animation defined in Update() by changing the value of 'opening'
// ... use 'audioSource' to play the AudioClip assigned to the AudioSource component
Debug.Log("'Door.OnDoorClicked()' was called");
if (locked == false)
{
audioSource.clip = doorOpen;
audioSource.Play();
opening = true;
}
else
{
audioSource.clip = doorLocked;
audioSource.Play();
locked = true;
opening = false;
}

// OPTIONAL-CHALLENGE: Prevent the door from being interacted with after it has started
opening


```
CONSEJO ACADÉMICO Aprobación: 2016 / 04 / 06
```
```
Formato: Guía de Práctica de Laboratorio / Talleres / Centros de Simulación
```
// TIP: You could disable the Event Trigger component, or for an extra challenge, try
disabling all the Collider components on all children

// OPTIONAL-CHALLENGE: Play a different sound if the door is locked
// TIP: You could get a reference to the 'Door_Locked' audio and play it without assigning
it to the AudioSource component

### }

public void Unlock () {
/// Called from Key.OnKeyClicked(), i.e. the Key.cs script, when the 'Key' game
object is clicked
/// - Unlocks the door

// Prints to the console when the method is called
Debug.Log ("'Door.Unlock()' was called");

// TODO: Unlock the door
// Unlock the door by changing the value of 'locked'
locked = false;
}

## }

## Nombre en GitHub: PedroOrellana

## Url del repositorio: https://github.com/PedroOrellana98/Practica08-Laberinto-VR.git

# 4. Funcionamiento de la aplicación


```
CONSEJO ACADÉMICO Aprobación: 2016 / 04 / 06
```
```
Formato: Guía de Práctica de Laboratorio / Talleres / Centros de Simulación
```
## https://estliveupsedu-

## my.sharepoint.com/:v:/g/personal/porellanaj_est_ups_edu_ec/EfD3eg_wQpNCnoGyaMyeNY4B7PzmVQ7swuUWLt-

## WTK9ACw?e=9BzTHh

## CONCLUSIONES:

## El entorno virtual es la tecnología del futuro y el desarrollo de modelos en 3D se está volviendo más común para los

## desarrolladores.

## RECOMENDACIONES:

## Se recomendaría el uso de las gafas de Google Cardboard para observar con mas detalle el modelado.

## Nombre de estudiante: Pedro José Orellana Jaramillo

## Firma de estudiante:


