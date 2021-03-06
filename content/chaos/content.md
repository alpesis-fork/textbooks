# Chaos Theory

## Introduction

> section: introduction
> id: pendulum

At the beginning of the 18th century, physicists like [Isaac Newton](bio:newton)
thought that the universe was a giant clockwork machine. If you had precise
information about every object right now, you could use the laws of physics to
predict what would happen in the future.

::: column(width=320)

    x-geopad.sticky.pendulum(width=320 height=320)
      canvas(width=640 height=640)
      svg
        circle(x="point(160,160)" name="c")
        circle.red(x="p")
        path.thick.red(x="segment(c,p)")
      button.btn Play

::: column.grow

One great example is the pendulum. You’ve already seen how you can use
gravity and differential equations to find an equation that predicts the
position of the pendulum at any time in the future.

{.fixme} Newtonian, Deterministic

{.fixme} Watch the pendulum for some time, and try to predict what it’ll do next!

:::

---
> id: double-pendulum

::: column(width=320)

    x-geopad.sticky.pendulum(width=320 height=320)
      canvas(width=640 height=640)
      svg
        circle(x="point(160,160)" name="c")
        circle.yellow(x="a1")
        circle.yellow(x="a2")
        path.thick.yellow(x="polyline(c,a1,a2)")
        circle.green(x="b1")
        circle.green(x="b2")
        path.thick.green(x="polyline(c,b1,b2)")
        circle.blue(x="c1")
        circle.blue(x="c2")
        path.thick.blue(x="polyline(c,c1,c2)")
        circle.red(x="d1")
        circle.red(x="d2")
        path.thick.red(x="polyline(c,d1,d2)")
      button.btn Play

::: column.grow

Now let’s try to make things a bit more complicated by adding a second pendulum
underneath the first one, to make a __double pendulum__.

{.fixme} Once again watch the motion of the pendulum, and try to predict what
it wll do next!

{.fixme} The double pendulum still follows Newton’s laws of gravity.

{.fixme} For small swings, the double pendulum behaves very regularly, but for
larger swings, its behaviour is completely irregular.

{.fixme} We can even have multiple double pendulums next to each other, with
slightly different initial positions. If we let them go simultaneously, 

:::

---
> id: double-pendulum-1

Mathematicians call this behaviour [__chaotic__](gloss:chaos): even if you know
the physical laws of the system, it is impossible to predict what might happen
in the future. Tiny changes in the initial conditions are quickly amplified and
lead to a completely different motion.

It is important to realise that _chaos_ is very different from _randomness_. The
double pendulum contains no element of chance or probability. It follows the
precise, deterministic laws of gravity, and nevertheless moves completely
unpredictably.

{.r} Chaos appears in many unexpected places in nature and mathematics. In this
course, we will explore some of these examples, and discover how mathematics can
help us understand them.
_{button.next-step} Continue_

---
> id: butterfly

### The Butterfly Effect

::: column.grow

In 1962, the mathematician [Edward Lorenz](bio:lorenz) was working at MIT, where
he was developing computer simulations of the atmosphere, to predict
the weather.

Lorenz had developed an algorithm that took current weather data like
temperature, humidity and wind speed as inputs. It then calculated how these
values would change a few minutes into the future. By repeating the process over
and over again, he was able to predict the weather days, or even weeks into the
future.

::: column(width=320)

    x-media(src="images/lgp30.jpg" width=320 height=280)

{.caption} Edward Lorenz used an LGP-30, one of the first off-the-shelf
computers.

:::

One day, Lorenz decided to run parts of his simulation a second time, with the
same input data. To his surprise, the weather predictions created in both cases
were completely different!

{.r} At first, Lorenz thought there must be a bug in the code – but he quickly
worked out what was actually going on. When running the simulation a second time,
he had rounded some of the input values to fewer decimal places (for example
0.506 instead of 0.506127). Even though the difference is tiny, less than 0.1%,
it seems to have been enough to cause the simulation to make completely
different forecasts.
_{button.next-step} Continue_

---
> id: butterfly-1
> goals: flap

::: column(width=280)

    .r
      x-water-canvas(width=280 height=380 src="images/america.jpg")
      .butterfly
      .tornado
    x-gesture(target=".butterfly")

::: column.grow

Lorenz called this the __butterfly effect__: even the flap of a butterfly’s
wings in Brazil might change the weather conditions enough to set off a tornado
in Texas, at some point in the future.

Usually, you’d expect a small change to the input parameters also lead to a
small change in the output. For chaotic systems, like the weather or the double
pendulum, the opposite is true. Even tiny changes can grow quickly, and lead
to huge differences.

This is why weather prediction only works for a few days into the future. After
that, slightly inaccurate weather data can lead to completely different
forecasts.

::: 

---
> id: butterfly-2
> goals: video

There is an important difference between _knowing the physical laws_ of a
system, and being able to _predict its behaviour_. Newtons laws of gravity tell
us exactly how the double pendulum should move. The differential equations of
fluid dynamics should, in principle, allow us to calculate the weather at any
time in the future.

Unfortunately, for this to work in practice, we would have to measure the
initial state of the pendulum with infinite precision, or know the exact
position of every particle in the atmosphere – and that is clearly impossible.
Over time, tiny measurement errors will completely throw off our predictions.
In other words, we can _never_ have a perfect weather forecast!

::: figure

    x-video(src="images/weather.mp4" poster="images/weather.jpg" width=640 height=360 controls credit="© NASA")
    // source: https://svs.gsfc.nasa.gov/12163

{.caption} NASA uses satellites, planes and thousands of ground-based weather
stations to take “snapshots” of the atmosphere: measuring important indicators
like wind speed, rainfall, humidity, air pressure, and ocean currents.

:::

---
> id: dominoes
> goals: video

Of course, a butterfly doesn’t actually _cause_ a tornado – but it might change
the conditions of the atmosphere just enough so that a tornado happens _now_
rather than at some other time in the future.

You could think about it as a series of dominoes with increasing size. A small
action that topples the first domino later leads to the largest domino falling:

::: figure

    x-video(src="images/dominoes.mp4" poster="images/dominoes.jpg" width=480 height=270 controls credit="© Gerrydomino, YouTube")

{.caption} The world’s largest domino toppling.

:::

---
> id: applications
> goals: video

### More Applications

You’ve already seen that the double pendulum and the weather behave chaotically,
but there are countless other examples in nature and technology:

::: column(width=200)

    x-video(src="images/reaction.mp4" poster="images/reaction.jpg" width=200 height=200 credit="© Tim Kench, YouTube")
    // source: https://www.youtube.com/watch?v=PpyKSRo8Iec

{.caption} The __Belousov–Zhabotinsky__ reaction occurs when you mix _bromate_
with an acid. (Shown at 20x speed, © Tim Kench)

::: column(width=200)

    x-media(lightbox src="images/finance.jpg" width=200 height=200)

{.caption} __Stock markets__, inflation and other parts of the economy are
chaotic, making them very difficult to predict.

::: column(width=200)

    x-media(lightbox src="images/heart.jpg" width=200 height=200)

{.caption} Scientists hope that explaining the origin of chaotic
__heartbeats__ (_ventricular fibrillation_) can lead to a cure.

    // Often life threatening abnomal heartbeat after a heart attack. Maybe
    // chaos can predict this and help design better pacemakers.

    // The main benefit to having a chaotic heart is that tiny variations in the
    // way those millions of cells contract serves to distribute the load more
    // evenly, reducing wear and tear on your heart and allowing it to pump
    // decades longer than would otherwise be possible.

::: column(width=200)

    x-media(lightbox src="images/city.jpg" width=200 height=200)

{.caption} __Population dynamics__ often is chaotic – from the number of humans
in a city, to rodent, fish or insect populations.

::: column(width=200)

    x-media(lightbox src="images/stars.jpg" width=200 height=200 credit="Hubble/ESO")

{.caption} __Variable stars__ pulsate by altering their brightness over time.
Some of these stars pulsate in a chaotic pattern.

    // https://en.wikipedia.org/wiki/Stellar_pulsation

::: column(width=200)

    x-media(lightbox src="images/code.jpg" width=200 height=200)

{.caption} Computers can use chaotic systems to generate pseudo-__random
numbers__, or to securely encrypt images.

:::

---
> id: applications-1 

Chaotic behaviour has also been found in electronic circuits, evolutionary
biology as well as dripping water taps, and scientists around the world are
researching many other applications.

    // https://en.wikipedia.org/wiki/Chua%27s_circuit
    // https://www.quantamagazine.org/can-scientists-predict-the-future-of-evolution-20140717/

But in all these examples, the existence of chaos means that there are
fundamental limits to how well we can predict the future. This is often called
a __prediction horizon__, beyond which it is impossible to make any accurate
forecasts.

::: column(width=300)

    x-media(src="images/forecast.jpg" width=300 height=280)

::: column.grow

The weather forecast currently has a prediction horizon of approximately one
week, and even with much better technology in the future, we might never surpass
two weeks of accuracy.

{.r} Instead, scientists can use probability to predict _averages_: for example
how often they’d expect certain weather events (like a tornado) to occur in a
year. These averages can be very accurate, even if we don’t know _when exactly_
a tornado might happen.
_{button.next-step} Continue_

:::

---
> id: definitions

Let’s summarise the key properties of _chaos_ that we have discovered so far:

::: .theorem

* A __chaotic system__ follows precise, [[deterministic|probabilistic|unpredictable]]
  laws, often described by one or more differential equations.
* {.reveal(when="blank-0")} Chaotic systems are highly __sensitive to change__.
  [[Tiny|Large]] initial differences multiply over time and can lead to
  [[huge|small|random]] differences in the result.
* {.reveal(when="blank-1 blank-2")} The behaviour is __unpredictable__ and
  non-repeating, even though it follows deterministic laws. It might even _look
  random_, but only because it depends on imperceptible changes or measurement
  errors.

:::

---
> id: definitions-1

Chaos theory tells us that we can never predict the future, or know in advance
what outcome our actions might have. This can be worrying if you consider how
much in our world depends on mathematical predictions: from modelling the wind
flowing around airplanes or skyscrapers, to assessing the impact of climate
change.

---
> id: pop-culture
> goals: video

On the other hand, chaos theory and the butterfly effect were such simple and
powerful ideas, that they soon started to appear in books, music lyrics, and
even in movies:

::: figure

    x-video(src="images/jurassic-park.mp4" poster="images/jurassic-park.jpg" width=480 height=270 audio controls)

{.caption} Extract from the movie _Jurassic Park_ (© Universal Pictures, 1993) 

:::



--------------------------------------------------------------------------------



## Mathematical Billiard

> id: pool
> section: billiard
> sectionBackground: dark casino
> sectionStatus: dev

One of the most surprising properties of chaos is that it can appear in really
simple systems. You've already seen the double-pendulum in the previous section.
Another fascinating example are billiard tables.

* https://plus.maths.org/content/chaos-billiard-table
* https://en.wikipedia.org/wiki/Dynamical_billiards
* http://mathworld.wolfram.com/Billiards.html
* https://www.bristol.ac.uk/media-library/sites/pace/documents/corina-powerpoint%20standard.pdf
* http://mathcircle.wustl.edu/uploads/4/9/7/9/49791831/20160306-billiards-presentation.pdf
* http://people.maths.ox.ac.uk/tanner/Prospects2010/CUlcigraiTalk.pdf

{.fixme} Imagine you are trying to predict the path a ball on a billiard table will take in response to a push. The rules at play simple: the ball's acceleration is equal to the force applied divided by its mass (that's Newton's second law of motion) and when it hits a side, the angle of reflection is equal to the angle of incidence (strictly speaking you also need to include the effect of friction, but that's not too hard to do).

{.fixme} The trouble is that in your average pub setting you can't easily measure the exact amount of force applied to the ball, the exact angle with which it hits a side, and so on. As you make your calculations, this small initial uncertainty can snowball, so that pretty soon your prediction may become so uncertain as to be useless. That "sensitivity to ignorance" is the hallmark of mathematical chaos.

    svg(width=760 height=440 viewBox="0 0 760 440")
      rect(x="20" y="20" width="720" height="400" fill="green")

{.fixme} Two billiard tables next to each other, move one ball a small amount

{.fixme} Real Life Applications (semiconductors)

---

### Elliptical Billiard

    figure: x-pool-table: svg(width=760 height=440 viewBox="0 0 760 440")

---

### Chaotic Scattering

{.fixme} Gaspard–Rice system



--------------------------------------------------------------------------------



## The Three Body Problem

> sectionStatus: dev
> section: three-bodies

Poincare etc.

{.fixme} There are two chaotic systems which affect us greatly. The first is the weather. Although weather equations are pretty well understood and are solved by computers every day, it is impossible to take into account all the factors influencing the weather (remember the butterfly). No set of data is perfect, nor are computers perfect at solving the equations. The effects of these small
 errors build up remarkably quickly. After about ten days it is essentially impossible to forecast weather with any degree of accuracy.

{.fixme} Chaos is also key to understanding the solar system. Whilst the motion of the planets is very predictable, the motion of many of the asteroids is not. Although asteroids do obey Newton's laws, they may well have orbits which move erratically about space. Such an erratic asteroid is thought to have hit the Earth 65 million years ago and wiped out the dinosaurs. The consequences of a similar
 incident occurring today are unthinkable; the nature of chaotic motion means that such events are virtually impossible to predict until too late.

{.fixme} In 1887, the French mathematician Henri Poincaré showed that while Newton’s theory of gravity could perfectly predict how two planetary bodies would orbit under their mutual attraction, adding a third body to the mix rendered the equations unsolvable. The best we can do for three bodies is to predict their movements moment by moment, and feed those predictions back into our equations … Though the dance of the planets has a lengthy prediction horizon, the effects of chaos cannot be ignored, for the intricate interplay of gravitation tugs among the planets has a large influence on the trajectories of the asteroids. Keeping an eye on the asteroids is difficult but worthwhile, since such chaotic effects may one day fling an unwelcome surprise our way. On the flip side, they can also divert external surprises such as steering comets away from a potential collision with Earth.



--------------------------------------------------------------------------------



## Phase Space and Strange Attractors

> sectionStatus: dev
> section: attractors

Phase diagram for pendulum:
https://youtu.be/MjPFHWul2J0?t=29

circles => equilibrium

spirals
friction => stable attractor

Fox + rabbit, dynamical systems

Poincaré-Bendixson theorem (equilibrium, limit cycle)

Vector fields, equilibrium
2D => simple, deterministic, 3D => not!

---

Water mill

Sinaï-Ruelle-Bowen measure / statistics / forecasting

* https://www.youtube.com/watch?v=xQ3mJxr2NAY
* https://bl.ocks.org/gcalmettes/c3363abb74fe219b283782f055b72386

{.fixme} Mathematicians use the concept of a “phase space” to describe the possible behaviours of a system geometrically. Phase space is not (always) like regular space - each location in phase space corresponds to a different configuration of the system. The behaviour of the system can be observed by placing a point at the location representing the starting configuration and watching how that point moves through the phase space.

{.fixme} In phase space, a stable system will move predictably towards a very simple attractor (which will look like a single point in the phase space if the system settles down, or a simple loop if the system cycles between different configurations repeatedly). A chaotic system will also move predictably towards its attractor in phase space - but instead of points or simple loops, we see “strange attractors” appear - complex and beautiful shapes (known as fractals) that twist and turn, intricately detailed at all possible scales.

{.fixme} Another feature of chaotic systems is that they can suddenly flip from one behaviour to another, very different, one. Think about how some kinds of debt can suddenly become a risk rather than an asset to banks. Such a sudden change is known as a phase transition. One way to see a phase transition in action is to play with a tap. Turn it on very slowly and you hear a regular drip, drip,
 drip. Turn it up slightly and the drips become more frequent and not all the same size. A tiny bit more, and the drips become completely irregular and unpredictable: chaos sets in. Keep going, and the water settles down to a smooth column. However once you increase too much, the water starts twisting, frothing and spiralling: turbulence begins. By steadily increasing the flow we see regularity
 and chaos, without leaving the world of determinism.



--------------------------------------------------------------------------------



## The Logistic Map

> sectionStatus: dev
> section: logistic-map

* https://www.dwitter.net/d/12018
* https://geoffboeing.com/2015/03/chaos-theory-logistic-map/
* Feigenbaum constant
