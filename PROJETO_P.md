# Phyton
#alguns projetos iniciais para meu curso na DIO 

from IPython import display
import numpy as np
import cv2
from PIL import Image
from google.colab.patches import cv2_imshow
from google.colab.patches import cv2_imshow

!wget https://upload.wikimedia.org/wikipedia/commons/thumb/0/08/Kitano_Street_Kobe01s5s4110.jpg/2560px-Kitano_Street_Kobe01s5s4110.jpg -O test.jpg
image_path = "teste.jpg"

with open(image_path, 'rb') as f:
  np_image_string = np.array([f.read()])

image = Image.open(image_path)
width, height = image.size


display.display(display.Image(image_path, width =1024))

#Convertendo e printando a imagem em tons de cinza
#abrir a imagem
caminho_imagem = "teste.jpg"
imagem = cv2.imread(caminho_imagem)

#converter para tons de Cinza
imagem_convertida =  cv2.cvtColor(imagem, cv2.COLOR_BGR2GRAY)
suave = cv2.GaussianBlur(imagem_convertida, (7, 7), 0)
cv2_imshow(imagem_convertida)

#formatando a imagem em tons de cinza para binario
#converter para binario
imagem_binario = cv2.threshold(imagem_convertida, 127, 255, cv2.THRESH_BINARY)
ib = cv2.threshold(imagem_convertida, 127, 255, cv2.THRESH_BINARY)
cv2_imshow(imagem_binario[1])

