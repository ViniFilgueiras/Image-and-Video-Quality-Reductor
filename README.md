# 🎬 Media Processor

Ferramenta de linha de comando para processamento de imagens, vídeos e áudios com funcionalidades de redimensionamento, compressão e efeitos especiais.

## 📋 Funcionalidades

- **Processamento de Imagens**: Redução ou ampliação de imagens usando algoritmo de mapeamento de pixels
- **Redução de Vídeos**: Diminuição da resolução de vídeos com controle de FPS
- **Processamento de Áudio**: Compressão ou aplicação de efeito "earrape" em arquivos de áudio

## 🚀 Instalação

### Pré-requisitos

- Python 3.7+
- FFmpeg instalado no sistema

### Dependências Python

```bash
pip install pillow opencv-python numpy matplotlib scipy
```

### Instalação do FFmpeg

**Windows:**
- Baixe do [site oficial](https://ffmpeg.org/download.html)
- Adicione ao PATH do sistema

**Linux (Ubuntu/Debian):**
```bash
sudo apt update
sudo apt install ffmpeg
```

**macOS:**
```bash
brew install ffmpeg
```

## 💻 Uso

Execute o programa principal:

```bash
python main.py
```

### Menu Principal

```
Escolha uma opção:
1. Reduzir/Ampliar Imagem
2. Reduzir Vídeo
3. Processar Áudio (compressão ou earrape)
4. Sair
```

### 1️⃣ Processamento de Imagens

Permite reduzir ou ampliar imagens por um fator específico.

**Exemplo:**
```
Caminho da imagem: foto.jpg
Fator (ex: 2 para metade ou dobro): 2
Deseja reduzir ou ampliar? (r/a): r
Digite o nome/caminho para salvar: foto_reduzida.png
```

**Resultado:** Imagem com metade da resolução original

### 2️⃣ Redução de Vídeos

Reduz a resolução de vídeos e opcionalmente processa o áudio.

**Exemplo:**
```
Caminho do vídeo: video.mp4
FPS do novo vídeo (padrão 30): 24
Fator de redução (ex: 2 para reduzir pela metade): 3
Deseja processar o áudio do vídeo?
1. Comprimir
2. Deixar estourado (earrape)
3. Nenhum
Opção: 1
```

**Resultado:** Vídeo com 1/3 da resolução original e áudio comprimido

### 3️⃣ Processamento de Áudio

Processa arquivos de áudio (MP3 ou extrai de MP4).

**Modos disponíveis:**
- **Comprimir**: Reduz o bitrate para economizar espaço (padrão: 64k)
- **Earrape**: Aumenta drasticamente o volume (+20dB)

**Exemplo:**
```
Caminho do arquivo de áudio: musica.mp3
Duração do trecho em segundos: 30
Escolha o modo:
1. Comprimir áudio
2. Deixar estourado (earrape)
Opção: 1
Digite o caminho/nome do áudio de saída: musica_comprimida.mp3
```

## 📁 Estrutura do Projeto

```
.
├── main.py                    # Interface principal do programa
├── image_resize.py            # Módulo de redimensionamento de imagens
├── video_reductor.py          # Módulo de processamento de vídeos
├── audio_quality_reductor.py  # Módulo de processamento de áudio
├── frames/                    # Pasta temporária para frames extraídos
├── final_frames/              # Pasta para frames processados
└── output/                    # Pasta padrão para saídas
```

## ⚙️ Como Funciona

### Algoritmo de Redimensionamento

O programa utiliza um algoritmo de **nearest neighbor** (vizinho mais próximo) para redimensionar imagens:

1. Calcula as novas dimensões baseadas no fator
2. Mapeia cada pixel da nova imagem para o pixel mais próximo da original
3. Preserva a proporção e qualidade dentro das limitações do método

### Processamento de Vídeo

1. Extrai todos os frames do vídeo original
2. Redimensiona cada frame individualmente
3. Recompõe o vídeo com o FPS especificado
4. Opcionalmente processa o áudio separadamente

### Processamento de Áudio

Utiliza FFmpeg para:
- Extrair áudio de arquivos MP4
- Cortar trechos específicos
- Ajustar bitrate (compressão)
- Aplicar ganho de volume (earrape)

## ⚠️ Avisos e Limitações

- **Qualidade**: O método nearest neighbor pode gerar imagens pixeladas em grandes ampliações
- **Espaço em Disco**: Vídeos longos geram muitos frames temporários
- **FFmpeg Obrigatório**: O processamento de áudio requer FFmpeg instalado
- **Earrape**: Use com moderação e cuidado com seus ouvidos! 🔊
  
## 📝 Licença

Este projeto é distribuído sob a licença MIT.

## 👨‍💻 Autor

Vinícius Filgueiras - [@ViniFilgueiras](https://github.com/ViniFilgueiras)

---

⭐ Se este projeto foi útil para você, considere dar uma estrela no GitHub!
