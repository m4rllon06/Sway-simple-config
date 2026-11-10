# sway-simple-config

Configuração minimalista do **Sway** com **Waybar** e **Fuzzel**, paleta preto acinzentado, estilo dwm/i3.
Feita no Fedora, mas funciona em qualquer distro com Sway.

## Estrutura

```
sway/config          -> ~/.config/sway/config
waybar/config.jsonc  -> ~/.config/waybar/config.jsonc
waybar/style.css     -> ~/.config/waybar/style.css
fuzzel/fuzzel.ini    -> ~/.config/fuzzel/fuzzel.ini
```

## Dependências

- `sway`, `swayidle`, `swaylock`
- `waybar`
- `fuzzel` (menu de aplicativos)
- `foot` (terminal)
- `mako` (notificações)
- `grim`, `slurp`, `wl-clipboard` (screenshots)
- `wireplumber` (`wpctl`), `pavucontrol` (áudio)
- `brightnessctl` (brilho)
- `NetworkManager` / `nm-connection-editor`
- Fonte: **Iosevka Nerd Font**

Fedora:

```sh
sudo dnf install sway swayidle swaylock waybar fuzzel foot mako grim slurp \
    wl-clipboard wireplumber pavucontrol brightnessctl network-manager-applet
```

## Instalação

Faça backup das suas configs atuais e copie os arquivos:

```sh
git clone https://github.com/m4rllon06/sway-simple-config.git
cd sway-simple-config
mkdir -p ~/.config
cp -r sway waybar fuzzel ~/.config/
```

Depois recarregue o Sway com `Super+Shift+c`.

## Ajustes necessários

**Monitores** — a seção `### Saída / wallpaper` em `sway/config` usa os nomes dos meus monitores
(`HDMI-A-1` externo e `eDP-1` do notebook). Liste os seus com:

```sh
swaymsg -t get_outputs
```

e ajuste as linhas `output`, `workspace ... output` e `bindswitch`. Se usa só um monitor,
pode comentar essas linhas.

**Teclado** — o layout está como `br` (ABNT2). Altere `xkb_layout` se necessário.

**Wallpaper** — descomente e aponte para sua imagem:

```
output * bg ~/Imagens/wallpaper.jpg fill
```

## Atalhos principais

| Atalho | Ação |
|---|---|
| `Super+Enter` | Terminal (foot) |
| `Super+d` | Menu (fuzzel) |
| `Super+q` | Fechar janela |
| `Super+h/j/k/l` ou setas | Mover foco |
| `Super+Shift+h/j/k/l` | Mover janela |
| `Super+1..0` | Trocar de workspace |
| `Super+Shift+1..0` | Mover janela para workspace |
| `Super+Shift+space` | Alternar flutuante / tiling |
| `Super+m` / `Super+Shift+m` | Maximizar / restaurar |
| `Super+c` | Centralizar janela |
| `Super+f` | Tela cheia |
| `Super+r` | Modo redimensionar |
| `Super+,` / `Super+.` | Foco no monitor esquerdo/direito |
| `Super+Escape` | Bloquear tela |
| `Alt+Tab` | Próxima janela |
| `Print` / `Shift+Print` | Screenshot tela / área (copia) |
| `Super+Shift+e` | Sair do Sway |

> Por padrão, toda janela nova abre **flutuando** (estilo GNOME/Plasma).
> Para voltar ao tiling clássico, remova as duas linhas `for_window [app_id=".*"]` e `for_window [class=".*"]`.

## Licença

[MIT](LICENSE)
