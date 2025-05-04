
# 🏃 Running Adventure

**Running Adventure** é um jogo de plataforma simples feito com [Pygame Zero](https://pygame-zero.readthedocs.io/en/stable/), onde você controla um herói que corre, pula obstáculos e evita inimigos em três fases diferentes. O objetivo é alcançar o final da última fase sem perder todas as vidas!

---

## 🎮 Como Jogar

- **← Seta para a esquerda**: Anda para a esquerda  
- **→ Seta para a direita**: Anda para a direita  
- **␣ Barra de espaço**: Pula (somente se estiver no chão)

**Objetivo:** Chegue ao lado direito da tela evitando inimigos. Se colidir com um inimigo, perde uma vida. O jogo termina após perder 3 vidas ou completar as 3 fases com sucesso.

---

## 📜 Menu Principal

No menu inicial, você verá três botões:

- **START**: Começa o jogo.
- **SOUND ON/OFF**: Liga ou desliga o som.
- **EXIT**: Fecha o jogo.

---

## 🧠 Explicação do Código (para iniciantes)

O jogo é construído com **Pygame Zero**, uma ferramenta que facilita a criação de jogos em Python sem precisar se preocupar com janelas, eventos ou configurações avançadas.

### 🎮 Estados do Jogo

O jogo tem três "estados":

- `MENU`: Tela inicial
- `PLAYING`: Jogo em andamento
- `CONGRATS`: Tela de parabéns após vencer todas as fases

A variável `game_state` guarda essa informação e muda conforme o jogo avança.

---

### 🦸 Personagem Principal (Hero)

```python
class Hero(Actor):
    def __init__(self, pos):
        ...
```

O **Hero** é o personagem controlado pelo jogador. Ele pode andar para os lados e pular. Usa duas listas de imagens (`images_idle` e `images_walk`) para animar o herói dependendo se ele está parado ou andando.

---

### 👾 Inimigos

```python
class Enemy(Actor):
    def __init__(self, pos, patrol_range):
        ...
```

Os inimigos andam de um lado para o outro e podem pular de vez em quando. Se o herói encostar neles, o jogador perde uma vida.

---

### 🎵 Sons e Música

O jogo usa sons e música de fundo. O botão "SOUND ON/OFF" ativa ou desativa todos os sons, inclusive a música.

```python
music.play('background_music')
```

> Certifique-se de ter os arquivos de áudio e imagens na pasta `images/` e `sounds/`.

---

### 📦 Organização do Código

- `draw()`: Função que desenha tudo na tela.
- `update()`: Atualiza as posições e checa colisões.
- `on_key_down()`, `on_key_up()`: Detecta teclas pressionadas.
- `on_mouse_down()`, `on_mouse_move()`: Detecta cliques e movimentação do mouse no menu.
- `spawn_enemies()`: Cria inimigos para cada fase.

---

## 📁 Requisitos

- Python 3.x
- Pygame Zero instalado:

```bash
pip install pgzero
```

Para rodar o jogo:

```bash
pgzrun nome_do_arquivo.py
```

> Substitua `nome_do_arquivo.py` pelo nome do seu arquivo Python.

---

## ✨ Recursos Necessários

Na pasta do jogo, coloque os seguintes arquivos:

### Imagens (`images/`):

- `hero_idle1.png`, `hero_idle2.png`, `hero_walk1.png`, `hero_walk2.png`
- `enemy_idle1.png`, `enemy_idle2.png`, `enemy_walk1.png`, `enemy_walk2.png`
- `background.png`

### Sons (`sounds/`):

- `background_music.wav` ou `.ogg`
- `hit.wav`
- `jump.wav`

---

## ✅ Conclusão

Este jogo é uma ótima forma de aprender lógica de programação, estruturas de controle e animações simples usando Python.  
Experimente modificar o código, adicionar novos inimigos ou novas fases!

---
