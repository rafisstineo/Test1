# 37 Agent Skills Gratuitas (mojomast/open-higgsfield-skills)

Repositório: https://github.com/mojomast/open-higgsfield-skills (licença MIT)

As 37 skills já estão neste repositório em `.claude/skills/`, então o Claude Code as carrega automaticamente ao abrir este projeto.

## Instalação global (opcional, na sua máquina)
```bash
git clone https://github.com/mojomast/open-higgsfield-skills.git
mkdir -p ~/.claude/skills
cp -r open-higgsfield-skills/skills/* ~/.claude/skills/
```

> Requisito: a maioria das skills precisa de um servidor ComfyUI com GPU (local, Comfy Cloud ou Google Colab via `google-colab-runner`).

## 1. Direção, Roteiro e Planejamento (4)
- video-director: orquestrador principal que transforma uma ideia em um curta-metragem completo.
- story-bible: cria e mantém a bíblia da história (personagens, locações, objetos e estilo visual).
- shot-planning: divide a história em cenas cronometradas com movimentos de câmera e duração.
- previs-control-passes: bloqueia cenas em 3D e exporta passes de controle (OpenPose, profundidade e câmera).

## 2. Geração e Edição de Imagens-Base / Keyframes (5)
- flux3-klein-stills: gera imagens estáticas e keyframes com FLUX 3 Klein ou FLUX.2 Klein.
- image-edit: edita imagens, novos ângulos, push-in e outpainting (Qwen-Image-Edit).
- relighting: altera direção, cor ou horário da iluminação de uma imagem.
- image-to-3d: converte uma imagem em malha 3D (.glb) com TRELLIS.2 ou Pixal3D.
- lora-training: treina um LoRA próprio (personagem, produto ou estilo) via ai-toolkit.

## 3. Geração e Animação de Vídeo (7)
- ltx25-image-to-video: anima uma imagem com LTX-2.5 (frame final e áudio nativo).
- camera-control: movimentos de câmera exatos (órbita, dolly, grua, trajetórias) com Wan Fun Camera e Wan ATI.
- control-to-video: vídeo guiado por profundidade, OpenPose ou bordas.
- audio-driven-motion: vídeo guiado por áudio (avatares, reação musical) com LTX-2.3 e Wan 2.2 S2V.
- lip-sync: sincronia labial ou redublagem (LTX-2.3 e Wan 2.1 InfiniteTalk).
- shot-transitions: clipes de transição entre o último frame de uma cena e o primeiro da próxima.
- ltx-iclora-utils: transferência de movimento, remoção de marcas d'água/legendas, preservação de identidade.

## 4. Efeitos Visuais (VFX), Troca e Estilo (6)
- character-swap-h3: troca pessoa, rosto ou objeto por uma referência (MiniMax H3 / LTX-2.3).
- video-inpaint-remove: remove/substitui objetos com máscaras rastreadas (Wan 2.1 VACE, LTX-2.3, SAM 2).
- one-take-vfx: efeitos em um passe (fogo, desintegração, congelamento, holograma, portal, neon).
- restyle: reestiliza visual ou movimento com base em um vídeo de referência.
- effect-recipe-read: engenharia reversa de um efeito em receita JSON reutilizável.
- background-matte: remove/substitui fundos com BiRefNet e PlateLock.

## 5. Áudio, Voz, Música e Legendas (3)
- voiceover: narração em 23 idiomas (inclui português) com clonagem de voz via Chatterbox TTS.
- music-sfx: trilhas, músicas e efeitos sonoros (ACE-Step 1.5, Stable Audio Open, MiniMax Music 3).
- subtitles-captions: legendas SRT/ASS via Whisper, embutidas com ffmpeg.

## 6. Pós-Produção, Qualidade e Montagem Final (8)
- video-upscale: upscale e restauração com SeedVR2.
- frame-interpolation: aumenta fps (24→60, câmera lenta) via FILM.
- camera-lens-lut: tremor de mão, efeitos de lente, LUT .cube e barras cinematográficas.
- reframe-aspect: reenquadra 16:9 → 9:16, 1:1 ou 4:5 preenchendo bordas com IA.
- film-assembly: montagem final com ffmpeg, sincronia com a música e mixagem da narração.
- still-qa: avalia imagens com Qwen-VL local e refaz se falhar.
- continuity-check: detecta quebras de continuidade entre cenas.
- shot-qc: QC técnico via ffprobe/ffmpeg (frames congelados, tela preta, desfoque, exposição).

## 7. Infraestrutura e Conexão com ComfyUI (4)
- comfyui-connect: envia workflows JSON ao ComfyUI, acompanha e baixa resultados.
- comfyui-preflight: verifica custom nodes e pesos antes de rodar.
- google-colab-runner: executa o projeto no Google Colab se não houver GPU local.
- multi-gpu-dispatch: distribui renderização entre várias GPUs/servidores ComfyUI.
