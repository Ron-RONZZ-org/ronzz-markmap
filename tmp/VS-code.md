# Visual Studio Code

- Keyboard Shortcuts
  - `SHIFT+DELETE`: Delete the entire current line
  - `CTRL+L`: Select the entire current line; press repeatedly to select multiple lines downward
  - `ALT+UpArrow / ALT+DownArrow`: Move the line up or down
  - `ALT+SHIFT+DownArrow`: Duplicate the line
  - `ALT+SHIFT+RightArrow`: Smart selection — expand selection
  - `CONTROL+SHIFT+UpArrow / CONTROL+SHIFT+DownArrow`: Create another cursor at the same position on the line above / below
  - `CTRL+` (backtick): Open / toggle the integrated terminal
  - `CTRL+SHIFT+` (backtick): Create a new terminal
  - `ALT+LeftArrow / ALT+RightArrow`: Switch between terminals in the same group (split)
  - `CTRL+PageUp / CTRL+PageDown`: Switch between terminal groups (tabs)
  - <figure>
    <img src="https://ronzz.org/content/images/2025/03/Code_0EI4A0LFwk.gif" alt="Multi-cursor" style="width: 50vw;">
    <figcaption>Multi-cursor animation</figcaption>
  </figure>

- Settings
  - ```json
    "editor.insertSpaces": true,
    "editor.tabSize": 2,
    "editor.formatOnSave": true
    ```

- Navigation
  - `Close tabs`: right-click on an editor tab, then choose the desired option (Close Others, Close All, etc.)

- Linting
  - turn off for a file
    - pylance : `# type: ignore`
# Astuces VSCode/Codium

## Édition de texte

- sélection
    - multi-lignes en indent-sensitive languages (e.g., python)
        - option 1
            - 1 e ligne : `HOME+SHIFT+END`
            - puis : `SHIFT+⬇`
        - option 2
            - dernier ligne : `END`
            - puis : `SHIFT+↕`
        - une astuce : adapter l'indentation après selectionner et avant coller
        
    - `SHIFT+les-flèches` : Sélectionner
        - `↕` : rapide
        - `↔` : lente
    - `ALT+SHIFT+➡`
    - `CTRL+D` : Sélectionner la prochaine occurrence
    - `HOME, SHIFT+END,SHIFT+➡` : Selectionner ligne courant jusqu'a fin de code plié
- navigation
    - `CTRL+CLIC_GAUCHE` : Suivre le lien
    - `CTRL+P` Recherche dans projet
    - `CTRL+SHIFT+P` Commandes et paramètres 
- plier/déplier
    - `CTRL+K`
        - plier : `+ CTRL+ 0`
        - déplier : `+ CTRL+ J`
            
## Suggestions

- Structure de projet
    - Pas toujour claire en VSCode Explorateur
        - Indentation minimale
            - Confusion: faux sens de duplication
                - fichier semble membre de chaque sous-dossier
            Solution: utiliser [`tree`](LinuxMint.md#tree)

## Linting

- Si on trouver linting sur saisir intrusif
    - desinstaller les extensions linters
        - beaucoup n'ont pas les intterupters 
        - ou désactiver par espace de travail
    - `emeraldwalk.runonsave` 
### Désactiver Copilot Suggestions en-ligne

- Ouvrir les paramètres (`CTRL+,`).
- Rechercher `Copilot`.
- Désactiver l'option **Inline Suggestions**.
- Alternativement, ajouter dans `settings.json` :
    ```json
    "editor.inlineSuggest.enabled": false
    ```
- Pour désactiver Copilot complètement :
    - Désactiver l'extension dans la vue Extensions (`CTRL+SHIFT+X`).

## Terminal

- Espace de travail avec plusieur dossiers
    - Emplacement actuel de terminal : Dossier racine de fichier actif

## Copilot

- Fornir un exemple
    - directement collez les codes si possible. Sinon référez par nom de fonctionne. Défensez contre les références par les numéros des lignes
        - pour raison inconnue, les numéros des lignes marche pas comme attedu.
