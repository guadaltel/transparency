# M.plugin.Transparency

Plugin que permite aplicar un efecto de transparencia a la capa seleccionada.

![Imagen1](./img/transparency_1.png)

# Dependencias

- transparency.ol.min.js
- transparency.ol.min.css


```html
 <link href="../../plugins/transparency/transparency.ol.min.css" rel="stylesheet" />
 <script type="text/javascript" src="../../plugins/transparency/transparency.ol.min.js"></script>
```

# Parámetros

- El constructor se inicializa con un JSON de options con los siguientes atributos:

- **layer**. Parámetro obligatorio. String que contiene el nombre de la capa (que está en el mapa) o la url en formato mapea para insertar una capa a través de servicios WMS ó WMTS. 
  A esta capa se le aplicará el efecto de transparencia.

- **position**. Indica la posición donde se mostrará el plugin.
  - 'TL':top left
  - 'TR':top right (default)
  - 'BL':bottom left
  - 'BR':bottom right

- **radius**. Campo numérico que modifica el radio del efecto transparencia. Tiene un rango entre 30 y 200.

# Eventos

# Otros métodos

# Ejemplos de uso

## Ejemplo 1
Insertar un capa a través de un servicio WMTS.
```javascript
  const mp = new M.plugin.Transparency({
    layer: 'wmts**http://www.ideandalucia.es/geowebcache/service/wmts*toporaster',
    postition: 'TL',
  });

   map.addPlugin(mp);
```

## Ejemplo 2
Aplicar a una capa ("provincias") que se encuentra en el mapa.

```javascript
const mp = new M.plugin.Transparency({
  layer: 'provincias',
  radius: 150,
});

map.addPlugin(mp);
```
## Ejemplo 3
Insertar un capa a través de un servicio WMS.
```javascript
  const mp = new M.plugin.Transparency({
    layer: 'WMS**http://www.ign.es/wms-inspire/ign-base*IGNBaseTodo',
    postition: 'TL',
  });

   map.addPlugin(mp);
```

