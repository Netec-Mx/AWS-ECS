# Despliegue de una aplicación mediante AWS Amplify

## Objetivo de la práctica:
Al finalizar la práctica, serás capaz de:
- Implementar un entorno de desarrollo en AWS Amplify.
- Desplegar la aplicación mediante AWS Amplify.

## Objetivo Visual 

![diagrama1](../images/m4/img0.png)

## Duración aproximada:
- 40 minutos.

## Tabla de ayuda:
| Región | Usuario |
| --- | --- |
| us-west-2 | student |

## Instrucciones 

### Tarea 1. Creación o autenticación de GitHub.

En esta tarea crearás una cuenta de GitHub o te autenticarás para cargar el proyecto de AWS Amplify.

**NOTA:** A lo largo de la práctica habrá imágenes para que puedas apoyarte y mejorar la experiencia de la configuración.

**NOTA:** Si ya estás autenticado al laboratorio, puedes avanzar al paso 4 y continuar desde ahí.

Paso 1. Primero inicia sesión en la cuenta de [**AWS**](https://us-east-2.signin.aws.amazon.com/oauth?client_id=arn%3Aaws%3Asignin%3A%3A%3Aconsole%2Fcanvas&code_challenge=O9XOfG1TAAeweXyB0WbmZbNsRtOhuxUkQSSJyXLAzcQ&code_challenge_method=SHA-256&response_type=code&redirect_uri=https%3A%2F%2Fconsole.aws.amazon.com%2Fconsole%2Fhome%3FhashArgs%3D%2523%26isauthcode%3Dtrue%26nc2%3Dh_ct%26src%3Dheader-signin%26state%3DhashArgsFromTB_us-east-2_039ecdfecdcea574)

Paso 2. Dentro de la página usa las credenciales asignadas en el curso:

| Cuenta | Usuario | Contraseña |
| --- | --- | ---|
| **Asignada durante el curso** | **student** | **Asignada durante el curso** |

![isession](../images/m1/img1.png)

Paso 3. Clic en el botón **Sign in**.

Paso 4. Una vez autenticado, verifica tu región; para esta práctica lo harás en **Oregon**/**us-west-2**. También puedes consultar la tabla de ayuda.

Paso 5. Ahora abre otra pestaña en tu mismo navegador y entra a la página de **GitHub** o da clic [**Aquí**](https://github.com/).

Paso 6. En la página de bienvenida de **GitHub**, crea una cuenta **si no tienes una**, colocando tu correo electrónico, **`puede ser personal o corporativo`**.

**NOTA:** Asegúrate de tener permisos administrativos para tu cuenta.

![git1](../images/m4/img1.png)

**NOTA:** Continúa con los pasos de la creación de la cuenta.

Paso 7. Si ya tienes una cuenta, da clic [**Aquí**](https://github.com/login) para autenticarte.

Paso 8. En el panel principal de tu cuenta de GitHub, una vez autenticado, da clic en **New** o **New repository**.

Paso 9. En la sección **Create a new repository**, configura lo siguiente:

| Propiedad | Valor | Descripción |
| --- | --- | ---|
| **Repository name** | **lab4-amplify-XXXX** (sustituye las **X** por letras y números aleatorios). | Nombre del repositorio |

**NOTA:** El resto de los valores se quedará por defecto.

![git1](../images/m4/img2.png)

Paso 10. Clic en el botón **Create repository**.

Paso 11. Copia la **URL** de clonación de tu repositorio; la usarás más adelante. **Guárdala en un bloc de notas**.

![git2](../images/m4/img3.png)

Paso 12. Clic en el nombre **creating a new file**.

![git3](../images/m4/img4.png)

Paso 13. Escribe el nombre del archivo **demofile.txt** y el texto **First File**, y da clic en el botón **Commit changes**.

![git4](../images/m4/img5.png)

Paso 14. Confirma la ventana emergente **Commit changes**.

Paso 15. Ve al ícono de tu **perfil de GitHub**. 

![git5](../images/m4/img6.png)

Paso 16. En el menú, da clic en **Settings**.

![git6](../images/m4/img7.png)

Paso 17. En el menú lateral izquierdo, hasta el final, encontrarás la opción **Developer settings**; da clic.

Paso 18. Ahora selecciona **Personal access tokens** y luego **Tokens (classic)**.

![git7](../images/m4/img8.png)

Paso 19. Genera un nuevo token en la opción **Generate new token** y luego **Generate new token (classic)**.

![git8](../images/m4/img9.png)

Paso 20. Configura como aparece en la imagen; el resto de los valores **se quedarán por defecto**.

![git9](../images/m4/img10.png)

Paso 21. Da clic en el botón **Generate token** al final de la página.

Paso 22. Una vez generado, **guarda el token en tu bloc de notas**; lo usarás más adelante.

![git10](../images/m4/img11.png)

**¡TAREA FINALIZADA!**

> Has completado la creación/autenticación al repositorio de GitHub.

### Tarea 2. Definición de la aplicación en React.

En esta tarea crearás el proyecto de la aplicación simple mediante React.

Paso 1. Vuelve a la página de la **Consola de AWS**.

**NOTA:** Si por error cerraste la página, repite los **pasos 1 a 3 de la tarea 1**.

Paso 2. Da clic en el ícono de **AWS Cloud Shell**.

![awscs](../images/m4/img12.png)

Paso 3. En la terminal, escribe el siguiente comando que creará la estructura del proyecto **React básico**.

```
npx create-react-app app-amplify
```

![awscs1](../images/m4/img13.png)

**NOTA:** Si te pide confirmar los paquetes a instalar, escribe **y**.

Paso 4. Comenzará la descarga e instalación de los paquetes.

![awscs2](../images/m4/img14.png)

**NOTA:** Espera el proceso de inicialización; puede tardar de **1 a 5 minutos**.

Paso 5. Una vez terminado, puedes escribir el comando **`ls`** para ver el directorio.

Paso 6. Ingresa al directorio creado, escribe el comando: **`cd app-amplify`**.

Paso 7. **Repite el paso 5** para ver el interior del directorio.

Paso 8. Entra a la carpeta **src**, escribe el comando: **`cd src`**.

Paso 9. Dentro de la carpeta, ajustarás el archivo llamado **App.js**; escribe el siguiente comando.

**NOTA:** Borra todo el contenido.

```
nano App.js
```

Paso 10. Ahora copia el siguiente código y pégalo dentro del archivo.

```
import './App.css'; // Asegúrate de importar el archivo CSS

function App() {
  return (
    <div className="App">
      <header className="App-header">
        <h1>Despliegue de React con AWS Amplify</h1>
        <p>¡Felicidades! haz desplegado una aplicación React básica en AWS Amplify.</p>
        <button className="btn-primary">Aprender más</button>
      </header>
    </div>
  );
}

export default App;
```

**NOTA:** Recuerda confirmar la ventana emergente, clic en el botón **Paste**.

**```CTRL + O```** **`Enter`** `Para guardar el archivo`

**```CTRL + X```** **`Enter`** `Para salir del archivo`

![awscs3](../images/m4/img15.png)

Paso 11. Ajustamos un archivo más llamado **App.css**.

Paso 12. Repite el **paso 9** y escribe el siguiente comando para editarlo:

```
nano App.css
```

**NOTA:** Borra todo el contenido.

Paso 13. Copia el siguiente código y pégalo dentro del archivo.

```
.App {
  text-align: center;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  background: linear-gradient(135deg, #6a11cb 0%, #2575fc 100%);
  color: white;
  font-family: 'Arial', sans-serif;
}

.App-header {
  background-color: rgba(255, 255, 255, 0.1);
  padding: 40px;
  border-radius: 15px;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
}

h1 {
  font-size: 3rem;
  margin-bottom: 20px;
}

p {
  font-size: 1.5rem;
  margin-bottom: 20px;
}

.btn-primary {
  background-color: #ff4081;
  color: white;
  padding: 10px 20px;
  font-size: 1.2rem;
  border: none;
  border-radius: 25px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

.btn-primary:hover {
  background-color: #ff1c63;
}
```

**NOTA:** Recuerda confirmar la ventana emergente, clic en el botón **Paste**.

**```CTRL + O```** **`Enter`** `Para guardar el archivo`

**```CTRL + X```** **`Enter`** `Para salir del archivo`

**¡TAREA FINALIZADA!**

> Haz completado la descarga de los paquetes con React y los ajustes de la aplicación básica.

### Tarea 3. Carga de archivos a GitHub.

En esta tarea cargarás los archivos al repositorio creado en la tarea 1.

Paso 1. Primero, regresa a la raíz de la carpeta del proyecto, escribe el comando:

```
cd ../../app-amplify
```

![awscs4](../images/m4/img16.png)

Paso 2. Dentro del directorio **app-amplify** escribe los siguientes comandos (uno por uno):

```
git init
```
```
git config --global init.defaultBranch main
```
```
git checkout -b main
```

**NOTA:** Si te sale la siguiente salida, puedes omitirla por el momento.

![awscs5](../images/m4/img17.png)

Paso 3. Ahora escribe el siguiente comando para asociar el repositorio remoto con el local:

```
git remote add origin TU_URL_REPO
```
![awscs6](../images/m4/img18.png)

Paso 4. Escribe el siguiente comando para sincronizar los cambios de los repositorios remoto y local:

```
git pull origin main --allow-unrelated-histories
```
![awscs7](../images/m4/img19.png)

Paso 5. Ahora escribe el comando para agregar los archivos y comenzar a rastrear los cambios:

```
git add .
```

Paso 6. Configura los siguientes datos de tu **cuenta de GitHub**:

```
git config --global user.email "tu_correo_github@example.com"
git config --global user.name "tu_usuario_github"
```

![awscs8](../images/m4/img20.png)

Paso 7. Configura los siguientes datos de tu **cuenta de GitHub**:

```
git config --global user.email "tu_correo_github@example.com"
git config --global user.name "tu_usuario_github"
```

Paso 8. Escribe el comando para rastrear los cambios de los archivos agregados.

```
git commit -m "Carga inicial del proyecto app-amplify"
```

![awscs6](../images/m4/img21.png)

Paso 9. Ahora escribe el siguiente comando para subir los archivos rastreados al repositorio remoto.

```
git push origin main
```

**NOTA:** Te pedirá los datos de tu cuenta de GitHub, **username** y **contraseña**. La contraseña es **tu token** guardado en tu bloc de notas en la tarea 1.

![awscs7](../images/m4/img22.png)

Paso 10. Verifica en tu cuenta de GitHub que los archivos hayan sido cargados correctamente, como lo muestra la imagen.

![awscs8](../images/m4/img23.png)

**¡TAREA FINALIZADA!**

> Haz completado la carga de los archivos al repositorio de GitHub.

### Tarea 3. Creación del proyecto de AWS Amplify

En esta tarea crearás el proyecto de AWS Amplify para el despliegue de la aplicación.

Paso 1. Ahora ve al buscador de AWS en la parte superior de la pantalla y escribe **`AWS Amplify`** y da clic en el servicio.

![amplify](../images/m4/img24.png)

Paso 2. En la página de bienvenida da clic en el botón **Deploy an app**.

![amplify1](../images/m4/img25.png)

Paso 3. En la opción **Deploy your app** de la sección **Start building with Amplify** da clic en **GitHub**.

![amplify2](../images/m4/img26.png)

Paso 4. Clic en el botón **Next**.

Paso 5. En la ventana emergente te pedirá **autorización** a tu repositorio de GitHub, selecciona tu cuenta de GitHub.

![amplify3](../images/m4/img27.png)

Paso 6. En la siguiente ventana selecciona solo el repositorio creado para el laboratorio y da clic en el botón **Install & Authorize**. Puedes apoyarte de la imagen.

![amplify4](../images/m4/img28.png)

Paso 7. De vuelta a **AWS Amplify**, en la sección **Add repository and branch** selecciona tu repositorio y tu rama.

![amplify5](../images/m4/img29.png)

Paso 8. Clic en el botón **Next**.

Paso 9. En la sección **App settings**, cambia el valor de **App name** y escribe el nuevo nombre.

**NOTA:** AWS Amplify detectará automáticamente que es una aplicación React.

```
app-amplify
```

Paso 10. Da clic en el botón **Next**.

Paso 11. Revisa los detalles finales y da clic en el botón **Save and deploy**.

Paso 12. AWS Amplify comenzará con el despliegue, como lo muestra la imagen.

**NOTA:** Puede tardar de **1 a 3 minutos**.

![amplify6](../images/m4/img30.png)

Paso 13. Ya desplegado, el resultado será como la imagen.

![amplify7](../images/m4/img31.png)

Paso 14. Ahora da clic en el link de la propiedad **Domain**, como se muestra en la imagen.

![amplify8](../images/m4/img32.png)

Paso 15. El resultado será la página de ejemplo en React.

![amplify8](../images/m4/img33.png)

**NOTA:** Si aún te queda tiempo, puedes explorar las opciones de AWS Amplify.

**¡TAREA FINALIZADA!**

> Has completado el despliegue de la aplicación en AWS Amplify.

### Resultado final esperado

El resultado es la ejecución correcta de todas las tareas y la imagen final de la aplicación desplegada en React.

![imagen resultado](../images/m4/img33.png)