# Special relativity

## A bit of history
- 1800 CE : A simpler universe
  - the world was a Newtonian clockwork
    - <img src="https://img.ronzz.org/img/brilliant-graphics/compression/capture_26-12-2025-18-11-32.png" style="width:300px">Newtonian clockwork
  - classic reference frames : position is relative, but time is constant 
    - Galilean transformation
    - <img src="https://img.ronzz.org/img/brilliant-graphics/relativity/classic-relativity.svg" alt="classic Galilean transformation" style="width: 300px;">
- 1900 CE : tout bascule
  - <img src="https://img.ronzz.org/img/brilliant-graphics/relativity/relative-clock.gif" alt="relative clock" style="width: 300px;">
  - relativity theory : time is also relative
  - spacetime : space and time are not fundamentally different

## the spacetime diagram

- simplest way to illustrate the phenomenon of temporal relativity
- <img src="https://img.ronzz.org/img/brilliant-graphics/relativity/spacetime-diagram.svg" alt="space-time diagram" style="width: 300px;">
- events : points 
- $$ (T,C) $$


## Getting up to speed : c

- history of $c$
- 1676 : Ole C. Rømer, Danish astronomer 
  - discovered systematic differences in the orbital period of Io — one of Jupiter's moons
  - depending on the time of year
- how possible ?
  - <img src="https://img.ronzz.org/img/brilliant-graphics/relativity/astronomical-relativity-1.svg" alt="astronomical-relativity-1" style="width: 300px;">
  - $$ T_{obs}=T_{Io} $$
  - <img src="https://img.ronzz.org/img/brilliant-graphics/relativity/astronomical-relativity-2.svg" alt="astronomical-relativity-2" style="width: 300px;">
  - point 1 : $$ (\frac{X_1}{c},X_1) $$
  - point 2 : $$  (\frac{X_2}{c}+T_{Io},X_2) $$
  - $$ T_{obs}=T_2-T_1=(\frac{X_2}{c}+T_{Io})-\frac{X_1}{c}=T_{Io}-\frac{(X_2-X_1)}{c} $$
  - $$ X_2-X_1=T_{obs}v,\ where\ v\ is\ speed\ of\ Io\ relative\ to\ earth $$
  - $$ T_{obs}=T_{Io}-\frac{(T_{obs}v)}{c} $$
  - $$ T_{obs}=\frac{T_{Io}}{1+\frac{v}{c}} $$

## Wave : breaking intuition

- wave speeds are independent of source speed
  - <img src="https://img.ronzz.org/img/brilliant-graphics/relativity/speed-of-light-is-constant.webp" alt="speed-of-light-is-constant" style="width: 300px;">
  - <img src="https://img.ronzz.org/img/brilliant-graphics/relativity/speed-of-light-is-constant-2.webp" alt="speed-of-light-is-constant-2" style="width: 300px;">
- <img src="https://img.ronzz.org/img/brilliant-graphics/relativity/AM-EM.svg" alt="AM-EM-2" style="width: 300px;"> bikeride misadventure 1
  - if $v_0=0$ : $$ T_0=\frac{L_0}{c_{sound}} $$
  - $v_0\neq 0$ : $$ \Delta T_{v_{0}} = \frac{L_0}{c_{sound}-v_0} \gt T_0 $$
- <img src="https://img.ronzz.org/img/brilliant-graphics/relativity/AM-EM-2.svg" alt="AM-EM" style="width: 300px;"> bikeride misadventure 1
  - $$ \Delta T=\frac{\sqrt{L_0+v_0\Delta T}}{c_{sound}} $$
  - solve for Delta T 
    -  $$ \Delta T_{v_{0}} = \frac{L_0}{\sqrt{c_{sound}^2-v_{0}^2}} $$ $$ = \frac{\frac{L_0}{c_{sound}}}{\sqrt{1-\frac{v_{0}^2}{c_{sound}^2}}} =  \frac{T_0}{\sqrt{1-\frac{v_{0}^2}{c_{sound}^2}}} \gt T_0 $$

## Michelson & Morley experiment
- <img src="https://img.ronzz.org/img/brilliant-graphics/relativity/michelson-morley-1.gif" alt="Michelson&Morley-experiment-1" style="width: 300px;"> $$ v \parallel L_0 $$
  - $$ \Delta T_R=\frac{L_0}{c-v} $$
  - $$ \Delta T_L=\frac{L_0}{c+v} $$
  - $$ \Delta T_{parallel\ total}= T_R+T_L $$ $$ =\frac{\frac{2L_0}{c}}{1-\frac{v^2}{c^2}} $$
- <img src="https://img.ronzz.org/img/brilliant-graphics/relativity/michelson-morley-2.gif" alt="Michelson&Morley-experiment-2" style="width: 300px;"> $$ v \bot L_0 $$
  - $$ \Delta T_U=\frac{sqrt{L_0^2+(v\Delta T)^2}}{c} $$
  - $$ \Delta T_D=T_U $$
  - $$ \Delta T_{vertical\ total}=T_U+T_D $$ $$ =\frac{\frac{2L_0}{c}}{\sqrt{1-\frac{v^2}{c^2}}} $$
- <img src="https://img.ronzz.org/img/brilliant-graphics/relativity/michelson-morley-3.gif" alt="Michelson and Morley-3" style="width: 300px;"> the experiment
  - expected observation : visible phase shift
    - $$ \Delta T_{parallel-vertical\ difference}=\Delta T_{parallel\ total}- \Delta T_{vertical\ total} $$ $$=\frac{\frac{2L_0}{c}}{1-\frac{v^2}{c^2}}-\frac{\frac{2L_0}{c}}{\sqrt{1-\frac{v^2}{c^2}}} $$ $$\propto L_0 $$
    - $$ \Delta \lambda = c \Delta T_{parallel-vertical-difference} $$
    - if $v=3\cdot 10^5 ms^{-1}$, $L_0=11m$, expecting $$ \Delta \lambda = 1.2 \cdot 10^{-7} $$
    - if $\lambda = 700\ nm$, $$ \varphi = \frac{2\pi \Delta\lambda}{\lambda} $$ $$ = 1.077\ rad $$
  - actual observation : no phase shift
    - $$ \varphi_{experimental} = 0 $$
    - how possible ??
      - no one had an answer

## The decades-long quest on understanding light

- 1860s : Light is a coordinated oscillation of electric and magnetic fields
  - ![EM-wave](/home/rongzhou/Documents/ronzz-img/public/img/science/physics/electricity/EM-Wave.gif)
  - electromagnetic wave
  - $$ c=2.998 \cdot 10^8 $$
  - J. C. Maxwell
    - ![James C. Maxwell](https://upload.wikimedia.org/wikipedia/commons/b/b0/James-Clerk-Maxwell-1831-1879.jpg)
- 1905 : Einstein postulates on relativity
  - Einstein : a patent clerk
    - ![Albert Einstein](../../../../../ronzz-img/public/img/science/physics/electricity/Einstein_patentoffice_full.jpg)
  - constancy of inertial frame
    1. The laws of physics are the same in all inertial frames of reference
      - generalises Newton's 1st law
    1. The speed of light in free space has the same value in all inertial frames
      - revolutionary
      - far-reaching consequences
        - Einstein : "Listen, I've got a theory of light propagation that doesn't require aether."
        - Colleague : "Marvelous !"
        - "In my theory, observers experience events in a different order depending on which direction they're moving."
        - "Rats !"
        - (imagined conversation)

## Mind-boggling implications of the constancy of $c$

- example : "simultaneous" laser firing 
- ![laserfiring](../../../../../ronzz-img/public/img/brilliant-graphics/relativity/laser-competition.svg)
- ![shuttle-observation](../../../../../ronzz-img/public/img/brilliant-graphics/relativity/shuttle-observation.webp)
  - $$ v \gt 0 $$
- ![laser-shooting-A](../../../../../ronzz-img/public/img/brilliant-graphics/relativity/laser-shooting-A.webp)
  - ![spacetime diagram A](../../../../../ronzz-img/public/img/brilliant-graphics/relativity/laser-firing-1.svg)
  - $$ \begin{cases} T_A=\frac{\frac{X_0}{2}+vT_A}{c} \\ T_B=\frac{\frac{X_0}{2}-vT_A}{c} \end{cases} $$
  - $$ \Rightarrow \begin{cases} T_A=\frac{X_0}{2(c-v)} \\ T_B=\frac{X_0}{2(c+v)} \end{cases} $$
  - $$ T_A-T_B=\frac{\frac{x_0v}{c^2}}{1-(\frac{v}{c})^2} \gt 0 $$
  - According to observer in the shuttle, **Alain** fires before **Binida**
- ![laser-shooting-B](../../../../../ronzz-img/public/img/brilliant-graphics/relativity/laser-shooting-B.webp)
  - by symmetry, $$ T_B-T_A=\frac{\frac{x_0v}{c^2}}{1-(\frac{v}{c})^2} \gt 0 $$
  - According to observer in the shuttle, **Binida** fires before **Alain** !
- According to Alain and Binida ?
  - " We fired at the same time ! "
    - $$ T_A-T_B=0 $$ !
  - " Otherwise how can the laser beams arrive at the target simultaneously ? "

## Lorenz Transformation

- Galilean system
  - $X$
    - relative $ \Delta X $ : agreement ✅
    - absolute : disagreement ❌
  - $T$
    - relative $ \Delta T $ : agreement ✅
    - absolute : agreement ✅
  - ![Galilean-system](../../../../../ronzz-img/public/img/brilliant-graphics/relativity/Galilean-system.svg)
- Einstein's system
  - $X$
    - relative $ \Delta X $: disagreement ❌
    - absolute : disagreement ❌
  - $T$
    - relative $ \Delta T $ : disagreement ❌
    - absolute : disagreement ❌
  - ![Einstein-system](../../../../../ronzz-img/public/img/brilliant-graphics/relativity/Einstein-system.svg)
- Reasoning towards Lorenz transformation
  - ![Einstein-system-1](../../../../../ronzz-img/public/img/brilliant-graphics/relativity/Einstein-system-1.svg)
  - own position is always origin in own reference
    - $$ t=\frac{x}{v} \Rightarrow x'=0 $$
    - $$ \therefore x=vt \Rightarrow x'=0 $$
  - all events along line $x'=0$ are simultaneous
    - $$ x= \frac{tc^2}{v} \Rightarrow t'=0 $$
    - $$ \therefore t= \frac{vx}{c^2} \Rightarrow t'=0 $$
  - implied constraint : the transformations must be linear
    - otherwise the resultant spacetime frame would curve in the original frame !
    - ![imaginary-non-linear-system](../../../../../ronzz-img/public/img/brilliant-graphics/relativity/imaginary-non-linear-system.svg)
  - $$ \therefore \begin{cases} x' \propto (x-vt) \\ t' \propto (t-\frac{vx}{c^2}) \end{cases}  $$
    - explanation : $$ a \propto b \Rightarrow a=kb $$. In effect it guarantees the quantity on the left can be expressed as a multiple of the quantity on the right.
    - Since $$ \begin{cases} x=vt \Rightarrow x-vt=0 \\ x= \frac{tc^2}{v} \Rightarrow t-\frac{vx}{c^2}=0 \end{cases} $$ respectively
    - It is guaranteed that $$x'=0$$ and $$t'=0$$ respectively under those conditions
  - $$ \therefore \begin{cases} x' = f(v) (x-vt) \\ t' = g(v) (t-\frac{vx}{c^2}) \end{cases} $$
  - By 1st postulate of special relativity (symmetry of laws of physics)
    - $f(v)$ $g(v)$ must be even functions of $v$ 
      - $$ \begin{cases} f(v)=f(-v) \\ g(v)=g(-v) \end{cases} $$
      - otherwise ![imaginary-non-symmetric-system](../../../../../ronzz-img/public/img/brilliant-graphics/relativity/imaginary-non-symmetric-system.svg)
        - time flowing backwards ?!
        - order of events inversed if relative motion reversed ?!
    - $$ \therefore \begin{cases} x' = \gamma(v^2) (x-vt) \\ t' = \phi(v^2) (t-\frac{vx}{c^2}) \end{cases} $$


