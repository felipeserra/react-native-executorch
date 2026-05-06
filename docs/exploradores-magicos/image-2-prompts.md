# Exploradores Mágicos — Guia de Imagens para OpenAI Image 2.0

Este documento define os prompts visuais iniciais para gerar fundos, personagens, sprites, botões, ícones e assets do jogo.

> Importante: para publicação em loja, todos os personagens devem ser originais. Evite nomes, aparência, roupas, cabelos, poderes e poses que lembrem franquias conhecidas.

## 1. Direção visual global

Estilo oficial:

```text
Ilustração 2D infantil, fantasia mágica, cores vibrantes, aparência premium de jogo mobile, traços limpos, atmosfera acolhedora, iluminação cinematográfica suave, sem texto, sem marcas, sem personagens de franquias famosas, composição vertical mobile 9:16, alta definição, pronto para uso como background de app.
```

Regras para geração:

1. Não usar personagens conhecidos, marcas ou franquias.
2. Não pedir texto dentro da imagem.
3. Fundos sempre sem texto e com espaço visual para cards de UI.
4. Personagens devem ter fundo transparente quando possível.
5. Sprites devem manter a mesma roupa, paleta e proporção.
6. Criar variações por estado: idle, falando, pensando, comemorando, erro e andando.
7. Para botões e ícones, pedir fundo transparente.

## 2. Fundos por tela

### 2.1 Splash Screen — Portal do Castelo

Uso: `assets/backgrounds/bg_splash_castle_portal.png`

```text
Ilustração 2D infantil estilo fantasy adventure, castelo mágico distante ao amanhecer, floresta colorida em primeiro plano, caminho de pedras levando até um portal brilhante, partículas douradas flutuando, mapa antigo semi-transparente misturado na composição, espaço livre no centro para logotipo, sem texto, sem personagens, formato vertical 9:16, alta definição, cores vibrantes e acolhedoras.
```

### 2.2 Login — Sala de Mapas

Uso: `assets/backgrounds/bg_login_map_room.png`

```text
Sala mágica de mapas em ilustração 2D infantil premium, mesa de madeira com pergaminhos, bússola dourada, cristais azuis brilhando, janela ao fundo mostrando céu estrelado, livros flutuando lentamente, iluminação quente e acolhedora, espaço livre no centro para botão de login, sem texto, sem personagens, formato vertical 9:16.
```

### 2.3 PIN Parental — Cofre Mágico

Uso: `assets/backgrounds/bg_parental_pin_vault.png`

```text
Cofre mágico infantil em uma parede de pedra clara, runas azuis luminosas ao redor, cadeado dourado no centro, pequenos cristais e estrelas mágicas, atmosfera segura e acolhedora, sem aparência assustadora, espaço livre no centro inferior para teclado de PIN, sem texto, formato vertical 9:16.
```

### 2.4 Cadastro da Família — Casa Mágica

Uso: `assets/backgrounds/bg_family_magic_home.png`

```text
Casa mágica aconchegante em estilo cartoon 2D infantil, jardim colorido, janelas com luz quente, pequenos cogumelos brilhantes, céu azul suave com nuvens, sensação de família e segurança, espaço livre para formulário no centro, sem texto, sem personagens, formato vertical 9:16.
```

### 2.5 Cadastro da Criança — Guarda-Roupa de Avatares

Uso: `assets/backgrounds/bg_child_avatar_wardrobe.png`

```text
Guarda-roupa mágico infantil cheio de fantasias de explorador, mago, fada, robô e dinossauro, cabides coloridos, espelho redondo brilhante, estrelas pequenas flutuando, visual alegre e organizado, espaço livre no centro para avatar e formulário, sem texto, formato vertical 9:16.
```

### 2.6 Dashboard Adulto — Mesa do Mapa

Uso: `assets/backgrounds/bg_parent_dashboard_map_table.png`

```text
Mesa de madeira vista levemente de cima, mapa mágico aberto com trilhas pontilhadas, bússola dourada, moedas pequenas, pergaminhos e cristais, iluminação quente, bordas com objetos mágicos, centro livre para cards de menu, ilustração 2D infantil premium, sem texto, formato vertical 9:16.
```

### 2.7 Nova Aventura — Portal dos Modos

Uso: `assets/backgrounds/bg_adventure_modes_portals.png`

```text
Clareira mágica com vários portais coloridos representando modos de aventura, portal azul para solo, portal verde para cooperação, portal dourado para festa, portal roxo para desafio, floresta suave ao fundo, estilo 2D infantil, centro com espaço para cards, sem texto, formato vertical 9:16.
```

### 2.8 Escolha de Tema — Galeria Encantada

Uso: `assets/backgrounds/bg_theme_gallery.png`

```text
Galeria mágica infantil com quadros flutuantes representando temas: piratas, espaço, dinossauros, fadas, detetives, magos e guerreiros estelares, chão brilhante, paredes com estrelas, composição organizada com espaço para seleção de cards, sem texto, formato vertical 9:16.
```

### 2.9 Checkpoints — Oficina de Pistas

Uso: `assets/backgrounds/bg_checkpoints_workshop.png`

```text
Oficina mágica infantil onde pergaminhos com símbolos abstratos são preparados, mesa com carimbos, cristais e papéis coloridos, visual de criação de pistas, sem texto legível, sem código real, espaço para lista de checkpoints, formato vertical 9:16.
```

### 2.10 Download IA — Biblioteca Viva

Uso: `assets/backgrounds/bg_model_download_magic_library.png`

```text
Biblioteca mágica infantil com livros flutuando, engrenagens douradas, cristais azuis, um grande livro aberto emitindo luz, partículas de letras abstratas sem formar palavras, espaço livre para barra de progresso, sem texto, formato vertical 9:16, alta definição.
```

### 2.11 Gameplay Floresta — Pista

Uso: `assets/backgrounds/themes/forest/bg_clue_forest.png`

```text
Floresta mágica infantil com árvores amigáveis, cogumelos brilhantes, vagalumes, trilha segura e colorida, luz solar entrando entre folhas, espaço livre no centro para card de charada, estilo 2D mobile game, sem texto, formato vertical 9:16.
```

### 2.12 Scanner — Moldura Mágica

Uso: `assets/overlays/scanner_magic_frame.png`

```text
Moldura mágica para scanner de código, formato quadrado com cantos dourados arredondados, pequenos cristais azuis, brilho suave, centro totalmente transparente, fundo transparente, estilo 2D infantil premium, sem texto.
```

### 2.13 Tesouro Final — Baú Dourado

Uso: `assets/backgrounds/bg_final_treasure_chest.png`

```text
Grande baú mágico dourado aberto emitindo luz quente, moedas e estrelas saindo suavemente, cenário de fantasia infantil, personagens não incluídos, espaço livre superior para mensagem, sem texto, formato vertical 9:16, estilo 2D mobile game premium.
```

## 3. Personagens principais

### 3.1 Mestre Gandaluz — Mentor

Características:

- Senhor sábio, simpático e original.
- Túnica azul com detalhes dourados.
- Cajado com cristal azul.
- Barba branca arredondada.
- Chapéu de mago azul original.
- Expressão acolhedora.
- Visual infantil, sem semelhança com personagens conhecidos.

Prompt base:

```text
Personagem original de mago mentor para jogo infantil, senhor sábio e simpático, estilo sprite 2D cartoon premium, túnica azul com detalhes dourados, chapéu de mago azul original, barba branca arredondada, cajado com cristal azul brilhante, expressão acolhedora, proporções chibi leves, contorno limpo, cores vibrantes, fundo transparente, sem texto, sem semelhança com personagens de franquias famosas.
```

Sprites necessários:

| Arquivo | Prompt complementar |
|---|---|
| `mentor_idle.png` | em pé, sorrindo, cajado apoiado, pose neutra |
| `mentor_talking.png` | falando, mão levantada, boca aberta amigável |
| `mentor_thinking.png` | olhando para cima, mão no queixo, estrela acima da cabeça |
| `mentor_hint.png` | segurando pergaminho brilhante, expressão de dica |
| `mentor_success.png` | levantando cajado, comemorando com estrelas |
| `mentor_error.png` | expressão gentil de tentativa, coçando a cabeça, sem tristeza |
| `mentor_walk_01.png` | andando para direita, primeiro frame |
| `mentor_walk_02.png` | andando para direita, segundo frame |
| `mentor_walk_03.png` | andando para direita, terceiro frame |
| `mentor_walk_04.png` | andando para direita, quarto frame |

### 3.2 Kaion — Guardião da Coragem

```text
Personagem original de guerreiro estelar infantil para jogo mobile, herói místico jovem com cabelo dourado luminoso estilizado, armadura leve branca e dourada, aura suave de energia, expressão corajosa e amigável, estilo sprite 2D cartoon premium, proporções chibi, fundo transparente, sem texto, sem copiar anime ou franquia famosa.
```

### 3.3 Luma — Guardiã da Clareza

```text
Personagem original de guardiã mística infantil, cabelo prateado com tons azul claro, roupa azul e lilás com detalhes de estrelas, segurando pequeno cristal de luz, expressão calma e inteligente, estilo sprite 2D cartoon premium, fundo transparente, sem texto, sem copiar franquias.
```

### 3.4 Thorin — Guardião Veloz

```text
Personagem original de guardião veloz para jogo infantil, pequeno herói místico com roupa verde e dourada, botas brilhantes, pose dinâmica de movimento seguro, sorriso animado, estilo sprite 2D cartoon premium, fundo transparente, sem texto, sem franquias famosas.
```

### 3.5 Zaya — Guardiã da Memória

```text
Personagem original de guardiã da memória para jogo infantil, jovem sábia com roupa roxa e dourada, livro mágico flutuando ao lado, pequenos símbolos abstratos brilhantes, expressão gentil e concentrada, estilo sprite 2D cartoon premium, fundo transparente, sem texto.
```

### 3.6 Orion — Guardião da Estratégia

```text
Personagem original de guardião celestial da estratégia, jovem místico com capa curta azul escura e detalhes prateados, segurando mini mapa estelar, olhar confiante e amigável, estilo sprite 2D cartoon premium, fundo transparente, sem texto, sem copiar franquias famosas.
```

## 4. Personagens simples de ambiente

### Fada Pip

```text
Pequena fada original para jogo infantil, asas translúcidas, vestido verde claro, cabelo castanho curto, expressão alegre, segurando varinha pequena com estrela, estilo sprite 2D cartoon premium, fundo transparente, sem texto.
```

### Duende Tito

```text
Pequeno duende original simpático para jogo infantil, roupa laranja e verde, chapéu pequeno, sorriso travesso mas amigável, segurando uma moeda dourada, estilo sprite 2D cartoon premium, fundo transparente, sem texto.
```

### Coruja Nara

```text
Coruja mágica original para jogo infantil, penas marrons e douradas, óculos redondo pequeno, expressão sábia e fofa, segurando pergaminho com símbolos abstratos sem texto legível, estilo sprite 2D cartoon premium, fundo transparente.
```

### Dragãozinho Bubu

```text
Dragão bebê original para jogo infantil, pequeno, azul claro com barriga amarela, asas pequenas, olhos grandes e amigáveis, expressão encorajadora, sem aparência assustadora, estilo sprite 2D cartoon premium, fundo transparente, sem texto.
```

### Robô Zik

```text
Robô infantil original para tema espacial, corpo arredondado branco e azul, olhos luminosos amigáveis, antena pequena, braços curtos, expressão curiosa, estilo sprite 2D cartoon premium, fundo transparente, sem texto.
```

### Dino Tuca

```text
Dinossauro bebê original para jogo infantil, pequeno triceratops verde claro, olhos grandes, sorriso amigável, postura comemorativa, estilo sprite 2D cartoon premium, fundo transparente, sem texto.
```

## 5. Ícones de itens

Todos em fundo transparente, estilo 2D premium, 512x512.

### Dica do Mentor

```text
Ícone de pergaminho mágico enrolado com brilho azul e dourado, estilo 2D infantil premium, fundo transparente, sem texto.
```

### Bússola Mágica

```text
Ícone de bússola dourada mágica com cristal azul no centro, estilo 2D infantil premium, fundo transparente, sem texto.
```

### Lanterna do Explorador

```text
Ícone de lanterna mágica infantil, corpo dourado, luz amarela suave, estilo 2D premium, fundo transparente, sem texto.
```

### Pergaminho Antigo

```text
Ícone de pergaminho antigo com símbolos abstratos não legíveis, fita roxa, brilho suave, estilo 2D infantil premium, fundo transparente.
```

### Cristal do Tempo

```text
Ícone de cristal azul em forma de ampulheta mágica, partículas douradas ao redor, estilo 2D infantil premium, fundo transparente, sem texto.
```

### Chave Dourada

```text
Ícone de chave dourada mágica com ponta em forma de estrela, brilho suave, estilo 2D infantil premium, fundo transparente, sem texto.
```

## 6. Componentes visuais

### Botão primário

```text
Botão de interface para jogo infantil mobile, formato arredondado, azul mágico com borda dourada, brilho suave, sem texto, fundo transparente, estilo 2D premium.
```

### Card de charada

```text
Card de pergaminho mágico para exibir charada em app infantil, bordas arredondadas, papel claro, detalhes dourados e cristais pequenos, área central limpa e vazia para texto, fundo transparente, estilo 2D premium.
```

### Medalha de Explorador

```text
Medalha dourada mágica com estrela no centro, fita azul, brilho suave, estilo 2D infantil premium, fundo transparente, sem texto.
```

## 7. Estrutura de assets

```txt
assets/
  backgrounds/
  characters/
    mentor/
    kaion/
    luma/
    thorin/
    zaya/
    orion/
    ambient/
  icons/
  overlays/
  ui/
```
