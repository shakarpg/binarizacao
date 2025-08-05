# 🖼️ Projeto: Binarização e Conversão para Tons de Cinza com OpenCV

Este projeto tem como objetivo demonstrar, em Python, como realizar a conversão de uma imagem colorida para:
- **Imagem em níveis de cinza** (valores de 0 a 255)
- **Imagem binarizada** (preto e branco, 0 e 255)

Utilizamos a imagem clássica da Lena como exemplo.

---

## 📌 Etapas do Projeto

1. Carregar a imagem colorida com OpenCV
2. Converter para níveis de cinza usando `cv2.cvtColor`
3. Aplicar a binarização com `cv2.threshold`
4. Exibir os resultados com Matplotlib

---

## 🧪 Tecnologias Utilizadas

- Python 3.x
- OpenCV (`cv2`)
- Matplotlib

---

## 🧱 Código-Fonte

```python
import cv2
import matplotlib.pyplot as plt

# 1. Carrega a imagem colorida (ex: lena.jpg)
imagem_colorida = cv2.imread('lena.jpg')

# Verifica se a imagem foi carregada corretamente
if imagem_colorida is None:
    raise Exception("Erro ao carregar a imagem. Verifique o caminho ou nome.")

# 2. Converte de BGR para RGB para visualização correta
imagem_colorida_rgb = cv2.cvtColor(imagem_colorida, cv2.COLOR_BGR2RGB)

# 3. Converte para tons de cinza
imagem_cinza = cv2.cvtColor(imagem_colorida, cv2.COLOR_BGR2GRAY)

# 4. Aplica limiar para binarização (preto e branco)
_, imagem_binarizada = cv2.threshold(imagem_cinza, 128, 255, cv2.THRESH_BINARY)

# 5. Exibe as imagens
plt.figure(figsize=(15, 5))

plt.subplot(1, 3, 1)
plt.imshow(imagem_colorida_rgb)
plt.title('Imagem Colorida')
plt.axis('off')

plt.subplot(1, 3, 2)
plt.imshow(imagem_cinza, cmap='gray')
plt.title('Imagem em Tons de Cinza')
plt.axis('off')

plt.subplot(1, 3, 3)
plt.imshow(imagem_binarizada, cmap='gray')
plt.title('Imagem Binarizada (PB)')
plt.axis('off')

plt.tight_layout()
plt.show()
```

---

## 🖼️ Exemplo Esperado

| Colorida | Tons de Cinza | Preto e Branco |
|---------|----------------|----------------|
| ![Colorida](images/lena_colorida.jpg) | ![Cinza](images/lena_cinza.jpg) | ![PB](images/lena_pb.jpg) |

> Substitua os arquivos na pasta `/images` pelos resultados gerados por você.

---

## 📥 Requisitos

Instale os pacotes com:

```bash
pip install opencv-python matplotlib
```

---

## 👨‍💻 Autor

Rafael PG — [@shakarpg](https://github.com/shakarpg)