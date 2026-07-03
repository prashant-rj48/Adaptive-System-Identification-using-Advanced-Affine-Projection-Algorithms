# Adaptive-System-Identification-using-Advanced-Affine-Projection-Algorithms
A MATLAB implementation and comparative study of low-complexity adaptive filtering techniques for linear and nonlinear system identification.
***
## 📖 About the Project
Adaptive filtering is one of the fundamental techniques in digital signal processing for estimating unknown systems from observed data. This project investigates both linear and nonlinear system identification using modern adaptive filtering algorithms.

For linear systems, advanced Affine Projection-based algorithms are implemented and compared in terms of convergence speed, computational complexity, and estimation accuracy.

For nonlinear systems, the Adaptive Exponential Functional Link Neural Network (AEFLN) is integrated with adaptive filtering algorithms to model nonlinear behaviors more effectively than conventional linear filters.
***
## ✨ Key Features
### 1️⃣Fast Convergence for Correlated Input Signals
Conventional adaptive algorithms such as NLMS exhibit slow convergence when processing highly correlated input signals. This project implements Affine Projection (AP) and its advanced variants (DAP, O-DAP, and SO-DAP) to significantly improve convergence speed by utilizing multiple recent input vectors and optimized adaptation strategies. The MATLAB simulations demonstrate faster learning and improved steady-state performance under correlated signal conditions.

### 2️⃣ Reduced Computational Complexity
While the AP algorithm provides excellent convergence, its computational cost is high due to repeated matrix inversion. To overcome this limitation, DAP, O-DAP, and SO-DAP are implemented to progressively reduce computational complexity without sacrificing convergence performance. The project includes a detailed theoretical and graphical comparison of algorithm complexity, highlighting the trade-off between computational efficiency and estimation accuracy.

### 3️⃣ Linear & Nonlinear System Identification
The project investigates adaptive filtering for both linear and nonlinear systems. Linear system identification is performed using NLMS, AP, DAP, O-DAP, and SO-DAP, while nonlinear system identification employs FLANN and AEFLN integrated with adaptive filtering algorithms. This comprehensive study demonstrates the evolution of adaptive filtering from simple linear models to advanced nonlinear neural network-based approaches.

### 4️⃣ MATLAB Implementation of Advanced Adaptive Algorithms
All algorithms are developed and simulated in MATLAB following methodologies reported in recent IEEE research. The implementation includes learning curve analysis, convergence evaluation, computational complexity analysis, and nonlinear system modeling. Each algorithm is implemented under identical simulation conditions to ensure a fair and meaningful comparison.

### 5️⃣ Comprehensive Performance Analysis
A detailed comparative analysis is carried out using multiple performance metrics, including Mean Square Error (MSE), Normalized Mean Square Deviation (NMSD), convergence rate, steady-state error, and computational complexity. The repository includes MATLAB-generated graphs that visually demonstrate the strengths, limitations, and practical trade-offs of each adaptive filtering algorithm.

***
## Evolution of Adaptive Filtering Algorithms

                    SYSTEM IDENTIFICATION
                            │
            ┌───────────────┴────────────────┐
            │                                │
            ▼                                ▼
 
    Linear System Identification      Nonlinear System Identification
            │                                │
            ▼                                ▼
          NLMS                            FLANN
            │                                │
     Drawback: Slow convergence      Drawback: Fixed nonlinear basis
     for correlated signals          functions
            │                                │
            ▼                                ▼
           AP                             AEFLN
            │
     Drawback: Matrix inversion
     (High computational complexity)
            │
            ▼
           DAP
            │
     Drawback:
     Fixed adaptation mechanism
            │
            ▼
         O-DAP
            │
     Drawback:
     Additional computation for
     optimal gain vector
            │
            ▼
         SO-DAP


***
## 📈 Algorithm Evolution Table
| Algorithm  | Why Introduced?                                | Main Advantage                                                              | Main Drawback                                        |
| ---------- | ---------------------------------------------- | --------------------------------------------------------------------------- | ---------------------------------------------------- |
| **NLMS**   | Baseline adaptive filter                       | Simple implementation, low complexity                                       | Slow convergence for correlated inputs               |
| **AP**     | Improve NLMS convergence                       | Uses multiple past input vectors, converges faster                          | Matrix inversion increases computational complexity  |
| **DAP**    | Reduce AP complexity                           | Removes expensive matrix inversion while maintaining similar convergence    | Uses a fixed adaptation mechanism                    |
| **O-DAP**  | Improve DAP performance                        | Optimal gain vector improves convergence and steady-state error             | Additional computations for optimal gain calculation |
| **SO-DAP** | Simplify O-DAP                                 | Nearly same performance with reduced computational complexity               | Slight approximation compared to O-DAP               |
| **FLANN**  | Extend adaptive filtering to nonlinear systems | Nonlinear modeling using trigonometric basis expansion                      | Fixed basis functions limit adaptability             |
| **AEFLN**  | Improve FLANN                                  | Adaptive exponential basis functions provide better nonlinear approximation | Slightly higher computational complexity             |

***
## 📈 Simulation Results & Performance Analysis
All simulations were performed in MATLAB under identical experimental conditions to ensure a fair comparison of convergence speed, computational complexity, and nonlinear system identification performance.

### 1. Linear System Identification
This figure compares the convergence performance of adaptive filtering algorithms for linear system identification using correlated autoregressive (AR) input signals. The performance is evaluated using Normalized Mean Square Deviation (NMSD) versus the number of iterations.
Input Signal:-  <img width="450" height="47" alt="image" src="https://github.com/user-attachments/assets/cd4ddbf1-36df-4fca-80e8-9cfac49cdf31" />

<img width="500" height="377" alt="image" src="https://github.com/user-attachments/assets/5c3d09d7-a58f-48a1-97e7-4be6372a3484" />

### Key Observations
NLMS converges slowly because it updates the filter using only the current input sample.

AP converges significantly faster by utilizing multiple recent input vectors.

DAP achieves nearly the same convergence performance as AP while reducing computational complexity.

O-DAP further improves convergence using an optimal gain vector.

SO-DAP provides performance close to O-DAP with lower computational cost.

 ---------------------------------------------- 

### 2. Computational Complexity Comparison
This figure compares the theoretical computational complexity of each adaptive filtering algorithm as the filter length increases. Complexity is measured in terms of the approximate number of arithmetic operations required per iteration.
<img width="500" height="377" alt="image" src="https://github.com/user-attachments/assets/fc7bea86-0e48-4c59-bf0c-07a76592c97a" />
### Key Observations
NLMS has the lowest computational complexity.

AP has the highest complexity because of projection matrix inversion.

DAP substantially reduces AP's computational burden.

O-DAP optimizes the update strategy while maintaining efficient computation.

SO-DAP achieves the best balance between computational complexity and convergence performance.

 ---------------------------------------------- 


### 3. Effect of Step Size (μ) on DAP
This figure illustrates the influence of the adaptive step size (μ) on the convergence behavior of the DAP algorithm.
<img width="500" height="377" alt="image" src="https://github.com/user-attachments/assets/a13bfadf-fe31-48e5-840d-4acdd188b915" />
### Key Observations

A small step size results in stable but slow convergence.

A large step size provides faster convergence but increases steady-state error and may reduce stability.

A moderate step size offers the best trade-off between convergence speed and estimation accuracy.


 ---------------------------------------------- 

### 4. FLANN-Based Nonlinear System Identification
This figure compares the performance of adaptive filtering algorithms for nonlinear system identification using a Trigonometric Functional Link Artificial Neural Network (FLANN). FLANN expands the input signal using trigonometric basis functions, enabling linear adaptive filters to model nonlinear systems.
Uniformly distributed random signal:-     x(n)∼U(−0.5,0.5)

<img width="500" height="377" alt="image" src="https://github.com/user-attachments/assets/72cb7a90-139b-4fbc-bc9e-c802354efca5" />

### Key Observations

AP-FLANN converges faster than NLMS-FLANN due to multiple input vector updates.

DAP-FLANN achieves nearly the same convergence while requiring lower computational complexity.

FLANN successfully models nonlinear system characteristics through functional expansion.


---------------------------------------------- 

### 5. AEFLN-Based Nonlinear System Identification
This figure evaluates the performance of Adaptive Exponential Functional Link Neural Network (AEFLN) integrated with adaptive filtering algorithms for nonlinear system identification.
Unlike FLANN, AEFLN incorporates adaptive exponential basis functions that automatically adjust during learning, resulting in improved nonlinear approximation.


<img width="500" height="377" alt="image" src="https://github.com/user-attachments/assets/98bcdf9c-2e1c-4b90-82b8-c47f4ae81d14" />


### Key Observations
AEFLN achieves faster convergence than FLANN.

AP-AEFLN provides the fastest learning among the compared algorithms.

DAP-AEFLN maintains AP-like convergence while reducing computational complexity.

Adaptive exponential basis functions significantly improve nonlinear modeling accuracy and reduce the final Mean Square Error (MSE).

***








## Real-World Applications
### Active Noise Cancellation (ANC)
<img width="500" height="377" alt="image" src="https://github.com/user-attachments/assets/729fc66d-d5c9-42de-9f74-9cc6fa817d64" />           <img width="377" height="377" alt="image" src="https://github.com/user-attachments/assets/6a406e28-b4dd-467d-9051-1a78e8fd3c6d" />

Active Noise Cancellation systems eliminate unwanted environmental noise by generating an anti-noise signal with the same amplitude and opposite phase. Since surrounding noise changes continuously, adaptive filters are required to update their coefficients in real time. Algorithms such as AP and DAP provide faster adaptation than NLMS, while O-DAP and SO-DAP reduce computational complexity, making them suitable for battery-powered ANC devices. AEFLN further improves performance by compensating for nonlinear distortions introduced by loudspeakers and microphones.

Key Contributions

Real-time environmental noise suppression.                                                                                                                       
Faster adaptation to changing noise conditions.                                                                                                                    
Low-power implementation for portable devices.                                                                                                                     
Improved nonlinear acoustic modeling using AEFLN

---------------------------------------------- 

### Acoustic Echo Cancellation (AEC)
<img width="1300" height="258" alt="image" src="https://github.com/user-attachments/assets/6d98c74c-7094-427f-8a71-bb62691dd088" />
Acoustic Echo Cancellation removes unwanted echoes produced when a loudspeaker's output is captured by a nearby microphone during voice or video calls. Adaptive filters continuously estimate the acoustic path and subtract the estimated echo from the microphone signal. AP and DAP provide superior performance for correlated speech signals, while O-DAP improves tracking in dynamic environments. AEFLN enhances echo cancellation by modeling nonlinear loudspeaker characteristics that conventional linear filters cannot accurately represent.

Key Contributions

Clear voice communication.                                                                                                                                         
Faster convergence in changing acoustic environments.                                                                                                              
Reduced computational cost for embedded systems.                                                                                                                   
Improved cancellation of nonlinear speaker distortion. 


---------------------------------------------- 


### Wireless Communication & Channel Equalization
<img width="536" height="400" alt="image" src="https://github.com/user-attachments/assets/576e0680-a6b8-4cb2-9340-2aabd290f8e1" />
Wireless communication channels are continuously affected by multipath fading, interference, and user mobility. Adaptive filters estimate the channel characteristics and update the equalizer coefficients to recover the transmitted signal accurately. AP offers rapid convergence under highly correlated channel conditions, while DAP, O-DAP, and SO-DAP reduce computational complexity for real-time implementations. AEFLN can additionally compensate for nonlinear effects introduced by RF power amplifiers and communication hardware.

Key Contributions

Adaptive channel estimation.                                                                                                                                       
Real-time equalization for time-varying channels.                                                                                                                  
Reduced computational complexity for mobile devices.                                                                                                               
Compensation of nonlinear hardware impairments.

***

## 📑 References

AP/DAP/O-DAP/SO-DAP IEEE paper.                                                                                                                                    
The FLANN paper.                                                                                                                                                   
The AEFLN paper.                                                                                                                                                   
MATLAB documentation (if used).













