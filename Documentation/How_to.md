# What I learned

## Venv: Virtual Environment for python packages

To manage Python packages for individual projects, it is best practice to use a virtual environment.

## Creating the venv

1. Open the terminal in VSCode `cmd + J`

    ```bash
    python3 -m venv venv
    ```

    alternatively you can create a hidden folder

    ```bash
    python3 -m venv .venv
    ```

    Hinweis: Der Punkt vor dem Namen (.venv) sorgt dafür, dass macOS und Linux den Ordner als versteckt markieren. VS Code erkennt .venv zudem automatisch als Standardpfad für virtuelle Umgebungen.

## Activate venv and install Dependencies

1. Activate the virtual environment:

    ```bash
    source .venv/bin/activate
    ```

    if you need to deactivate it type:
    ```bash
    deactivate
    ```

2. Install dependencies:

    ```bash
    cd #to the folder where requirements.txt is located
    pip install -r requirements.txt
    ```

3. Allow your code to be able to see 'mlrs2':

    ```bash
    pip install -e.
    ```

    installiert das lokale Projekt im "editierbaren" Modus, sodass Änderungen am Quellcode sofort ohne eine erneute Installation wirksam werden und das Paket systemweit innerhalb der virtuellen Umgebung importierbar ist.

    <details>
    Stell dir vor, du hast ein Programm, das aus vielen kleinen Dateien besteht.
    Normalerweise, wenn du ein Paket installierst (pip install .), kopiert Python den Code in einen speziellen Ordner für installierte Bibliotheken. Wenn du dann etwas an deinem Code änderst, bemerkt Python das nicht, weil es mit der alten, kopierten Version arbeitet.

    Wenn du aber -e (für "editable") nutzt, kopiert Python den Code nicht, sondern legt lediglich eine "Verknüpfung" (einen sogenannten Symlink) in deine Bibliothek-Umgebung.

    Das bedeutet:

    Ohne -e: Änderungen am Code erfordern eine Neuinstallation, um wirksam zu werden.

    Mit -e: Python "schaut" direkt in deinen aktuellen Ordner. Jede Änderung, die du an deinen Skripten speicherst, wird sofort beim nächsten Ausführen übernommen.

    Für Übungen in der Uni ist das ideal, da du ständig den Code bearbeitest und sofort testen willst, ohne jedes Mal pip install neu ausführen zu müssen.

    Ist der Unterschied zwischen dem "Kopieren" und der "Verknüpfung" so etwas verständlicher für dich?

    </details>