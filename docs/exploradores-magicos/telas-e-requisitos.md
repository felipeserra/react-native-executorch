# Exploradores Mágicos — Telas e Requisitos Funcionais

## 1. Splash Screen

Objetivo: abrir o app com identidade mágica e verificar sessão local.

Elementos:

- Fundo: castelo mágico ao amanhecer com floresta, mapa antigo e partículas douradas.
- Logo: “Exploradores Mágicos”.
- Animação: brilho surgindo do centro para fora.
- Texto de loading: “Abrindo o portal mágico...”
- Ação automática: verificar token, perfil familiar, PIN e modelo local.

Estados:

- Sessão válida: ir para Dashboard do Adulto.
- Sem sessão: ir para Login.
- Modelo pendente: ir para Download da IA após login.

## 2. Login do Responsável

Objetivo: entrada segura apenas para adulto.

Elementos:

- Fundo: sala de mapas mágicos com pergaminhos, bússola, cristais e janela com céu estrelado.
- Botão principal: “Entrar com Google”.
- Botão secundário: “Conhecer o jogo”.
- Texto: “O adulto cria a aventura. A criança vive a magia.”

Regras:

- Login infantil não existe.
- Após login, backend valida Google ID Token.
- Se primeiro acesso, abrir criação de PIN parental.

## 3. PIN Parental

Objetivo: proteger compras, configurações e saída do modo infantil.

Elementos:

- Fundo: cofre mágico com runas azuis.
- Campo PIN: 4 ou 6 dígitos.
- Confirmação do PIN.
- Botão: “Guardar chave mágica”.

Regras:

- Salvar hash/segredo seguro.
- Exigir PIN em loja, configurações, exclusão de perfil e encerramento de partida infantil.

## 4. Cadastro da Família

Objetivo: criar a conta familiar.

Campos:

- Nome da família.
- Nome do responsável.
- Idioma.
- Consentimento LGPD.
- Permitir IA local.
- Permitir fallback cloud.
- Permitir câmera durante partidas.
- Permitir GPS durante partidas.

Fundo:

- Casa mágica em estilo cartoon, com luz quente saindo das janelas.

## 5. Cadastro da Criança

Objetivo: criar perfil infantil sem coletar dados sensíveis.

Campos:

- Apelido.
- Idade ou faixa etária.
- Avatar.
- Cor favorita.

Elementos visuais:

- Fundo: guarda-roupa mágico de avatares.
- Avatares: explorador, fada, robozinho, dinossauro, aprendiz de mago.

Regras:

- Não pedir sobrenome, escola, telefone, documento ou endereço.
- Idade calibra dificuldade das pistas.

## 6. Dashboard do Adulto

Objetivo: central de criação e gestão das aventuras.

Cards:

- “Nova Aventura”.
- “Continuar Aventura”.
- “Crianças”.
- “Modelos de IA”.
- “Loja”.
- “Histórico”.
- “Configurações”.

Elementos:

- Fundo: mapa mágico sobre mesa de madeira.
- Gandalf/Mestre Gandaluz andando no rodapé.
- Card de quota: “Aventuras grátis hoje: 3/3”.

## 7. Nova Aventura — Modo de Jogo

Objetivo: escolher como a criança joga.

Opções:

- Solo.
- Cooperativo no mesmo aparelho.
- Cooperativo online.
- Competitivo.
- Festa infantil.
- Escola/Terapia.

MVP:

- Implementar Solo e Cooperativo local.

## 8. Nova Aventura — Ambiente

Opções:

- Casa/apartamento: QR Code e imagem.
- Condomínio: QR Code + GPS opcional.
- Parque: GPS + bússola.
- Escola: QR Code + equipes.
- Festa: QR Code + ranking.

MVP:

- Casa/apartamento com QR Code.

## 9. Nova Aventura — Tema

Temas iniciais:

1. Floresta Mágica.
2. Piratas.
3. Espaço.
4. Dinossauros.
5. Detetives.
6. Magos.
7. Guerreiros Estelares.

Cada tema precisa de:

- Fundo do dashboard temático.
- Fundo de pista.
- Fundo de vitória.
- Fundo de erro.
- Fundo de tesouro.
- Mentor principal.
- Dois personagens auxiliares.
- Ícones de itens.
- Música curta.
- Efeitos sonoros.

## 10. Cadastro de Checkpoints

Objetivo: adulto define os pontos físicos da caça.

Campos:

- Nome do local.
- Tipo: QR, GPS, imagem ou manual.
- Dificuldade.
- Observação interna.
- Ordem fixa ou embaralhada.
- Marcar como tesouro final.

Bloqueios automáticos:

- Fogão.
- Tomada.
- Janela.
- Rua.
- Piscina sem adulto.
- Produto químico.
- Objeto cortante.
- Área externa sem supervisão.

## 11. Geração de QR Codes

Objetivo: gerar códigos seguros para imprimir/esconder.

Conteúdo do QR:

```json
{
  "gameId": "uuid",
  "checkpointId": "uuid",
  "nonce": "random",
  "signature": "hmac"
}
```

Regras:

- QR não pode conter resposta em texto puro.
- QR deve expirar por partida.
- PDF de impressão deve ter moldura mágica e nome interno pequeno para o adulto.

## 12. Download da IA

Objetivo: baixar e preparar o modelo local.

Cards:

- Leve: Qwen 3.5 0.8B Quantized.
- Melhor: Qwen 3.5 2B Quantized.
- Futuro/custom: Gemma convertido para `.pte`.

Elementos:

- Fundo: biblioteca mágica com livros flutuando.
- Barra de progresso.
- MB baixados.
- Botão pausar.
- Botão continuar depois.
- Estado de erro.

Regras:

- Usar `downloadProgress` do `useLLM` quando aplicável.
- Se modelo não carregar, usar templates locais.
- Não travar o app em aparelhos incompatíveis.

## 13. Preparação da Aventura

Objetivo: IA cria enredo e charadas.

Etapas visuais:

1. “Lendo os locais seguros...”
2. “Escolhendo uma rota divertida...”
3. “Criando charadas para a idade da criança...”
4. “Chamando os personagens mágicos...”
5. “Aventura pronta!”

## 14. Início Infantil

Objetivo: mudar para modo criança.

Elementos:

- Fundo do tema.
- Gandalf/Mestre Gandaluz com animação idle.
- Texto: “Pequeno explorador, o tesouro sumiu!”
- Botão: “Começar missão”.

Regras:

- Sair exige PIN.
- Ocultar loja, configurações e dados adultos.

## 15. Tela de Pista

Objetivo: apresentar a charada e ações principais.

Elementos:

- Fundo temático com parallax.
- Card da charada.
- Personagem da fase.
- Barra de progresso: “Pista 2 de 6”.
- Botões:
  - “Ouvir”.
  - “Dica”.
  - “Abrir câmera”.
  - “Bússola”.
  - “Inventário”.

Regras:

- Chat livre bloqueado no MVP.
- Dicas evoluem em nível 1, 2 e 3.
- Personagem deve falar no máximo 2 frases.

## 16. Scanner QR

Objetivo: validar checkpoint.

Elementos:

- Preview da câmera.
- Moldura mágica para QR.
- Botão lanterna.
- Botão voltar.

Feedback:

- Certo: brilho dourado, vibração leve e som de vitória.
- Errado: “Esse portal ainda não é o certo”.
- QR inválido: “Esse código pertence a outra aventura”.

## 17. Bússola Mágica

Objetivo: guiar em jogos outdoor.

Elementos:

- Fundo de mapa antigo.
- Bússola animada.
- Distância aproximada.
- Mensagens: “Frio”, “Morno”, “Quente”.

MVP:

- Deixar tela planejada, mas não obrigatória na primeira versão.

## 18. Inventário

Itens:

| Item | Uso |
|---|---|
| Dica do Gandalf | Gera dica gradual |
| Bússola Mágica | Ajuda GPS |
| Lanterna | Liga flash |
| Pergaminho Antigo | Relembra pista anterior |
| Cristal do Tempo | Dá tempo extra |
| Chave Dourada | Pula pista com permissão adulta |

## 19. Acerto

Elementos:

- Fundo: explosão mágica leve.
- Confetes.
- Personagem comemorando.
- Texto: “Você encontrou a pista!”
- Recompensa: moedas, XP ou figurinha.
- Botão: “Próxima charada”.

## 20. Erro

Elementos:

- Fundo: cenário do tema com luz suave.
- Personagem: Dragãozinho Bubu ou Gandalf.
- Texto: “Boa tentativa! Esse ainda não é o lugar certo.”
- Botões: “Tentar de novo” e “Pedir dica”.

Regra:

- Nunca punir, envergonhar ou assustar a criança.

## 21. Tesouro Final

Elementos:

- Fundo: baú grande no cenário do tema.
- Animação: baú abre com luz dourada.
- Personagens comemorando.
- Texto: “Você encontrou o tesouro!”
- Prêmio definido pelo adulto.
- Botão: “Ver resumo”.

## 22. Resumo

Métricas:

- Tempo total.
- Pistas resolvidas.
- Dicas usadas.
- Medalhas.
- Personagem favorito.
- Melhor momento.

Compartilhamento:

- Gerar card seguro, sem localização e sem dados sensíveis.

## 23. Loja

Acesso:

- Somente com PIN parental.

Produtos:

- Plano mensal.
- Plano anual.
- Pacote +5 aventuras.
- Temas premium.
- Personagens premium.
- Ferramentas mágicas.

Regras:

- Criança não compra.
- Criança não vê preço durante gameplay.
