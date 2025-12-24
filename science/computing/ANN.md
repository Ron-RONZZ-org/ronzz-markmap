# Artificial Neural Network

- data $\longrightarrow$ features $\longrightarrow$ deterministic/probabilistic classifications/predictions $\longrightarrow$ decision
  - everyday examples
    - weather report $\longrightarrow$ clothes tomorrow
    - price from competitors $\longrightarrow$ buy here or elsewhere
- feature space
  - <img src="https://img.ronzz.org/img/brilliant-graphics/capture_24-12-2025-17-06-37.png" alt="feature space" style="width: 300px;">
  - $\sum_{i=0}^{n}w_ix_i \ge b $
- binary neuron
  - $
    y = 
    \begin{cases}
    1 & \text{if } \sum_{k=1}^{n} w_k x_k - b \ge 0 \\
    0 & \text{otherwise}
    \end{cases}
    $

- sigmoid neuron
  - <img src="https://img.ronzz.org/img/brilliant-graphics/sigmoid-neuron.gif" alt="sigmoid neuron" style="width: 300px;">
  - <img src="https://img.ronzz.org/img/brilliant-graphics/sigmoid-neuron-2.gif" alt="sigmoid neuron" style="width: 300px;">
  - sigmoid functions
    - general form : $O=\sigma((\sum I_iw_i)-b)$
    - most common : $O=\frac{1}{1+e^{b-(\sum I_iw_i)}}$
    - <img src="https://img.ronzz.org/img/brilliant-graphics/capture_24-12-2025-18-38-27.png" alt="sigmoid functions" style="width: 300px;">
    - error tolerance
  - parameters
    - bias
    - input weight
- identity neuron
  - $O=(\sum I_iw_i)-b$

- layers of abstraction : "hidden neurons"
  - Neural network $\longrightarrow$ Logic gate
    - <img src="https://img.ronzz.org/img/brilliant-graphics/XOR.gif" alt="XOR" style="width: 300px;">
  - hidden layers
    - <img src="https://img.ronzz.org/img/brilliant-graphics/hidden-layers-ANN.png" alt="hidden layers" style="width: 300px;">
  - curve fitting
    - <img src="https://img.ronzz.org/img/brilliant-graphics/curve-fitting.png" alt="curve fitting" style="width: 300px;">
    - <img src="https://img.ronzz.org/img/brilliant-graphics/capture_24-12-2025-18-23-02.png" alt="multiple decision boundaries" style="width: 300px;">
      - $\longrightarrow$ <img src="https://img.ronzz.org/img/brilliant-graphics/multiple-decision-boundaries.gif" alt="multiple decision boundaries" style="width: 300px;">
    - overfitting
      - unecessary complexity
  - universal approximation
    - binary neuron pair
      - <img src="https://img.ronzz.org/img/brilliant-graphics/binary-neuron-pair.gif" alt="binary neuron pair" style="width: 300px;">
      - $O=B_1-B_2$
    - network
      - universal approximation theorem
      - <img src="https://img.ronzz.org/img/brilliant-graphics/universal-approximation-theorem.png" alt="universal approximation theorem" style="width: 300px;">
- training
  - shape prediction
    - <img src="https://img.ronzz.org/img/brilliant-graphics/capture_24-12-2025-19-26-22.png" alt="shape prediction" style="width: 300px;">
  - weight map
     - <img src="https://img.ronzz.org/img/brilliant-graphics/weight-map-1.png" alt="weight map" style="width: 300px;">
     - <img src="https://img.ronzz.org/img/brilliant-graphics/weight-map.png" alt="weight map" style="width: 300px;">

