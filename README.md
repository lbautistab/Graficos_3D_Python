![WhatsApp Image 2025-04-16 at 4 08 31 PM](https://github.com/user-attachments/assets/c53f8321-68be-4d8f-9fda-9602f8c5219c)


# Funciones de dos variables

Una función de dos variables  $z=f(x,y)$ aplica cada par ordenado  $(x,y)$ en un subconjunto  $D$
del plano real  $\mathbb{R}^2$ a un único número real  $z$. El conjunto  $D$ se llama el dominio de la función. El rango de  $f$ es el conjunto de todos los números reales  $z$ que tiene al menos un par ordenado  $(x,y)∈D$ de manera que  $f(x,y)=z$.  

![Dominio](https://github.com/user-attachments/assets/57009f8d-c144-4d67-a22a-64e970d7a32d)

## **Ejercicio:**
Gráficar la siguiente función: $Z(X, Y) = \frac{\sin\left(\sqrt{X^2 + Y^2}\right)}{\sqrt{X^2 + Y^2}}$

## **Solución:**

```bash
# Importando las librerias necesarias
import matplotlib.pyplot as plt
import numpy as np

# Definir el espacio de la malla
x = np.linspace(-8, 8, 100)
y = np.linspace(-8, 8, 100)
X, Y = np.meshgrid(x, y)

# Calcular R evitando la división por cero
R = np.sqrt(X**2 + Y**2)
R = np.where(R == 0, 1, R)  # Evitar división por cero
Z = np.sin(R) / R

# Crear la figura y los ejes 3D
fig = plt.figure(figsize=(12, 10))
ax = fig.add_subplot(111, projection='3d')

# Superficie 3D con mejor visualización
surf = ax.plot_surface(X, Y, Z, cmap='Spectral_r', edgecolor='none')

# Agregar barra de colores
fig.colorbar(surf, ax=ax, shrink=0.5, aspect=10)

# Etiquetas y título
ax.set_xlabel('Eje X')
ax.set_ylabel('Eje Y')
ax.set_zlabel('Eje Z')
ax.set_title('Superficie 3D')

# Mostrar la figura
plt.show()
```
![Gráfico en 3D](https://github.com/user-attachments/assets/f2c8bc35-b31d-49b1-b405-a7588f48355c)

También puede revisar el video en Youtube:  

https://www.youtube.com/watch?v=pPmFVTYCliM&t=527s

