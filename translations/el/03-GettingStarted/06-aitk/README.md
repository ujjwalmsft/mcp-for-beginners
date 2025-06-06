<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "a3cbadbf632058aa59a523ac659aa1df",
  "translation_date": "2025-05-17T12:22:06+00:00",
  "source_file": "03-GettingStarted/06-aitk/README.md",
  "language_code": "el"
}
-->
# Κατανάλωση ενός διακομιστή από την επέκταση AI Toolkit για το Visual Studio Code

Όταν δημιουργείτε έναν AI πράκτορα, δεν αφορά μόνο τη δημιουργία έξυπνων απαντήσεων. Είναι επίσης για να δώσετε στον πράκτορά σας τη δυνατότητα να αναλάβει δράση. Εκεί μπαίνει το Model Context Protocol (MCP). Το MCP διευκολύνει τους πράκτορες να έχουν πρόσβαση σε εξωτερικά εργαλεία και υπηρεσίες με συνεπή τρόπο. Σκεφτείτε το σαν να συνδέετε τον πράκτορά σας σε ένα εργαλειοθήκη που μπορεί *πραγματικά* να χρησιμοποιήσει.

Ας πούμε ότι συνδέετε έναν πράκτορα στον διακομιστή MCP της αριθμομηχανής σας. Ξαφνικά, ο πράκτοράς σας μπορεί να εκτελεί μαθηματικές λειτουργίες απλώς λαμβάνοντας μια προτροπή όπως «Ποιο είναι το 47 επί 89;» — δεν χρειάζεται να σκληροκωδικοποιήσετε λογική ή να δημιουργήσετε προσαρμοσμένα APIs.

## Επισκόπηση

Αυτό το μάθημα καλύπτει πώς να συνδέσετε έναν διακομιστή MCP αριθμομηχανής σε έναν πράκτορα με την επέκταση [AI Toolkit](https://aka.ms/AIToolkit) στο Visual Studio Code, επιτρέποντας στον πράκτορά σας να εκτελεί μαθηματικές λειτουργίες όπως πρόσθεση, αφαίρεση, πολλαπλασιασμό και διαίρεση μέσω φυσικής γλώσσας.

Το AI Toolkit είναι μια ισχυρή επέκταση για το Visual Studio Code που απλοποιεί την ανάπτυξη πρακτόρων. Οι μηχανικοί AI μπορούν εύκολα να δημιουργήσουν εφαρμογές AI αναπτύσσοντας και δοκιμάζοντας γενετικά μοντέλα AI—τοπικά ή στο cloud. Η επέκταση υποστηρίζει τα περισσότερα από τα κύρια γενετικά μοντέλα που είναι διαθέσιμα σήμερα.

*Σημείωση*: Το AI Toolkit υποστηρίζει αυτήν τη στιγμή Python και TypeScript.

## Στόχοι μάθησης

Μέχρι το τέλος αυτού του μαθήματος, θα είστε σε θέση να:

- Καταναλώνετε έναν διακομιστή MCP μέσω του AI Toolkit.
- Διαμορφώνετε μια διαμόρφωση πράκτορα για να του επιτρέψετε να ανακαλύψει και να χρησιμοποιήσει εργαλεία που παρέχονται από τον διακομιστή MCP.
- Χρησιμοποιείτε εργαλεία MCP μέσω φυσικής γλώσσας.

## Προσέγγιση

Να πώς πρέπει να προσεγγίσουμε αυτό σε υψηλό επίπεδο:

- Δημιουργήστε έναν πράκτορα και ορίστε την προτροπή συστήματός του.
- Δημιουργήστε έναν διακομιστή MCP με εργαλεία αριθμομηχανής.
- Συνδέστε το Agent Builder στον διακομιστή MCP.
- Δοκιμάστε την ενεργοποίηση εργαλείων του πράκτορα μέσω φυσικής γλώσσας.

Ωραία, τώρα που καταλαβαίνουμε τη ροή, ας διαμορφώσουμε έναν πράκτορα AI για να αξιοποιήσει εξωτερικά εργαλεία μέσω MCP, ενισχύοντας τις δυνατότητές του!

## Προαπαιτούμενα

- [Visual Studio Code](https://code.visualstudio.com/)
- [AI Toolkit για Visual Studio Code](https://aka.ms/AIToolkit)

## Άσκηση: Κατανάλωση ενός διακομιστή

Σε αυτήν την άσκηση, θα δημιουργήσετε, εκτελέσετε και βελτιώσετε έναν πράκτορα AI με εργαλεία από έναν διακομιστή MCP μέσα στο Visual Studio Code χρησιμοποιώντας το AI Toolkit.

### -0- Προπαρασκευή, προσθέστε το μοντέλο OpenAI GPT-4o στα My Models

Η άσκηση αξιοποιεί το μοντέλο **GPT-4o**. Το μοντέλο πρέπει να προστεθεί στα **My Models** πριν δημιουργήσετε τον πράκτορα.

![Στιγμιότυπο οθόνης μιας διεπαφής επιλογής μοντέλου στην επέκταση AI Toolkit του Visual Studio Code. Η επικεφαλίδα αναγράφει "Βρείτε το σωστό μοντέλο για τη λύση AI σας" με έναν υπότιτλο που ενθαρρύνει τους χρήστες να ανακαλύψουν, δοκιμάσουν και αναπτύξουν μοντέλα AI. Κάτω, κάτω από "Δημοφιλή Μοντέλα," εμφανίζονται έξι κάρτες μοντέλων: DeepSeek-R1 (φιλοξενείται στο GitHub), OpenAI GPT-4o, OpenAI GPT-4.1, OpenAI o1, Phi 4 Mini (CPU - Μικρό, Γρήγορο), και DeepSeek-R1 (φιλοξενείται στο Ollama). Κάθε κάρτα περιλαμβάνει επιλογές για "Προσθήκη" του μοντέλου ή "Δοκιμή στο Playground](../../../../translated_images/aitk-model-catalog.143ab567942a0c88d21eb49c9f384182a688aa2ca7f44bc263a1c8ee45ee6252.el.png)

1. Ανοίξτε την επέκταση **AI Toolkit** από τη **Γραμμή Δραστηριότητας**.
1. Στην ενότητα **Κατάλογος**, επιλέξτε **Μοντέλα** για να ανοίξετε τον **Κατάλογο Μοντέλων**. Επιλέγοντας **Μοντέλα** ανοίγει τον **Κατάλογο Μοντέλων** σε μια νέα καρτέλα επεξεργαστή.
1. Στη γραμμή αναζήτησης του **Καταλόγου Μοντέλων**, εισαγάγετε **OpenAI GPT-4o**.
1. Κάντε κλικ στο **+ Προσθήκη** για να προσθέσετε το μοντέλο στη λίστα **My Models** σας. Βεβαιωθείτε ότι έχετε επιλέξει το μοντέλο που είναι **Φιλοξενείται από το GitHub**.
1. Στη **Γραμμή Δραστηριότητας**, επιβεβαιώστε ότι το μοντέλο **OpenAI GPT-4o** εμφανίζεται στη λίστα.

### -1- Δημιουργία πράκτορα

Το **Agent (Prompt) Builder** σας επιτρέπει να δημιουργείτε και να προσαρμόζετε τους δικούς σας πράκτορες με AI. Σε αυτήν την ενότητα, θα δημιουργήσετε έναν νέο πράκτορα και θα του αναθέσετε ένα μοντέλο για να τροφοδοτήσει τη συνομιλία.

![Στιγμιότυπο οθόνης της διεπαφής δημιουργίας "Calculator Agent" στην επέκταση AI Toolkit για το Visual Studio Code. Στο αριστερό πάνελ, το επιλεγμένο μοντέλο είναι "OpenAI GPT-4o (μέσω GitHub)." Μια προτροπή συστήματος αναγράφει "Είστε καθηγητής σε πανεπιστήμιο που διδάσκει μαθηματικά," και η προτροπή χρήστη λέει, "Εξήγησέ μου την εξίσωση Fourier με απλούς όρους." Επιπλέον επιλογές περιλαμβάνουν κουμπιά για προσθήκη εργαλείων, ενεργοποίηση διακομιστή MCP και επιλογή δομημένης εξόδου. Ένα μπλε κουμπί "Εκτέλεση" βρίσκεται στο κάτω μέρος. Στο δεξιό πάνελ, κάτω από "Ξεκινήστε με Παραδείγματα," αναφέρονται τρεις δείγμα πράκτορες: Web Developer (με διακομιστή MCP, Second-Grade Simplifier, και Dream Interpreter, καθένας με σύντομες περιγραφές των λειτουργιών τους.](../../../../translated_images/aitk-agent-builder.df46f391ec9a2b0e8cd1ddbb1dbc968c42bb20411350a44d87c8f082ba4a45d5.el.png)

1. Ανοίξτε την επέκταση **AI Toolkit** από τη **Γραμμή Δραστηριότητας**.
1. Στην ενότητα **Εργαλεία**, επιλέξτε **Agent (Prompt) Builder**. Επιλέγοντας **Agent (Prompt) Builder** ανοίγει τον **Agent (Prompt) Builder** σε μια νέα καρτέλα επεξεργαστή.
1. Κάντε κλικ στο κουμπί **+ Νέος Δημιουργός**. Η επέκταση θα ξεκινήσει έναν οδηγό ρυθμίσεων μέσω του **Command Palette**.
1. Εισαγάγετε το όνομα **Calculator Agent** και πατήστε **Enter**.
1. Στον **Agent (Prompt) Builder**, για το πεδίο **Μοντέλο**, επιλέξτε το μοντέλο **OpenAI GPT-4o (μέσω GitHub)**.

### -2- Δημιουργία προτροπής συστήματος για τον πράκτορα

Με τον πράκτορα να έχει δημιουργηθεί, είναι ώρα να ορίσετε την προσωπικότητα και τον σκοπό του. Σε αυτήν την ενότητα, θα χρησιμοποιήσετε τη δυνατότητα **Generate system prompt** για να περιγράψετε την προοριζόμενη συμπεριφορά του πράκτορα—στην προκειμένη περίπτωση, ενός πράκτορα αριθμομηχανής—και θα έχετε το μοντέλο να γράψει την προτροπή συστήματος για εσάς.

![Στιγμιότυπο οθόνης της διεπαφής "Calculator Agent" στο AI Toolkit για το Visual Studio Code με ένα ανοιχτό παράθυρο με τίτλο "Generate a prompt." Το παράθυρο εξηγεί ότι ένα πρότυπο προτροπής μπορεί να δημιουργηθεί με την κοινοποίηση βασικών λεπτομερειών και περιλαμβάνει ένα πλαίσιο κειμένου με την δείγμα προτροπή συστήματος: "Είστε ένας χρήσιμος και αποτελεσματικός βοηθός μαθηματικών. Όταν σας δίνεται ένα πρόβλημα που περιλαμβάνει βασική αριθμητική, απαντάτε με το σωστό αποτέλεσμα." Κάτω από το πλαίσιο κειμένου βρίσκονται κουμπιά "Κλείσιμο" και "Δημιουργία." Στο παρασκήνιο, φαίνεται μέρος της διαμόρφωσης του πράκτορα, συμπεριλαμβανομένου του επιλεγμένου μοντέλου "OpenAI GPT-4o (μέσω GitHub)" και πεδίων για προτροπές συστήματος και χρήστη.](../../../../translated_images/aitk-generate-prompt.fc5fdce97b37f4c22511cc2ed3cc1d85e79ccf21c339e64a9553b9e2cc4dac37.el.png)

1. Για την ενότητα **Προτροπές**, κάντε κλικ στο κουμπί **Generate system prompt**. Αυτό το κουμπί ανοίγει στον δημιουργό προτροπών που αξιοποιεί το AI για να δημιουργήσει μια προτροπή συστήματος για τον πράκτορα.
1. Στο παράθυρο **Generate a prompt**, εισαγάγετε το ακόλουθο: `You are a helpful and efficient math assistant. When given a problem involving basic arithmetic, you respond with the correct result.`
1. Κάντε κλικ στο κουμπί **Generate**. Θα εμφανιστεί μια ειδοποίηση στην κάτω δεξιά γωνία που επιβεβαιώνει ότι η προτροπή συστήματος δημιουργείται. Μόλις ολοκληρωθεί η δημιουργία της προτροπής, η προτροπή θα εμφανιστεί στο πεδίο **System prompt** του **Agent (Prompt) Builder**.
1. Ανασκοπήστε την **System prompt** και τροποποιήστε αν είναι απαραίτητο.

### -3- Δημιουργία διακομιστή MCP

Τώρα που έχετε ορίσει την προτροπή συστήματος του πράκτορά σας—καθοδηγώντας τη συμπεριφορά και τις απαντήσεις του—είναι ώρα να εξοπλίσετε τον πράκτορα με πρακτικές δυνατότητες. Σε αυτήν την ενότητα, θα δημιουργήσετε έναν διακομιστή MCP αριθμομηχανής με εργαλεία για εκτέλεση υπολογισμών πρόσθεσης, αφαίρεσης, πολλαπλασιασμού και διαίρεσης. Αυτός ο διακομιστής θα επιτρέψει στον πράκτορά σας να εκτελεί μαθηματικές λειτουργίες σε πραγματικό χρόνο σε απάντηση σε φυσικές γλωσσικές προτροπές.

![Στιγμιότυπο οθόνης του κάτω τμήματος της διεπαφής Calculator Agent στην επέκταση AI Toolkit για το Visual Studio Code. Δείχνει επεκτάσιμα μενού για "Εργαλεία" και "Δομή εξόδου," μαζί με ένα αναπτυσσόμενο μενού με την ετικέτα "Επιλέξτε μορφή εξόδου" ορισμένο σε "κείμενο." Δεξιά, υπάρχει ένα κουμπί με την ετικέτα "+ MCP Server" για προσθήκη ενός διακομιστή Model Context Protocol. Ένα εικονικό εικονίδιο εικόνας δείχνει πάνω από την ενότητα Εργαλεία.](../../../../translated_images/aitk-add-mcp-server.7696efa0c3d1774d2ba903c86c8782fbc80fcb8ac9e51d7c6089cccc47396386.el.png)

Το AI Toolkit είναι εξοπλισμένο με πρότυπα για διευκόλυνση της δημιουργίας του δικού σας διακομιστή MCP. Θα χρησιμοποιήσουμε το πρότυπο Python για τη δημιουργία του διακομιστή MCP αριθμομηχανής.

*Σημείωση*: Το AI Toolkit υποστηρίζει αυτήν τη στιγμή Python και TypeScript.

1. Στην ενότητα **Εργαλεία** του **Agent (Prompt) Builder**, κάντε κλικ στο κουμπί **+ MCP Server**. Η επέκταση θα ξεκινήσει έναν οδηγό ρυθμίσεων μέσω του **Command Palette**.
1. Επιλέξτε **+ Προσθήκη Διακομιστή**.
1. Επιλέξτε **Δημιουργία Νέου Διακομιστή MCP**.
1. Επιλέξτε **python-weather** ως πρότυπο.
1. Επιλέξτε **Προεπιλεγμένος φάκελος** για αποθήκευση του προτύπου διακομιστή MCP.
1. Εισαγάγετε το ακόλουθο όνομα για τον διακομιστή: **Calculator**
1. Ένα νέο παράθυρο Visual Studio Code θα ανοίξει. Επιλέξτε **Ναι, εμπιστεύομαι τους συγγραφείς**.
1. Χρησιμοποιώντας το τερματικό (**Terminal** > **Νέο Τερματικό**), δημιουργήστε ένα εικονικό περιβάλλον: `python -m venv .venv`
1. Χρησιμοποιώντας το τερματικό, ενεργοποιήστε το εικονικό περιβάλλον:
    1. Windows - `.venv\Scripts\activate`
    1. macOS/Linux - `source venv/bin/activate`
1. Χρησιμοποιώντας το τερματικό, εγκαταστήστε τις εξαρτήσεις: `pip install -e .[dev]`
1. Στην **Προβολή Εξερεύνησης** της **Γραμμής Δραστηριότητας**, επεκτείνετε τον κατάλογο **src** και επιλέξτε **server.py** για να ανοίξετε το αρχείο στον επεξεργαστή.
1. Αντικαταστήστε τον κώδικα στο αρχείο **server.py** με το ακόλουθο και αποθηκεύστε:

    ```python
    """
    Sample MCP Calculator Server implementation in Python.

    
    This module demonstrates how to create a simple MCP server with calculator tools
    that can perform basic arithmetic operations (add, subtract, multiply, divide).
    """
    
    from mcp.server.fastmcp import FastMCP
    
    server = FastMCP("calculator")
    
    @server.tool()
    def add(a: float, b: float) -> float:
        """Add two numbers together and return the result."""
        return a + b
    
    @server.tool()
    def subtract(a: float, b: float) -> float:
        """Subtract b from a and return the result."""
        return a - b
    
    @server.tool()
    def multiply(a: float, b: float) -> float:
        """Multiply two numbers together and return the result."""
        return a * b
    
    @server.tool()
    def divide(a: float, b: float) -> float:
        """
        Divide a by b and return the result.
        
        Raises:
            ValueError: If b is zero
        """
        if b == 0:
            raise ValueError("Cannot divide by zero")
        return a / b
    ```

### -4- Εκτέλεση του πράκτορα με τον διακομιστή MCP αριθμομηχανής

Τώρα που ο πράκτοράς σας έχει εργαλεία, είναι ώρα να τα χρησιμοποιήσετε! Σε αυτήν την ενότητα, θα υποβάλετε προτροπές στον πράκτορα για να δοκιμάσετε και να επικυρώσετε αν ο πράκτορας αξιοποιεί το κατάλληλο εργαλείο από τον διακομιστή MCP αριθμομηχανής.

![Στιγμιότυπο οθόνης της διεπαφής Calculator Agent στην επέκταση AI Toolkit για το Visual Studio Code. Στο αριστερό πάνελ, κάτω από "Εργαλεία," ένας διακομιστής MCP με το όνομα local-server-calculator_server έχει προστεθεί, δείχνοντας τέσσερα διαθέσιμα εργαλεία: πρόσθεση, αφαίρεση, πολλαπλασιασμός και διαίρεση. Ένα σήμα δείχνει ότι τέσσερα εργαλεία είναι ενεργά. Κάτω είναι μια συμπτυγμένη ενότητα "Δομή εξόδου" και ένα μπλε κουμπί "Εκτέλεση." Στο δεξιό πάνελ, κάτω από "Απάντηση Μοντέλου," ο πράκτορας ενεργοποιεί τα εργαλεία πολλαπλασιασμού και αφαίρεσης με εισόδους {"a": 3, "b": 25} και {"a": 75, "b": 20} αντίστοιχα. Η τελική "Απάντηση Εργαλείου" εμφανίζεται ως 75.0. Ένα κουμπί "Προβολή Κώδικα" εμφανίζεται στο κάτω μέρος.](../../../../translated_images/aitk-agent-response-with-tools.64afc99ab720b2cd97d0142ba8f98aca0ddc9eba46f148adc2c35d6979ddb349.el.png)

Θα εκτελέσετε τον διακομιστή MCP αριθμομηχανής στον τοπικό υπολογιστή ανάπτυξής σας μέσω του **Agent Builder** ως πελάτη MCP.

1. Πατήστε `F5` to start debugging the MCP server. The **Agent (Prompt) Builder** will open in a new editor tab. The status of the server is visible in the terminal.
1. In the **User prompt** field of the **Agent (Prompt) Builder**, enter the following prompt: `Αγόρασα 3 αντικείμενα με τιμή $25 το καθένα και στη συνέχεια χρησιμοποίησα έκπτωση $20. Πόσο πλήρωσα;`
1. Click the **Run** button to generate the agent's response.
1. Review the agent output. The model should conclude that you paid **$55**.
1. Here's a breakdown of what should occur:
    - The agent selects the **multiply** and **substract** tools to aid in the calculation.
    - The respective `a` and `b` values are assigned for the **multiply** tool.
    - The respective `a` and `b` οι τιμές ανατίθενται για το εργαλείο **αφαίρεσης**.
    - Η απάντηση από κάθε εργαλείο παρέχεται στην αντίστοιχη **Απάντηση Εργαλείου**.
    - Η τελική έξοδος από το μοντέλο παρέχεται στην τελική **Απάντηση Μοντέλου**.
1. Υποβάλετε επιπλέον προτροπές για να δοκιμάσετε περαιτέρω τον πράκτορα. Μπορείτε

**Αποποίηση ευθυνών**:  
Αυτό το έγγραφο έχει μεταφραστεί χρησιμοποιώντας την υπηρεσία μετάφρασης AI [Co-op Translator](https://github.com/Azure/co-op-translator). Ενώ προσπαθούμε για ακρίβεια, παρακαλώ σημειώστε ότι οι αυτοματοποιημένες μεταφράσεις μπορεί να περιέχουν λάθη ή ανακρίβειες. Το αρχικό έγγραφο στη μητρική του γλώσσα θα πρέπει να θεωρείται η αυθεντική πηγή. Για κρίσιμες πληροφορίες, συνιστάται επαγγελματική ανθρώπινη μετάφραση. Δεν φέρουμε ευθύνη για τυχόν παρεξηγήσεις ή ερμηνείες που προκύπτουν από τη χρήση αυτής της μετάφρασης.