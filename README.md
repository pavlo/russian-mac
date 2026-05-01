# russian-mac.el

Quail input method for Emacs that implements the **Russian Mac keyboard layout** (ЙЦУКЕН) — the layout macOS uses by default when you switch to Russian.

If you type in Russian on a Mac and want Emacs to respect the same key positions you already know, this is the package you need.

## Why a separate layout?

The standard `russian-computer` input method bundled with Emacs follows the Windows/PC ГОСТ layout. The Mac layout differs in the **shifted number row** and a few other keys, so muscle memory breaks down.

### Keyboard layout

```
Mac Russian layout
┌────┬────┬────┬────┬────┬────┬────┬────┬────┬────┬────┬────┬────┬──────────┐
│ §> │ 1! │ 2" │ 3№ │ 4% │ 5: │ 6, │ 7. │ 8; │ 9( │ 0) │ -_ │ =+ │  delete  │
├────┴──┬─┴──┬─┴──┬─┴──┬─┴──┬─┴──┬─┴──┬─┴──┬─┴──┬─┴──┬─┴──┬─┴──┬─┴──┬─────┤
│  tab  │ Й й│ Ц ц│ У у│ К к│ Е е│ Н н│ Г г│ Ш ш│ Щ щ│ З з│ Х х│ Ъ ъ│ \ёЁ │
├───────┴──┬─┴──┬─┴──┬─┴──┬─┴──┬─┴──┬─┴──┬─┴──┬─┴──┬─┴──┬─┴──┬─┴──┬────────┤
│  caps    │ Ф ф│ Ы ы│ В в│ А а│ П п│ Р р│ О о│ Л л│ Д д│ Ж ж│ Э э│ return │
├──────────┴──┬─┴──┬─┴──┬─┴──┬─┴──┬─┴──┬─┴──┬─┴──┬─┴──┬─┴──┬─┴────┴────────┤
│    shift    │ Я я│ Ч ч│ С с│ М м│ И и│ Т т│ Ь ь│ Б б│ Ю ю│    shift      │
└─────────────┴────┴────┴────┴────┴────┴────┴────┴────┴────┴───────────────┘
```

### Shifted number row comparison

| Key   | Mac layout | Standard (PC/ГОСТ) |
|-------|:----------:|:------------------:|
| `1`   | `!`        | `!`                |
| `2`   | `"`        | `"`                |
| `3`   | `№`        | `№`                |
| `4`   | `%`        | `;`                |
| `5`   | `:`        | `%`                |
| `6`   | `,`        | `:`                |
| `7`   | `.`        | `?`                |
| `8`   | `;`        | `*`                |
| `9`   | `(`        | `(`                |
| `0`   | `)`        | `)`                |

### Special keys

| Physical key | Mac Russian |
|:------------:|:-----------:|
| `` ` ``      | `]` / `[` (tilde → `[`) |
| `\`          | `ё`         |
| `\|`         | `Ё`         |
| `/`          | `/`         |
| `§`          | `>`         |

## Installation

### Manual

Copy `russian-mac.el` to your load path (e.g. `~/.emacs.d/`) and add to your config:

```elisp
(load-file "~/.emacs.d/russian-mac.el")
(setq default-input-method "russian-mac")
```

### use-package (straight.el)

```elisp
(use-package russian-mac
  :straight (:host github :repo "pavlo/russian-mac")
  :config
  (setq default-input-method "russian-mac"))
```

## Usage

Toggle the input method with `C-\`. When active, the mode line shows `RU`.

To activate temporarily: `C-u C-\` — prompts for an input method.

## License

MIT
