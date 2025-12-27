# Screw theory

- Dual vectors : <a href="https://en.wikipedia.org/wiki/Screw_theory" target="_blank">Mozzi-Chasles theorem</a>
  - <img src="https://upload.wikimedia.org/wikipedia/commons/4/Pure_screw.svg/250px-Pure_screw.svg.png" alt="screw theory motion" style="width: 300px;">
  
  - $$\left\{ \mathcal{T} \right\}_O = \begin{Bmatrix} \vec{F}\ \vec{\mathcal{M}}_O \end{Bmatrix}$$
    - translation
      - $$ \vec{F}$$
        - $$ \begin{Bmatrix} \vec{F_x} \\ \vec{F_y} \\ \vec{F_z} \\ \end{Bmatrix}$$
    - rotation
      - $$ \vec{\mathcal{M}}_O$$
        - $$ \begin{Bmatrix} \vec{M_x} \\ \vec{M_y} \\ \vec{M_z} \\ \end{Bmatrix}$$

- Displacement
  - translation
    - $$ \vec{F}_B=\vec{F}_A$$
  - rotation
    - $$ \vec{\mathcal{M}}_B=\vec{\mathcal{M}}_A+\vec{BA}\wedge \vec{F}_A $$

- Static condition
  - $$\sum \left\{ \mathcal{T} \right\}=0$$

- Planar static equilibrium
  - 3 degrees of freedom
    - $$ \begin{Bmatrix} x\ \ 0 \\ y\ \ 0 \\ 0\ \ M_z \end{Bmatrix}$$
  - solution procedure
    - <img src="https://img.ronzz.org/img/science/physics/mechanics/capture_17-12-2025-20-35-30.png" alt="bicycle stem" style="width: 600px;">
    - links diagram
     - <img src="https://img.ronzz.org/img/science/physics/mechanics/capture_17-12-2025-20-33-54.png" alt="links diagram" style="width: 300px;">
     - <img src="https://img.ronzz.org/img/science/physics/mechanics/capture_17-12-2025-20-37-43.png" alt="joints diagram" style="width: 150px;">
    - identification of potential subsystems
      - <img src="https://img.ronzz.org/img/science/physics/mechanics/capture_17-12-2025-20-38-14.png" alt="subsystems tables" style="width: 500px;">
    - isolation and solution of **approriate** sub-systems
      - 2 links
        - $$ \vec{F_1}=-\vec{F_2}$$
      - 3 unknowns
        - $$ \sum{F_x}=0$$
        - $$ \sum{F_y}=0$$
        - $$ \sum{M_z}=0$$
      - IMPORTANT : all dual vectors must be transformed to the **same base point** !!