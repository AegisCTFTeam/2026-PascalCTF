
- solved by @cooku222

제공해주는 `output.jpg`의 바깥 1px 테두리를 위 스크립트와 동일한 순서로 읽어서
`밝으면 1, 어두우면 0`으로 비트화 한 후 8비트씩 끊어서 문자로 변환하면 플래그를 얻을 수 있다.
⁨
**solve.py**
```
from PIL import Image
import numpy as np

img = Image.open("output.jpg").convert("RGB")
arr = np.array(img)
h, w, _ = arr.shape

coords = []
for x in range(w): coords.append((0, x))
for y in range(1, h-1): coords.append((y, w-1))
for x in range(w-1, -1, -1): coords.append((h-1, x))
for y in range(h-2, 0, -1): coords.append((y, 0))

def bit_of(rgb, thresh=128):
    r,g,b = rgb
    lum = 0.299*r + 0.587*g + 0.114*b
    return 1 if lum > thresh else 0

bits = [bit_of(arr[y, x]) for y, x in coords]

out = []
for i in range(0, len(bits)//8*8, 8):
    v = 0
    for b in bits[i:i+8]:
        v = (v<<1) | b
    out.append(v)

data = bytes(out).decode("latin1", errors="ignore")
print(data)
```

Flag: pascalCTF{Wh41t_wh0_4r3_7h0s3_9uy5???}
