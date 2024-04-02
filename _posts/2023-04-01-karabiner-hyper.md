---
title: Hyperkey and Karabiner Elements: The perfect duo
description: 
date: 2023-04-01
categories: Blogging
tags: [productivity]
---

So, for the past few years, I've been on a keyboard collecting spree. My quest for the ultimate keyboard introduced me to Karabiner Elements—a swift and seamless macOS app that lets you remap your keyboard keys no sweat. It's so slick, it feels like it's built into the OS. Having used it for ages, I've never encountered any lag or anything of the sort.

Recently, I decided to tweak my workflow, standardizing shortcuts and other system goodies. Normally, I'd tweak my keyboard layers, adding an extra key for easy access to my VIM motions and whatnot. However, not all my keyboards come with a spare key for remapping. So, I aimed to rework my workflow to break free from the need for those extra keys. But more on that later.

## My Keyboards' Layout

Here's what my basic keyboard layouts look like.

![vanilla-keyboards](/assets/img/2024-04-01-19.06.png)

As you can see, I always ditch Caps Lock to remap it as Ctrl, inspired by my HHKB.

If possible, I tweak it so a press acts as Ctrl, but a tap gives me Esc. I'm nuts about always having Esc at my side. Honestly, who uses Caps Lock anyway?

> Ctrl (hold), Esc (Tap)
{: .prompt-info }

But on fancier keyboards like the UHK and MNT Reform, packed with keys, I got used to having those extras always at hand. Great, but shifting back to my MacBook Pro keyboard, or any other vanilla keyboard, the first hour was always brutal.

![mnt-reform-uhk](/assets/img/2024-04-01-19.24.png)

These two have been my go-to keyboards for years; no matter what new keyboard I get, I always come back to them (HHKB was the previous favorite). They're just the best to me.

## Workflow Simplification

As I mentioned, I adapted my workflow to stop relying on sometimes unavailable keys. I took a random keyboard and did a few things:

-   Listed my most-used apps.
    - Reviewed their shortcuts.
    - Tested those shortcuts on an unmodified keyboard to check their difficulty.
        - If a shortcut was too hard, it had to go away.
-   With a refined list of shortcuts, I began transforming them into comfortable, quick movements.

For example, Ctrl + cmd + [7-0]. Why 7 to 0, you might wonder? That's because my right hand can't quickly reach keys beyond 7, like the entire 1 to 6 stretch. The aim was to follow the principle of duty segregation preached by touch typing skills:

![typing-skills-graph](/assets/img/2024-04-01-19.42.png)

Obviously, sticking to just 2 modifiers would:

1. Limit my options,
2. Cause clashes between app shortcuts.

So, I upgraded my beloved Ctrl (Caps Lock) to Hyper. 

Hyper equals Ctrl + Shift + Opt(Alt) + Cmd(Super/Windows). 

Attempting such a combo manually is a recipe for a hand cramp, thus the birth of the Hyper key. Back in the day, Hyper was just another modifier, but modern OS developments morphed it into the beast I outlined.

Now, it's Hyper + [Any Key] for me, with "Any Key" being whichever my right hand can easily reach.

In my [dotfiles](https://github.com/fcosanabria/dotfiles), you can spot how I wield Hyper to command my macOS windows.

```rc
# Change Focus between external displays
hyper - q : yabai -m display --focus 1
hyper - w : yabai -m display --focus 2
hyper - e : yabai -m display --focus 3

...

# Move window to space number 1-9
hyper - 1 : yabai -m window --space 1
hyper - 2 : yabai -m window --space 2
hyper - 3 : yabai -m window --space 3
hyper - 4 : yabai -m window --space 4
hyper - 5 : yabai -m window --space 5
hyper - 6 : yabai -m window --space 6
hyper - 7 : yabai -m window --space 7
hyper - 8 : yabai -m window --space 8
hyper - 9 : yabai -m window --space 9
```

# Español

Desde hace unos años para acá, he coleccionado teclados. Esta búsqueda, al principio, por el teclado perfecto me llevó a saber sobre la existencia de Karabiner Elements. Karabiner Elements, rápidamente, es una aplicación para macOS que tiene la posibilidad de remapear las teclas de tu teclado sin dificultad alguna. Es tan rápido, y funciona tan bien, que parece que las modificaciones ocurren de manera nativa. Al menos, yo que tengo años de estarla usando, nunca he tenido problemas de lag o algo similar al momento de usar la aplicación.

Resulta que, desde hace poco, quise modificar mi flujo de trabajo en lo que respecta a mis atajos, estandarización de aplicaciones y demás utilidades del sistema. Lo que hacía normalmente era que modificaba las capas del teclado, para tener una tecla adicional que me permita usar con comodidad mis VIM motions, y demás. El problema es que no todos los teclados que tengo tienen una tecla adicional que pueda remapear. Entonces, bajo esa condición, decidí modificar mi flujo de trabajo para dejar de depender de teclas adicionales en el teclado. Pero más detalles sobre eso, adelante.

## El layout de mis teclados

Normalmente así luce el layout de mis teclados sencillos.

![vainilla-keyboards](/assets/img/2024-04-01-19.06.png)

Como podrán notar, siempre quito el Caps Lock para poder remapear Ctrl. Esto lo empecé a usar gracias a mi HHKB.

Si el teclado me lo permite, lo modifico para que cuando presiono la tecla sea Ctrl, pero cuando la toco sea Esc. Me encanta la idea de tener Esc siempre a mi lado. La verdad es que Caps Lock es una tecla que no uso.

> Ctrl (hold), Esc (Tap)
{: .prompt-info }

Lamentablemente, en teclados más avanzados como el UHK y el MNT Reform, que tienen muchísimas teclas más de lo normal, me acostumbré a tener esas teclas *siempre* disponibles, lo cual está bien, para eso son, pero cuando regresaba al teclado de la MacBook Pro, o de cualquier otro teclado más vainilla, la primera hora siempre era un infierno.

![mnt-reform-uhk](/assets/img/2024-04-01-19.24.png)

Estos dos teclados han sido mis principales teclados desde los últimos años; no importa qué teclado me compre, siempre uso esos dos (antes de estos usaba el HHKB). Simplemente son mis favoritos.

## Simplificación del Workflow

Como les mencioné ahora, hice un cambio en mi flujo de trabajo para dejar de depender de teclas que a veces no tengo disponibles. Y para eso, tomé un teclado cualquiera y definí varias cosas:

-  Hice una lista de las aplicaciones que más uso.
    - Revisé los atajos de esas aplicaciones.
    - Repliqué esos atajos con el teclado (SIN MODIFICACIONES), para determinar su dificultad.
        - Si el atajo era difícil de realizar, tenía que quitarlo. 
-  Con la categoría de cada uno de los atajos ya listos, empecé a transformarlos de manera que fuera cómodo, y sobre todo rápido de poder realizar ese movimiento.

Por ejemplo, Ctrl + cmd + [7-0]. ¿Por qué del 7 al 0 se preguntarán? Eso porque con mi mano derecha, no puedo alcanzar de manera rápida teclas más allá del 7, por ejemplo, toda la línea del 1 al 6. El punto era seguir el principio de la segregación de deberes que predica la mecanografía:

![mecanografia-graph](/assets/img/2024-04-01-19.42.png)

Claramente, usar solamente la combinación de 2 modificadores, iba a causar dos cosas:

1. Que se me acaben las posibilidades, 
2. Que choquen los atajos entre aplicaciones.

Dicho eso, decidí cambiar mi tan querida tecla Ctrl (Caps Lock) a Hyper. 

Hyper es el equivalente a usar Ctrl + Shift + Opt(Alt) + Cmd(Super/Windows). 

Obviamente, querer realizar ese movimiento es sumamente complejo, si no, imposible. Y es por eso que la tecla Hyper existe. Hace muchos años atrás, Hyper era solo un modificador como cualquier otro, pero con el paso de los años con sistemas operativos más modernos, eso ha cambiado a lo que les mencioné que es.

Entonces, ahora uso Hyper + [Cualquier tecla]. Obvio, cualquier tecla que me permita usar mi mano derecha.

En mis [dotfiles](https://github.com/fcosanabria/dotfiles), se puede ver el clarísimo ejemplo de cómo uso Hyper para manejar mis ventanas en macOS.