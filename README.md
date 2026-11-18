# Snippet-Dateien

In diesem Repository befinden sich meine **Snippet-Dateien** für die Visual Studio Code Erweiterung [HyperSnipsV2](https://marketplace.visualstudio.com/items?itemName=Oskar-Idland.HyperSnipsV2).

## Installation (macOS)

1. Installiere die Erweiterung [HyperSnipsV2](https://marketplace.visualstudio.com/items?itemName=Oskar-Idland.HyperSnipsV2).
2. Führe im Terminal aus:

```zsh
mkdir -p "$HOME/Library/Application Support/Code/User/hsnips"
cd "$HOME/Library/Application Support/Code/User/hsnips"
for f in * .[^.]*; do mv "$f" "$HOME/Desktop/alte-$f"; done

git clone https://github.com/04joh/vscode-snippets .
```

Bereits vorhandene Dateien werden dabei als `alte-<Dateiname>` auf den Schreibtisch verschoben. Falls der Ordner noch leer ist, kannst du die Fehlermeldung `no matches found: *` ignorieren.


**Alternativ:** Öffne den hsnips-Ordner, stelle sicher, dass er leer ist, und führe dort aus:

```zsh
git clone https://github.com/04joh/vscode-snippets .
```

## Aktualisieren

```zsh
cd "$HOME/Library/Application Support/Code/User/hsnips"
git pull
```
