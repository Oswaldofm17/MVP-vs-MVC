##Modelo–Vista–Presentador (MVP)

Es una derivación del patrón arquitectónico modelo–vista–controlador (MVC), y es utilizado mayoritariamente para construir interfaces de usuario.

En MVP el presentador asume la funcionalidad del "intermediario". En MVP, toda lógica de presentación es colocada al presentador.

MVP es un patrón arquitectónico de interfaz de usuario diseñada para facilitar pruebas de unidad automatizada y mejorar la separación de inquietudes en lógica de presentación:

El modelo es una interfaz que define los datos que se mostrará o no actuado en la interfaz de usuario.

El presentador actúa sobre el modelo y la vista. Recupera datos de los repositorios (el modelo), y los formatea para mostrarlos en la vista.
La vista es una interfaz pasiva que exhibe datos (el modelo) y órdenes de usuario de las rutas (eventos) al presentador para actuar sobre los datos.

Normalmente, la vista de implementación instancia el objeto de presentador en concreto, proporcionando una referencia a él. El siguiente código C# demuestra una simple vista de un constructor, donde ConcreteDomainPresenter implementa la interfaz IDomainPresenter:

```
public class DomainView : IDomainView
{
    private IDomainPresenter domainPresenter = null;

    ///<summary>Constructor</summary>
    public DomainView()
    {
        domainPresenter = new ConcreteDomainPresenter(this);
    }
}
```

###Diferencias entre MVC Y MVP

El Modelo Vista Controlador (MVC) y el Modelo Vista Presentador son Paradigmas de Diseño de software. La idea principal de estos paradigmas es separar la interfaz gráfica, la lógica, y la "cola" que los une en distintos modulos en el programa.


La diferencia esencial entre MVC y MVP es que los objetos que son parte de la interfaz gráfica del software, delegan sus acciones al controlador para responder a las interacciones del usuario, mientras que en el MVP, los objetos de la interfaz gráfica se encargan de responder al usuario, en vez de delegar las acciones al Controlador como lo haría MVC.
