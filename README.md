import numpy as np
import matplotlib.pyplot as plt

X = np.array([180, 162, 183, 174, 160, 163, 180, 165, 175, 170, 169, 168, 175, 169, 171, 155, 158, 175, 165, 165])
y = np.array([86, 55, 86.5, 70, 62.5, 64, 60, 72, 93, 89, 75, 56, 89, 45, 60, 72])

X = X.reshape(-1, 1)

X = np.insert(X, 0, 1, axis=1)

theta = np.linalg.inv(X.T @ X) @ X.T @ y

print(f"Giá trị của θ: {theta}")
x1 = 150
x2 = 190

y1 = theta[0] + theta[1] * x1
y2 = theta[0] + theta[1] * x2

plt.xlabel('Chiều cao (cm)')
plt.ylabel('Cân nặng (kg)')
plt.title('Chiều cao và cân nặng của sinh viên VLU')
plt.plot([x1, x2], [y1, y2], 'r-.')
plt.plot(X[:, 1], y, 'bo')
plt.show()

# phananhthu
