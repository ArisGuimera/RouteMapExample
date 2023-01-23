# Genera RUTAS en ANDROID con GOOGLE MAPS

<p align="center">
<a href="https://youtu.be/_6EeTp4GxLo">
<img src="https://i.imgur.com/Q9WckzP.jpg" style="height: 75%; width:75%;"/></center> </a></p>

## Crea un proyecto desde cero que genere rutas en tiempo real

Uber, Glovo, Rappi... ¿Qué tienen en común? TODAS tienen rutas, ya que es una de las tecnologías 
más usadas y requeridas a día de hoy. 

En este proyecto aprenderemos a crear una App completa donde implementaremos Google Maps y utilizaremos 
el API gratuito de OpenRouteService para poder seleccionar coordenadas y pintar la ruta más óptima en el momento. 

En este vídeo aprenderás:
<br />
- Añadir mapas de Google Maps
- Preparar el API de OpenRouteService con Retrofit
- Aprender a dibujar Polylines
- Personalizar las rutas

## Cómo hacer que funciona el proyecto

Si clonas el proyecto directamente no va a funcionar ya que he quitado mis claves API personales.
Para solucionarlo tendrás que:

- Generar un API_KEY de Google Maps (el vídeo lo explica) y añadirla en el fichero *AndroidManifest.xml* 

```xml
 <meta-data
    android:name="com.google.android.geo.API_KEY"
    android:value="TU_API_KEY"/>
```

- Crear un API_KEY en OpenRouteService (explicado en el vídeo) y añadirla en el fichero *MainActivity*

```kotlin
private fun createRoute() {
    CoroutineScope(Dispatchers.IO).launch {
        val call = getRetrofit().create(ApiService::class.java)
            .getRoute("TU_API_KEY", start, end)
        if (call.isSuccessful) {
            drawRoute(call.body())
        } else {
            Log.i("aris", "KO")
        }
    }
}
```

## COLABORA.

Este proyecto es totalmente GRATUITO por lo que puedes aportar tu grano de arena de múltiples formas.

- Dale a FAV al proyecto (Star)
- Sígueme en mis [redes sociales](https://aristi.dev)
- Nomíname a [GITHUB STAR](https://stars.github.com/nominate/)