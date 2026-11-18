# Snippet-Dateien

In diesem Repository befinden sich meine **Snippet-Dateien** für die Visual Studio Code Erweiterung [HyperSnipsV2](https://marketplace.visualstudio.com/items?itemName=Oskar-Idland.HyperSnipsV2).

## Installation (macOS)

1. Installiere die Erweiterung [HyperSnipsV2](https://marketplace.visualstudio.com/items?itemName=Oskar-Idland.HyperSnipsV2).
2. Repository clonen:

### Ganzes Repository klonen

```bash
(
  mkdir -p "$HOME/Library/Application Support/Code/User/hsnips"
  cd "$HOME/Library/Application Support/Code/User/hsnips"
  setopt null_glob 2>/dev/null || shopt -s nullglob
  for f in * .[^.]*; do mv "$f" "$HOME/Desktop/alte-$f"; done
  git clone https://github.com/04joh/vscode-snippets .
)
```

Bereits vorhandene Dateien werden dabei als `alte-<Dateiname>` auf den Schreibtisch verschoben. 

### Nur einzelne Snippet-Dateien klonen
Beispielsweise `latex.hsnips` und `lean4.hsnips`:

```bash
(
  mkdir -p "$HOME/Library/Application Support/Code/User/hsnips"
  cd "$HOME/Library/Application Support/Code/User/hsnips"
  setopt null_glob 2>/dev/null || shopt -s nullglob
  for f in * .[^.]*; do mv "$f" "$HOME/Desktop/alte-$f"; done
  git clone --filter=blob:none --no-checkout https://github.com/04joh/vscode-snippets .
  git sparse-checkout set --no-cone /latex.hsnips /lean4.hsnips
  git checkout main
)
```

### Alternative
Öffne den hsnips-Ordner, stelle sicher, dass er komplett leer ist, und führe dort aus:

```bash
git clone https://github.com/04joh/vscode-snippets .
```

## Aktualisieren

```bash
cd "$HOME/Library/Application Support/Code/User/hsnips"
git pull
```
