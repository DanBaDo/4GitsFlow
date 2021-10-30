
# 4GitsFlow

## Intro

Git te permite hacer lo que quieras, así que las posibles forma de usarlo son infinitas.

Como tenemos que trabajar en equipo y nos queremos llevar bien, necesitamos ponernos de acuerdo en una metodología común.

Nuestro Maestro Jedi, Manu Martínez, nos propone un métodología basada en su experiencia.

Esto es un intento de hacer un mapa para encontrarnos y no perdernos.

## Notas

* Cuando pongo ```git switch``` puedes usar ```git checkout```. Para el caso es lo mismo.
* Sí, muchos de los ```git switch``` son innecesarios. Pero asegurate de estar en la rama correcta antes de hacer algo si no quieres liarla parda.


## Con dibujitos

```
                                Cada tarea a realizar supone una iteración.
                                En cada iteración cada persona crea sus commits en
                                rama local, sincronizandolas eventualmente a su rama remota.
                                Cuando alquien ha realizado la entrega (commit) final de una
                                tarea (a,b), pasa los commits de su rama a la devel.
                                Antes de iniciar la siguiente tarea, recoge los commits de los
                                compañeros desde la rama devel a la propia.
                                Todo empieza otra vez.

                             /---------- Iteración -------\   /-------------- Iteración -------------\
                            👇                            👇 👇                                      👇

                   _worker2___b___b_______________________ab______d________abd_______________________abcd
                  /                 \                     /                   \                     /
                 /_worker1___a___a___\__________ab______ /____c______abc_______\__________abcd____ /
                /                 \   \        /        /               \       \        /        /
        _devel_/___________________\a__\ab____/________/_________________\abc____\abcd__/________/____
       /                                                                                              \
_main_/________________________________________________________________________________________________\abcd  -  Welldone! 👌

                                                             |    |      |       |     |         |      |
                                                             |    |      |       |     |         |     (4) Todo está listo. Consolidamos todas las entregas de devel en main:
                                                             |    |      |       |     |         |        git switch main         - Nos aseguramos de tener main como rama activa.
                                                             |    |      |       |     |         |        git pull origin devel   - Traemos a main los commit de devel.
                                                             |    |      |       |     |         |        git push origin main    - Sincronizamos la rama remota para publicar los cámbios. 🍻
                                                             |    |      |       |     |         |
                                                             |    |      |       |     |        (1) Worker2 mantiene su rama sincronizada con los commits de devel antes de iniciar nuevas tareas.
                                                             |    |      |       |     |           git switch worker2      - Nos aseguramos de tener worker2 como rama activa.
                                                             |    |      |       |     |           git pull origin devel   - Traemos a worker2 los commits entregados en devel.
                                                             |    |      |       |     |
                                                             |    |      |       |    (1) Worker1 mantiene su rama actualizada con los commits de devel antes de iniciar nuevas tareas.
                                                             |    |      |       |       git switch worker1      - Nos aseguramos de tener worker1 como rama activa.
                                                             |    |      |       |       git pull origin devel   - Traemos a worker1 los commits entregados en devel.
                                                             |    |      |       |
                                                             |    |      |      (3) Worker2 termina tarea d y pasa sus commits a devel.
                                                             |    |      |         Tras hacer la última entrega en la rama local, copia los commits en devel.
                                                             |    |      |         git switch devel          - Nos aseguramos de tener devel como rama activa.
                                                             |    |      |         git pull origin worker1   - Enviamos nuestros commits a devel.
                                                             |    |      |         git push origin devel     - Sincronizamos la rama devel local con la remota.
                                                             |    |      |         git switch worker2        - Regresamos a nuestra rama.
                                                             |    |      |
                                                             |    |     (3) Worker1 termina tarea c y pasa sus commits a devel.
                                                             |    |        Tras hacer la última entrega en la rama local, copia los commits en devel.
                                                             |    |        git switch devel          - Nos aseguramos de tener devel como rama activa.
                                                             |    |        git pull origin worker1   - Enviamos nuestros commits a la rama devel local.
                                                             |    |        git push origin devel     - Sincronizamos la rama devel local con la remota.
                                                             |    |        git switch worker1        - Regresamos a nuestra rama.
                                                             |    |
                                                             |   (2) Worker2 inicia la tarea d despues de recibir la a desde devel.
                                                             |      Repite estos pasos para entregar cada progreso a lo largo de la tarea.
                                                             |      git switch worker2                       - Nos aseguramos de tener worker2 como rama activa.
                                                             |      git add fuckingCode.js                   - Seleccionamos los archivos de la entrega.
                                                             |      git commit -m "The fucking functions."   - Creamos la entrga.
                                                             |      git push origin worker2                  - Eventualmente, sincronizamos las entregas de nuestra rama local con nuestra rama remota.
                                                             |
                                                            (2) Worker1 inicia la tarea c despues de recibir la b desde devel
                                                               Repite estos pasos para entregar cada progreso a lo largo de la tarea.
                                                               git switch worker1                       - Nos aseguramos de tener worker2 como rama activa.
                                                               git add fuckingLibrary.js                - Seleccionamos los archivos de la entrega.
                                                               git commit -m "The fucking library."     - Creamos la entrga.
                                                               git push origin worker1                  - Eventualmente, sincronizamos las entregas de nuestra rama local con nuestra rama remota.

```

## Resumiendo
* Antes de empezar una tarea, actualiza en tu rama las entregas de devel para contar con las aportaciones de tus compañeros (1).
* Realiza en tu rama todos los commits para la nueva tarea. Eventualmente sincroniza tus entregas con tu rama remota (2).
* Cuando hayas realizado el último commit de una tarea, entrega todos los commits desde tu rama a devel (3).
* Empieza otra vez el ciclo.
* Cuando todas las tareas estén listas y revisadas en devel, pasamos todos los commits de devel a main (4).
                                                                        
## Post data
¿Has visto algún error o se te ocurre una mejora? Tienes dos opciones:
* Crea un fork del repo, haz los cambios que consideres y crea un pull request. Github se ocupará de que quede constancia de tu aportación.
* Abre un issue y deja que otros lo arreglen. Señalar una necesidad también es una forma de ayudar.

## Licencia
[  ![WTFPL](wtfpl-badge-1.png)  ]( http://www.wtfpl.net/ )
