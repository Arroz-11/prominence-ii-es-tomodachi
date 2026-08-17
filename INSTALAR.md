# Cómo entrar al server

## 1. Instalá Prism Launcher

https://prismlauncher.org/download/

Necesitás **Java 17**. Si no lo tenés: https://adoptium.net → **Temurin 17 (LTS)**.

(Es la versión que pide el modpack. Java 21 suele andar, pero si algo falla,
probá con la 17 antes que nada.)

## 2. Bajate este archivo

👉 **[Prominence-II-ES-Tomodachi.zip](../../raw/master/Prominence-II-ES-Tomodachi.zip)** (3,7 MB)

## 3. Importalo en Prism

`Añadir instancia` → `Importar` → `Navegar` → elegí el zip que bajaste → `Aceptar`

> ⚠️ **Si ya importaste una versión anterior, borrá esa instancia primero**
> (click derecho → `Eliminar`) y volvé a importar. Las primeras versiones del pack
> quedaban incompletas y no se arreglan solas.

## 4. Dale a Jugar

**La primera vez tarda bastante**: se está bajando los 442 mods y la traducción.
Dejalo terminar aunque parezca colgado.

Arranca **en español y con todo aplicado**. No tenés que tocar ninguna opción.

### Si te salta un aviso de Java

Prism normalmente elige la 17 solo. Si te avisa que la versión no es compatible:

`Editar instancia` → `Configuración` → tildá **Instalación de Java** →
`Auto-detectar` → elegí la **17** → `Aceptar`

Y si no te aparece ninguna 17 en la lista, es que no la tenés instalada:
https://adoptium.net → **Temurin 17 (LTS)**.

---

## Listo. Nunca más hacés nada.

Cada vez que abrís el juego se actualiza solo. Si se agrega un mod o se corrige
algo de la traducción, te llega sin que muevas un dedo.

---

## Dos cosas importantes

❌ **No saques el inglés del menú de idiomas.** Es un bug conocido del modpack: si
lo quitás, el juego se queda **sin nada de texto**. Poné el español por encima,
pero no borres el inglés.

❌ **No uses el botón "Traducir"** del FTB Quests Translator. Las misiones ya están
traducidas y revisadas a mano; ese botón las pisaría con una traducción automática.

## RAM

Viene con **8 GB**, que anda bien en la mayoría de las PCs. Las flags de rendimiento
(Aikar) ya vienen puestas: **no toques nada de Java ni copies configuraciones**.

Si querés cambiarla:

`Editar instancia` → `Configuración` → tildá **Memoria** → poné los dos valores:

| Tu PC tiene | Mínimo | Máximo |
|---|---|---|
| 8 GB  | `2048` | `6144`  |
| 16 GB | `2048` | `8192`  ← el que viene |
| 32 GB | `2048` | `10240` |

Son MiB: 6144 = 6 GB, 8192 = 8 GB, 10240 = 10 GB.

**No le des toda tu RAM.** Windows y el resto necesitan lo suyo; dejale al menos
6 GB libres o el juego va a andar peor, no mejor.

⚠️ Esto es la config **de la instancia**, no la global de Prism. Son distintas:
la de la instancia manda.

## ¿Algo no anda?

Mandale el error a Agustín. Si el juego no abre, el archivo que sirve está en
`Editar instancia` → `Otros` → `Registros`.
