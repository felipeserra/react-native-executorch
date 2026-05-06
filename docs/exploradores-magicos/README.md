# Exploradores Mágicos — Especificação do Produto React Native

> Aplicativo mobile infantil de caça ao tesouro com IA local, personagens 2D animados, QR Code, GPS, multiplayer em tempo real e controle parental.

## 1. Objetivo

Transformar este repositório em uma base de app React Native/Expo usando `react-native-executorch` como motor de IA local para criar uma caça ao tesouro física e digital.

O adulto configura a aventura, define crianças, tema, checkpoints e prêmio final. A criança joga em uma interface lúdica, com personagens animados, charadas geradas por IA local, validação por QR Code/GPS/imagem e recompensas.

## 2. Stack oficial

| Camada | Tecnologia |
|---|---|
| Mobile | React Native + Expo Router |
| IA local | React Native ExecuTorch |
| Modelo leve nativo | Qwen 3.5 0.8B Quantized `.pte` |
| Modelo intermediário | Qwen 3.5 2B Quantized `.pte` |
| Modelo futuro/custom | Gemma exportado para `.pte`, quando disponível no pipeline |
| Estado local | Zustand ou Context + hooks dedicados |
| Storage seguro | Expo SecureStore |
| Banco local/cache | SQLite/AsyncStorage, conforme necessidade |
| Câmera/QR | expo-camera ou react-native-vision-camera + scanner |
| GPS | expo-location |
| Animação | React Native Reanimated, Lottie, Skia opcional |
| Backend | Node.js + Fastify |
| Tempo real | Socket.IO |
| Cache/sessões | Redis |
| Banco persistente | PostgreSQL |
| Pagamentos | Stripe |
| Login | Google Sign-In |

## 3. Premissas técnicas do repositório

- O projeto é um monorepo Yarn 4 com workspaces `packages/*` e `apps/*`.
- O app de exemplo `apps/llm` usa Expo Router.
- A biblioteca `react-native-executorch` expõe hooks como `useLLM` para carregar modelos, acompanhar download, gerar texto, interromper geração e enviar mensagens.
- O projeto exige New React Native Architecture.
- O alvo mínimo do runtime atual é iOS 17 e Android 13.

## 4. Produto

Nome comercial provisório: **Exploradores Mágicos**.

Posicionamento:

> O primeiro app de caça ao tesouro infantil com IA local, onde os pais criam aventuras personalizadas e as crianças exploram o mundo real com segurança.

Diferenciais:

1. IA local para privacidade e funcionamento offline.
2. Personagens com personalidade própria via system prompts.
3. Charadas calibradas por idade.
4. QR Code/GPS/imagem como validação física.
5. Modo festa com lobby e ranking familiar.
6. Controle parental obrigatório para compras e configurações.
7. Assets gerados por OpenAI Image 2.0 com identidade visual consistente.

## 5. Jornada principal

::: mermaid
 graph LR;
 A[Adulto faz login Google] --> B[Cria família e PIN parental];
 B --> C[Cadastra criança e idade];
 C --> D[Escolhe tema, local e modo de jogo];
 D --> E[Cadastra checkpoints QR/GPS/Imagem];
 E --> F[Seleciona ou baixa modelo local];
 F --> G[IA gera enredo e charadas];
 G --> H[Criança inicia aventura];
 H --> I[Gandalf apresenta pista];
 I --> J[Criança explora ambiente real];
 J --> K[App valida QR/GPS/Imagem];
 K --> L{Acertou?};
 L -->|Sim| M[Recompensa e próxima pista];
 L -->|Não| N[Dica gradual e incentivo];
 M --> O{Última pista?};
 O -->|Não| I;
 O -->|Sim| P[Tesouro final e resumo];
:::

## 6. Módulos mobile

```txt
apps/exploradores-magicos/
  app/
    _layout.tsx
    index.tsx
    auth/
      login.tsx
    parent/
      dashboard.tsx
      pin.tsx
      child-profile.tsx
      new-adventure.tsx
      checkpoints.tsx
      model-download.tsx
      store.tsx
      settings.tsx
    game/
      intro.tsx
      clue.tsx
      scanner.tsx
      compass.tsx
      inventory.tsx
      result-success.tsx
      result-fail.tsx
      treasure.tsx
      summary.tsx
    multiplayer/
      lobby.tsx
      leaderboard.tsx
  src/
    assets/
    components/
    config/
    hooks/
    services/
    stores/
    prompts/
    types/
```

## 7. Regras de segurança infantil

1. Criança nunca acessa compra sem PIN parental.
2. Chat livre deve ficar bloqueado no MVP.
3. A criança escolhe apenas botões guiados: “dica”, “não entendi”, “estou perdido”, “comemorar”.
4. O app não deve pedir sobrenome, escola, telefone, endereço ou contato da criança.
5. Câmera e GPS só funcionam durante a partida.
6. Locais perigosos devem ser bloqueados: fogão, tomada, janela, rua, piscina sem adulto, escada perigosa, produto químico, área externa sem supervisão.
7. A IA nunca deve sugerir correr em local perigoso, subir em móveis, mexer em objetos cortantes ou acessar áreas proibidas.

## 8. Modelos locais

| Modelo | Status no projeto | Uso |
|---|---|---|
| Qwen 3.5 0.8B Quantized | Nativo no repositório | Mentor rápido, dicas curtas e charadas simples |
| Qwen 3.5 2B Quantized | Nativo no repositório | Melhor criatividade e raciocínio |
| Gemma 4 2B/4B | Custom/futuro | Exige exportação para `.pte` e cadastro como model source |
| LFM2.5 350M | Alternativa muito leve | Fallback para aparelhos fracos |

## 9. MVP recomendado

Fazer primeiro:

1. App React Native `apps/exploradores-magicos`.
2. Login do adulto.
3. PIN parental.
4. Cadastro de criança.
5. Modo solo com QR Code.
6. Tema “Floresta Mágica”.
7. Download/carregamento do Qwen 3.5 0.8B Quantized.
8. Gandalf como mentor via prompt local.
9. Geração de 3 a 6 charadas por aventura.
10. Validação do QR.
11. Tela de tesouro final.
12. Resumo da aventura.

Fase 2:

1. Multiplayer com Socket.IO/Redis.
2. Ranking familiar.
3. GPS e bússola.
4. Loja com Stripe.
5. Temas premium.
6. Personagens especiais.

## 10. Como rodar a base atual

```bash
yarn install
cd apps/llm
yarn android
# ou
yarn ios
```

## 11. Nova app recomendada

Criar uma nova workspace app:

```bash
mkdir -p apps/exploradores-magicos
```

A nova app deve copiar a estratégia do `apps/llm`:

- Expo Router como entrypoint.
- `initExecutorch` no layout raiz.
- `ExpoResourceFetcher` para download/cache de recursos.
- `useLLM` dentro de hooks especializados.
- Controle global de geração para impedir troca de tela durante inferência.

## 12. Definição de pronto

O MVP estará pronto quando:

- Um adulto conseguir criar uma aventura com pelo menos 3 pistas.
- O app carregar a LLM local ou usar fallback seguro.
- O personagem Gandalf apresentar a história e as charadas.
- A criança conseguir escanear QR Codes e avançar.
- O app finalizar com tesouro, medalha e resumo.
- Nenhuma compra ou configuração adulta estiver acessível sem PIN.
