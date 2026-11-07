# AeroSpace

Config em `~/.aerospace.toml`. O AeroSpace organiza as janelas em mosaico e usa workspaces no lugar dos Spaces do macOS.

A app está em `/Applications/AeroSpace.app`. Não arranca com o Mac. Para aplicar a config:

```bash
aerospace reload-config
```

O ícone na barra de menus mostra o workspace ativo. Documentação: https://nikitabobko.github.io/AeroSpace/guide

## Teclas

| Na config | No teclado |
|---|---|
| `alt` | option ⌥ |
| `ctrl` | control ⌃ |
| `shift` | shift ⇧ |

## Atalhos

| Ação | Atalho |
|---|---|
| Workspace 1–5 do ecrã principal | `⌥` + `1` `2` `3` `4` `5` |
| Workspace 1–5 do monitor de cima | `⌃` + `1` `2` `3` `4` `5` |
| Workspace 1–5 do terceiro monitor | `⌥⌃` + `1` `2` `3` `4` `5` |
| Agarrar a janela e mandá-la para esse workspace | mantém o clique e carrega no atalho de cima |
| Levar a janela para um workspace do ecrã principal | `⌥⇧` + `1` `2` `3` `4` `5` |
| Levar a janela para um workspace do monitor de cima | `⌃⇧` + `1` `2` `3` `4` `5` |
| Abrir o Obsidian | `⌥O` |
| Abrir o Cursor | `⌥C` |
| Abrir o Terminal | `⌥T` |
| Ecrã inteiro da janela focada | `⌥F` |
| Minimizar a janela focada | `⌥M` |
| Flutuante / mosaico | `⌥⇧F` |
| Diminuir / aumentar a janela focada | `⌥⇧A` / `⌥⇧D` |

Se agarrares uma janela (botão do rato carregado) e carregares em `⌥2`, essa janela vai para o workspace 2 e o ecrã segue-a. Sem o rato carregado, `⌥2` só muda de workspace. O mesmo vale para `⌥1`–`⌥5` e para `⌃1`–`⌃5` no monitor de cima.

`⌃1`–`⌃5` são também o atalho do Mission Control para mudar de Space. Em Definições do Sistema → Teclado → Atalhos de teclado → Mission Control, desliga "Mudar para a secretária 1" até à 5. Se não, o macOS fica com essas teclas e o AeroSpace não muda o monitor de cima.

## Monitores

O ecrã principal é o que o macOS marca como principal (barra de menus). Agora é o Built-in Retina Display. O monitor de cima é o `DELL P2422HE (2)`. O terceiro é o `DELL P2422HE (1)`.

| Tecla | Workspace | Onde aparece | Nome na barra de menus |
|---|---|---|---|
| `⌥1` … `⌥5` | 1 … 5 | Ecrã principal | `1` … `5` |
| `⌃1` … `⌃5` | 1 … 5 desse monitor | Dell, em cima | `c1` … `c5` |
| `⌥⌃1` … `⌥⌃5` | 1 … 5 desse monitor | Terceiro Dell | `t1` … `t5` |

Os nomes `c1`–`c5` e `t1`–`t5` existem porque um workspace não pode chamar-se `1` em dois monitores. A tecla é na mesma o número 1–5. Com um só Dell ligado, o macOS tira o `(2)` do nome e os workspaces de cima continuam nesse ecrã. Os `t1`–`t5` só têm monitor enquanto o `(1)` está ligado.

## Mosaico Fibonacic

Esta versão do AeroSpace (0.21.3) não tem um layout com o nome Fibonacci. O mosaico é `tiles`, com duas regras:

- Um contentor não fica com mais de dois filhos.
- Um contentor dentro de outro muda de direção (horizontal, depois vertical).

Quando abre uma janela, a config junta-a com a janela ao lado. A primeira janela ocupa o ecrã. A segunda parte-a ao meio. A terceira parte uma dessas metades, na outra direção, e assim por diante. É a espiral de Fibonacci: cada janela nova corta a anterior, alternando o eixo.

`⌥⇧F` tira a janela focada do mosaico. A mesma tecla volta a pô-la no mosaico.

`⌥F` faz a janela focada ocupar o workspace e esconde as outras desse workspace. A barra de menus fica. É o ecrã inteiro do AeroSpace, não o do macOS (o botão verde).

As margens estão a 0. Uma janela sozinha ocupa o ecrã útil, abaixo da barra de menus.
