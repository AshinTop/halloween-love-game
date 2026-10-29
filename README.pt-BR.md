[English](README.md) · [简体中文](README.zh-CN.md) · [Español](README.es.md) · [Português (Brasil)](README.pt-BR.md) · [日本語](README.ja.md)

# Haunted Hearts — Jogo de quebra-cabeça cooperativo de Halloween

👻 Dois fantasminhas, duas metades de coração e uma lanterna para dividir. Leve Luna e Rose por oito salas assombradas em que ajudar o parceiro abre o caminho de casa. Controle os dois personagens ou compartilhe um aparelho e combine os próximos passos com alguém.

**[Jogar agora](https://halloween-love-game.crazy3d.org/)** · [Ver os 12 jogos de Halloween](https://github.com/AshinTop/halloween-games) · [⭐ Dar uma estrela no GitHub](https://github.com/AshinTop/halloween-love-game)

O README está disponível em cinco idiomas. A **interface do jogo oferece apenas inglês e chinês simplificado**.

![Quebra-cabeça Haunted Hearts com Luna, Rose, corações coloridos, portões e uma lanterna compartilhada](docs/images/gameplay.jpg)

## O que torna este jogo especial

- Oito salas de uma tela apresentam portões, caminhos exclusivos e a troca da lanterna.
- Dois fantasmas com movimentos independentes, metades de coração e arcos de saída próprios.
- Desfazer sem limite, reiniciar e receber uma dica calculada para a posição atual.
- Recordes de movimentos e links de salas para revisitar os desafios.
- Cenários SVG originais, sons sintetizados opcionais, teclado, toque e suporte a movimento reduzido.

## Como jogar

Escolha Luna ou Rose e recolha a metade de coração de cada um. Luna usa os pisos azuis de lua e vai ao arco azul; Rose usa os pisos rosas e o arco correspondente. A sala termina quando os dois corações foram recolhidos e cada fantasma está em sua própria saída. Eles não podem ocupar a mesma casa.

As placas de lua e estrela mantêm os portões correspondentes abertos **enquanto estão ocupadas**. Antes de sair de uma placa, confira se o parceiro ainda precisa da passagem. Em algumas salas, outra placa permite que ele assuma a tarefa de segurar o portão.

Só quem carrega a lanterna pode **entrar na névoa**. Passe a luz quando os fantasmas estiverem lado a lado. Quem já está na névoa pode sair depois de entregar a lanterna; essa regra ajuda nas travessias.

As oito salas começam com um reencontro simples e passam a combinar portas, caminhos estreitos e luz compartilhada. Não há cronômetro nem limite de jogadas. As menores rotas iniciais verificadas usam **8, 18, 22, 20, 19, 24, 28 e 30 movimentos**: são desafios extras, não exigências para vencer.

## Controles

| Ação | Como fazer |
| --- | --- |
| Escolher personagem | Clique no retrato ou fantasma; **Q** alterna |
| Mover | Setas / **WASD**, botões de direção ou uma casa vizinha |
| Passar a lanterna | **L** ou o botão de passar, com os personagens lado a lado |
| Desfazer | **Z** ou **Undo** |
| Dica, reinício e seleção de sala | Botões correspondentes no jogo |

## Um pouco de estratégia

Posicione primeiro quem vai ajudar a abrir a passagem. Reserve espaço para os dois se aproximarem na hora de passar a lanterna. A dica seleciona o personagem certo e indica a próxima ação de uma rota mais curta a partir da **posição atual**, mas você faz o movimento. Se não houver mais saída, desfaça algumas jogadas ou reinicie.

## Progresso e links de desafios

Os melhores resultados por sala e as preferências de idioma e som ficam neste navegador. Recarregar reinicia a sala selecionada; os movimentos de uma tentativa incompleta não são retomados. Não há sincronização entre aparelhos.

Um link como o da [sala 6](https://halloween-love-game.crazy3d.org/#room=6) abre o desafio desde o início. Compartilhar copia o resultado real e o link, sem enviar um replay. Se o navegador bloquear a área de transferência, o texto aparece para cópia manual.

## Capturas de tela e vídeo de apresentação

![Haunted Hearts em uma janela compacta com seleção de personagens e botões de direção sempre visíveis](docs/images/mobile.jpg)

Captura real em um iframe compacto. Ela mostra o layout em uma janela pequena, não um teste em celular físico.

[Player de vídeo e transcrição](https://halloween-love-game.crazy3d.org/intro.html) · [Baixar o MP4](docs/media/intro.mp4)

A **apresentação de 24 segundos, sem áudio**, combina capturas reais e legendas. É um passeio visual, não uma partida gravada continuamente nem uma demonstração sonora.

## Perguntas frequentes

### Preciso de outra pessoa para jogar?

Você pode resolver tudo alternando os personagens. Duas pessoas também podem jogar por turnos no mesmo aparelho; não há modo multijogador remoto.

### Por que o portão fechou ou a névoa bloqueou o caminho?

O portão precisa da placa correspondente ocupada. Para entrar na névoa, é preciso estar com a lanterna. Confira as duas condições antes de mover quem está ajudando.

### É uma calculadora de compatibilidade amorosa?

É um jogo de lógica cooperativa com corações e fantasmas. Não pede nomes, avalia relacionamentos nem calcula compatibilidade.

## Executar localmente e incorporar

Inicie um servidor HTTP na raiz do repositório:

```sh
python3 -m http.server 4173
```

Abra **http://localhost:4173/**. Não é preciso compilar nem instalar dependências. Use HTTP: `file://` pode bloquear módulos JavaScript.

Execute as verificações incluídas com Node:

```sh
npm test
```

Os testes verificam as rotas completas das oito salas, colisões, pisos exclusivos, placas, portões, troca da lanterna, entrada na névoa e links de sala inválidos.

```html
<iframe src="https://halloween-love-game.crazy3d.org/?embed=1"
  title="Haunted Hearts"
  style="display:block;width:100%;height:521px;border:0"
  allow="fullscreen" allowfullscreen></iframe>
```

O palco principal tem cerca de **833×521** no desktop. Também foram revisadas janelas de **356×280**, **326×280**, **390×650** e **844×340**. Em áreas muito baixas, use os botões de direção; uma altura de **480 px ou mais** é mais confortável no celular quando disponível. O iframe ativa o layout compacto automaticamente; `?embed=0` mostra a página completa.

Veja [EMBEDDING.md](EMBEDDING.md) para tamanho, armazenamento, foco e permissões. Meça a altura disponível após a barra do site principal.

## Mais pequenas aventuras de Halloween

- **[Moonlit Mirrors](https://halloween-mirror-hearts.crazy3d.org/)** · [Código](https://github.com/AshinTop/halloween-mirror-hearts) — Guie dois fantasmas ao mesmo tempo por tabuleiros espelhados.
- **[Ghost Lanterns 3D](https://halloween-3d.crazy3d.org/)** · [Código](https://github.com/AshinTop/halloween-3d) — Ilumine um jardim de abóboras com regras de Lights Out e pares de almas.
- **[Witch’s Candy Blocks](https://halloween-block-blast.crazy3d.org/)** · [Código](https://github.com/AshinTop/halloween-block-blast) — Encaixe doces em um tabuleiro 8×8 e complete pedidos de poções.
- **[Pumpkin Jam](https://halloween-sprunki.crazy3d.org/)** · [Código](https://github.com/AshinTop/halloween-sprunki) — Monte uma banda de quatro partes e teste a memória no Ghost Echo.

## Créditos e apoio

Criado para **AshinTop** e **Midnight Candy Club**, com design, programação e revisão conduzidos por pessoas com auxílio de IA. Arte e sons sintetizados originais do projeto. Dispensa conta remota; a hospedagem pode adicionar scripts ou registros de acesso.

Gostou? **[Deixe uma estrela no GitHub](https://github.com/AshinTop/halloween-love-game)**. Para relatar problemas, inclua navegador, tamanho do iframe, link e passos para reproduzi-los.
