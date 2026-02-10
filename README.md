# OCR + NLP Pipeline com Tesseract e Python

Projeto focado em **Reconhecimento Óptico de Caracteres (OCR)** utilizando
**Tesseract OCR**, integrado com **Python, OpenCV e PyTesseract**, com suporte
a múltiplos idiomas e preparação para técnicas de **NLP**.

## 🎯 Objetivo

Extrair texto de imagens reais (prints, páginas de livros, imagens escaneadas)
com alta precisão, controlando manualmente modelos de linguagem e parâmetros
de segmentação do Tesseract.

## 🧠 Tecnologias Utilizadas

- Python 3
- Tesseract OCR
- PyTesseract
- OpenCV
- Matplotlib
- NLP (planejado)

## ⚙️ Funcionalidades Atuais

- Extração de texto a partir de imagens
- Suporte a **Português (por)** e **Inglês (eng)**
- Configuração manual do diretório `tessdata`
- Ajuste de **Page Segmentation Mode (PSM)**
- Comparação de resultados com diferentes configurações

## 📌 Exemplos de Configuração

```python
config = '--tessdata-dir tessdata --psm 6'
texto = pytesseract.image_to_string(imagem, lang='por', config=config)
