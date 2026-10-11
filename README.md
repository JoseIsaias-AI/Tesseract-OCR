# Tesseract OCR

![Python](https://img.shields.io/badge/Python-3-3776AB?logo=python&logoColor=white)
![Tesseract](https://img.shields.io/badge/Tesseract-OCR-5A5A5A)
![OpenCV](https://img.shields.io/badge/OpenCV-imagem-5C3EE8?logo=opencv&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?logo=jupyter&logoColor=white)

Pipeline de reconhecimento óptico de caracteres (OCR) com Tesseract, PyTesseract e OpenCV para extrair texto de imagens reais, como capturas de tela, páginas de livro e imagens escaneadas. O projeto controla manualmente o modelo de idioma e o modo de segmentação de página do Tesseract e compara os resultados de cada configuração, servindo de base para etapas futuras de NLP.

## Funcionalidades

- Leitura e conversão de imagens com OpenCV antes da extração.
- Extração de texto com `pytesseract.image_to_string`.
- Suporte a português (`por`) e inglês (`eng`), com o modelo de português baixado para um diretório `tessdata` próprio.
- Ajuste do Page Segmentation Mode (PSM) conforme o tipo de imagem.
- Comparação lado a lado entre a configuração padrão e as configurações ajustadas.

## Configurações testadas

| Configuração | Uso indicado |
|---|---|
| padrão, sem idioma definido | linha de base em inglês |
| `lang='por'` | textos em português com acentuação |
| `--psm 6` | bloco único de texto uniforme, como trechos de livro |
| `--psm 7` | uma única linha de texto |

```python
config = '--tessdata-dir tessdata --psm 6'
texto = pytesseract.image_to_string(imagem, lang='por', config=config)
```

## Stack

- Python 3
- Tesseract OCR e PyTesseract
- OpenCV
- Matplotlib

## Estrutura do repositório

```text
Tesseract-OCR/
├── tesseract.ipynb   # pipeline completo com as comparações
└── textos/           # imagens de teste: capturas, trecho de livro e saídas
```

## Como executar

O notebook foi desenvolvido no Kaggle, com as imagens carregadas como datasets. Para rodar localmente:

1. Instale o Tesseract e o pacote de idioma português:

   ```bash
   # Debian/Ubuntu
   sudo apt install tesseract-ocr tesseract-ocr-por
   ```

   No Windows, use o instalador do [Tesseract at UB Mannheim](https://github.com/UB-Mannheim/tesseract/wiki).

2. Instale as dependências Python:

   ```bash
   pip install pytesseract opencv-python matplotlib notebook
   ```

3. Ajuste nos `cv2.imread` do notebook os caminhos das imagens para a pasta `textos/`.
4. Execute `jupyter notebook tesseract.ipynb`.

## Autor

**José Isaías** · Engenharia de Computação no Inteli ·
[LinkedIn](https://www.linkedin.com/in/joseisaias) ·
[GitHub](https://github.com/JoseIsaias-AI)
