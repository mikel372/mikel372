import matplotlib.pyplot as plt
import numpy as np

# إعداد الرسم
fig, ax = plt.subplots()
ax.set_aspect('equal')

# رسم الجمجمة (دائرة)
skull = plt.Circle((0.5, 0.5), 0.4, color='black', fill=False, lw=2)
ax.add_patch(skull)

# رسم العينين
eye_left = plt.Circle((0.35, 0.65), 0.08, color='black', fill=True)
eye_right = plt.Circle((0.65, 0.65), 0.08, color='black', fill=True)
ax.add_patch(eye_left)
ax.add_patch(eye_right)

# رسم الأنف (مثلث)
nose = plt.Polygon([[0.5, 0.55], [0.45, 0.4], [0.55, 0.4]], closed=True, color='black')
ax.add_patch(nose)

# رسم الفم (خط منحني)
t = np.linspace(0, np.pi, 100)
x = 0.5 + 0.25 * np.cos(t)
y = 0.3 + 0.1 * np.sin(-t)
ax.plot(x, y, color='black', lw=2)

# إخفاء المحاور
ax.axis('off')

# عرض الرسم
plt.show()
