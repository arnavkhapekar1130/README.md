# MA303 Project: Autonomous System Phase Portrait Analyzer

## 📊 Project Overview
This project is a Python-based computational tool designed to analyze and visualize the stability of 2D autonomous systems of linear differential equations. The tool handles systems of the form:
$\dot{x} = ax + by$  
$\dot{y} = cx + dy$

## 🧠 The Mathematics
The core of this tool is based on the **Stability Theorem for Linear Systems**. 

### 1. Eigenvalue Calculation
The tool solves the characteristic equation:
$$\det(A - \lambda I) = 0 \implies \lambda^2 - Tr(A)\lambda + \det(A) = 0$$
where $Tr(A)$ is the trace and $\det(A)$ is the determinant of the system matrix.

### 2. Stability Classification
Using the **Discriminant** ($\Delta = Tr(A)^2 - 4\det(A)$), the tool automatically classifies the equilibrium point at the origin:
* **Saddle Point:** $\det(A) < 0$
* **Spiral Sink/Source:** $\det(A) > 0$ and $\Delta < 0$
* **Node Sink/Source:** $\det(A) > 0$ and $\Delta > 0$

### 3. Nullclines
The tool overlays nullclines (where $\dot{x}=0$ or $\dot{y}=0$) to show where the flow of the system changes direction.

## 🛠 Technical Implementation
* **Language:** Python 3
* **Libraries:** NumPy (Matrix algebra) and Matplotlib (Streamplot visualization)
* **Visuals:** I used the `streamplot` function because it uses numerical integration to accurately trace the trajectories, providing a much higher-quality visual than standard vector arrows.
