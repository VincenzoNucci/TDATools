# TDATools

Set of tools created in order to perform some Topological Data Analysis on a point cloud or a time serie with Python 3.6.


## Packages

### Persentropy
```py
from TDA.persentropy import persentropy

entropies = persentropy([[[0,4] , [3,4]]])
print(entropies)
#output: [0.5]
```

### SlidingWindow

```py
from TDA.slidingWindow import slidingWindow
from mpl_toolkits.mplot3d import Axes3D
from sklearn.decomposition import PCA
import numpy as np

T = 40
NPeriods = 4
N = T*NPeriods
t = np.linspace(0, 2*np.pi*NPeriods, N+1)[:N]
x = np.cos(t)

X = slidingWindow(x, 20, 1, 0.5)

pca = PCA(n_components = 3)
Y = pca.fit_transform(X)

fig = plt.figure()
ax = fig.add_subplot(111, projection='3d')

ax.scatter(Y[:, 0], Y[:, 1], Y[:, 2])
plt.show()
```

## Visualization tools

Script like:
- testKMapper
- testPersim
- visualize2D
- visualize3D

Are different tools that can be used to visualize a csv dataset in deifferent ways, while
- testFFT
- testSlidingWindow

for the moment work only on a precumputed input.