# 🎁 Amigo Secreto

## 📌 Descripción

Este proyecto permite a los usuarios ingresar nombres de amigos, almacenarlos en una lista y sortear aleatoriamente un "amigo secreto". Está desarrollado con **HTML, CSS y JavaScript**.

## 🚀 Características

- Agregar amigos a una lista.
- Mostrar la lista de amigos ingresados.
- Sortear aleatoriamente un amigo de la lista.
- Mostrar el resultado del sorteo en pantalla.

## 🛠️ Tecnologías Utilizadas

- **HTML5** → Estructura del sitio.
- **CSS3** → Estilos y diseño.
- **JavaScript** → Lógica del sorteo y manipulación del DOM.

## 📂 Estructura del Proyecto

```
Amigo-Secreto/
│── assets/                # Imágenes y otros recursos
│── index.html             # Página principal
│── style.css              # Estilos del sitio
│── app.js                 # Lógica del proyecto
│── README.md              # Documentación
```

## 📦 Instalación

1. **Clona el repositorio**
   ```bash
   git clone https://github.com/tu-usuario/amigo-secreto.git
   ```
2. **Abre la carpeta del proyecto**
   ```bash
   cd amigo-secreto
   ```
3. **Abre el archivo **``** en tu navegador**
   - Puedes hacer doble clic en el archivo o usar una extensión como "Live Server" en VS Code.

## 📌 Dependencias

Este proyecto no requiere instalación de dependencias externas, ya que utiliza únicamente HTML, CSS y JavaScript nativo.

## ▶️ Cómo Ejecutar el Proyecto

1. **Método 1: Abrir directamente en el navegador**
   - Haz doble clic en `index.html`.
2. **Método 2: Usar Live Server en VS Code**
   - Instala la extensión "Live Server".
   - Haz clic derecho en `index.html` y selecciona "Open with Live Server".

## 🎯 Funcionalidades

### ➕ Agregar un Amigo

- Escribe un nombre en el campo de entrada.
- Haz clic en el botón "Añadir".
- El nombre se agregará a la lista de amigos.

### 🔄 Actualizar la Lista

- La lista se actualizará automáticamente cada vez que se agregue un amigo.

### 🎲 Sortear un Amigo

- Haz clic en el botón "Sortear amigo".
- Se seleccionará un nombre aleatorio de la lista.
- El resultado se mostrará en pantalla.

## 📝 Código Principal (`app.js`)

```javascript
let amigos = [];

function agregarAmigo() {
    let input = document.getElementById("amigo");
    let nombre = input.value.trim();
    if (nombre === "") {
        alert("Por favor, inserte un nombre.");
        return;
    }
    amigos.push(nombre);
    actualizarLista();
    input.value = "";
}

function actualizarLista() {
    let lista = document.getElementById("listaAmigos");
    lista.innerHTML = "";
    for (let amigo of amigos) {
        let li = document.createElement("li");
        li.textContent = amigo;
        lista.appendChild(li);
    }
}

function sortearAmigo() {
    let resultado = document.getElementById("resultado");
    if (amigos.length === 0) {
        alert("No hay amigos en la lista para sortear.");
        return;
    }
    let indiceAleatorio = Math.floor(Math.random() * amigos.length);
    resultado.innerHTML = `<li>${amigos[indiceAleatorio]} es el amigo secreto 🎉</li>`;
}
```

## ⚠️ Posibles Problemas y Soluciones

### ❌ No se muestra la lista de amigos después de agregar

🔹 **Solución:** Asegúrate de que el ID `listaAmigos` esté correctamente referenciado en el HTML y que `actualizarLista()` se esté llamando después de agregar un amigo.

### ❌ No se puede sortear si no hay amigos en la lista

🔹 **Solución:** Asegúrate de agregar amigos antes de intentar sortear.

### ❌ No se actualiza la página después de modificar `app.js`

🔹 **Solución:** Intenta recargar la página (`Ctrl + R`) o borrar la caché con `Ctrl + Shift + R`.

## 📌 Mejoras Futuras

- Agregar la opción de eliminar amigos de la lista.
- Implementar almacenamiento local para guardar la lista.
- Mejorar el diseño con animaciones CSS.

¡Diviértete sorteando a tu amigo secreto! 🎉

