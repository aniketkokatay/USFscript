# USFScript & MathOS Specification  An implementation of a pure mathematical execution model that translates traditional control flow, conditionals, and state transitions into closed-form algebraic equations using the **Universal Step Function (USF)**.  
## 🌐 Site Link : [USFscript](https://aniketkokatay.github.io/USFscript/)
## 📄 Primary Research Paper  - **Title:** An Elementary Universal Step Function for Translating Programming Constructs into Pure Mathematics 
- **Zenodo DOI/Record:** [10.5281/zenodo.23131071](https://zenodo.org/records/23131071)
- **Author:** Aniket Mandar Kokatay - **ORCID:** [0009-0001-1428-6447](https://orcid.org/0009-0001-1428-6447)

-  ## 📐 Core Foundation  The Universal Step Function $o(x,y,z,p,q)$ maps continuous inputs directly to discrete state outputs without programmatic branching (`if/else` conditionals):  $$o(x,y,z,p,q) = \left\lceil \frac{\vert{}g_x\vert{}}{\vert{}g_x\vert{} + 1} \right\rceil \cdot g_y$$
### Key Relational Operators 
- **Greater Than or Equal ($x \ge y$):** $g_1(x,y) = o(x, 1, y, 0, 0)$
- **Logical Equality ($x = y$):** $e_f(x,y) = g_1(x,y) \cdot g_1(y,x)$  
-  ## 💻 Python Implementation  
```python import math
def usf(x, y, z, p=0, q=0):
  kx = math.floor(x - z)
  ky = math.ceil(abs(y + q))
  gx = abs(kx + 1) + kx + 1 + p
  gy = math.ceil(abs(ky) / (abs(ky) + 1))
  return math.ceil(abs(gx) / (abs(gx) + 1)) * gy
def gte(x, y):
  return usf(x, 1, y, 0, 0)  def equals(x, y):
  return gte(x, y) * gte(y, x)
print("Equality check (5 == 5):", equals(5, 5))
# Outputs 1
print("Equality check (5 == 3):", equals(5, 3))
# Outputs 0
