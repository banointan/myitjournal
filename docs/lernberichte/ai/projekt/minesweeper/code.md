# Minesweeper Code

```
import java.util.Random;
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        System.out.println("Beginner Grösse:           	Spalte = 9      Zeile = 9      Anzahl Bomben = 10");
        System.out.println("Fortgeschrittene Grösse:   	Spalte = 16     Zeile = 16     Anzahl Bomben = 40");
        System.out.println("Profis Grösse:             	Spalte = 30     Zeile = 16     Anzahl Bomben = 99");
        System.out.println("Info: Alle * sind Bomben, wenn eines davon aufgedeckt wird, wird das Spiel automatisch beendet.");

        // Ausgabe & Eingabe
        System.out.print("Bitte geben Sie die gewünschte Spalte Grösse ein: ");
        Scanner eingabeSpalte = new Scanner(System.in);
        while (!eingabeSpalte.hasNextInt() && eingabeSpalte.nextInt() > 0) {
            System.out.println("Falsche Eingabe");
            System.out.print("Bitte geben Sie die gewünschte Spalte Grösse ein: ");
            eingabeSpalte = new Scanner(System.in);
        }
        int inputSizeSpalte = eingabeSpalte.nextInt();

        System.out.print("Bitte geben Sie die gewünschte Zeilen Grösse ein: ");
        Scanner eingabeZeile = new Scanner(System.in);
        while (!eingabeZeile.hasNextInt() && eingabeZeile.nextInt() > 0) {
            System.out.println("Falsche Eingabe");
            System.out.print("Bitte geben Sie die gewünschte Zeilen Grösse ein: ");
            eingabeZeile = new Scanner(System.in);
        }
        int inputSizeZeile = eingabeZeile.nextInt();

        // Ausgabe & Eingabe
        System.out.print("Bitte geben Sie die gewünschte Anzahl Bomben ein: ");
        Scanner eingabeBomben = new Scanner(System.in);
        while (!eingabeBomben.hasNextInt() && eingabeBomben.nextInt() > 0) {
            System.out.println("Falsche Eingabe");
            System.out.print("Bitte geben Sie die gewünschte Anzahl Bomben ein: ");
            eingabeBomben = new Scanner(System.in);
        }
        int inputBomben = eingabeBomben.nextInt();

        // Ausgabe inputSize & inputBomben
        System.out.println();
        System.out.println("Ihre gewünschte Zeilen Grösse lautet " + inputSizeSpalte);
        System.out.println("Ihre gewünschte Spalte Grösse lautet " + inputSizeZeile);
        System.out.println("Ihre gewünschte Anzahl Bomben sind: " + inputBomben);

        // Funktion aufrufen & in der int[] array speichern
        int[][] array = createArray(inputSizeSpalte, inputSizeZeile);
        boolean[][] booleanArray = new boolean[inputSizeSpalte][inputSizeZeile];

        // Funktion aufrufen
        placeBombs(array, inputBomben);
        bombenImNachbarfelder(array);
        printBoard(array, booleanArray);
        felderAufdecken(array, booleanArray, inputBomben);
    }

    public static void felderAufdecken (int[][] array, boolean[][] booleanArray, int inputBomben) {
        while (!spielFertig(booleanArray)) {
            System.out.println();
            System.out.println("Welches Feld möchten Sie Aufdecken? ");

            Scanner inputXAchse;
            int inputX = 0;
            boolean correctInput = true;
            while (correctInput) {
                try {
                    System.out.print("Position X-Achse: ");
                    inputXAchse = new Scanner(System.in);
                    inputX = inputXAchse.nextInt() - 1;
                    if (inputX + 1 > array.length || inputX + 1 < 1) {
                        System.out.println("Bitte geben Sie einen Wert zwischen 1 und " + array.length + " ein.");
                    } else {
                        correctInput = false;
                    }
                } catch (Exception exception) {
                    System.out.println("Bitte geben Sie eine Ganzzahl an.");
                }
            }

            Scanner inputYAchse;
            int inputY = 0;
            correctInput = true;
            while (correctInput) {
                try {
                    System.out.print("Position Y-Achse: ");
                    inputYAchse = new Scanner(System.in);
                    inputY = inputYAchse.nextInt() - 1;
                    if (inputY + 1 > array[0].length || inputY + 1 < 1) {
                        System.out.println("Bitte geben Sie einen Wert zwischen 1 und " + array[0].length + " ein.");
                    } else {
                        correctInput = false;
                        booleanArray[inputX][inputY] = true;
                    }
                } catch (Exception exception) {
                    System.out.println("Bitte geben Sie einen Integer an.");
                }
            }

            if (array[inputX][inputY] == 9){
                printBoard(array, booleanArray);
                System.out.println("Schade, Sie haben das Spiel verloren!");
                return;
            } else if (array[inputX][inputY] == 0) {
                NachbarfelderVomZero(booleanArray, array, inputX, inputY);
            }
            printBoard(array, booleanArray);
            int bombenprüfen = 0;
            for (int x = 0; x < booleanArray.length; x++) {
                for (int y = 0; y < booleanArray[0].length; y++) {
                    if (booleanArray[x][y] == false) {
                        bombenprüfen = bombenprüfen + 1;
                    }
                }
            }
            if (bombenprüfen == inputBomben) {
                System.out.println("Herzlichen Glückwunsch!");
                System.out.println("Sie haben das Spiel gewonnen.");
                return;
            }
        }
    }

    public static void NachbarfelderVomZero (boolean[][] booleanArray, int[][] array, int inputX, int inputY) {
        checkForZero(booleanArray, array, inputX + 1, inputY);
        checkForZero(booleanArray, array, inputX + 1, inputY + 1);
        checkForZero(booleanArray, array, inputX + 1, inputY - 1);
        checkForZero(booleanArray, array, inputX - 1, inputY);
        checkForZero(booleanArray, array, inputX - 1, inputY + 1);
        checkForZero(booleanArray, array, inputX - 1, inputY - 1);
        checkForZero(booleanArray, array, inputX, inputY + 1);
        checkForZero(booleanArray, array, inputX, inputY - 1);
    }

    public static void checkForZero (boolean[][] booleanArray, int[][] array, int x, int y) {
        if (x >= 0 && x < booleanArray.length && y >= 0 && y < booleanArray[0].length && booleanArray[x][y] == false) {
            if (array[x][y] != 9) {
                if (booleanArray[x][y] == false) {
                    booleanArray[x][y] = true;
                }
            }
            if (array[x][y] == 0) {
                NachbarfelderVomZero(booleanArray, array, x, y);
            }
        }
    }

    public static boolean spielFertig (boolean[][] booleanArray) {
        for (int x = 0; x < booleanArray.length; x++) {
            for (int y = 0; y < booleanArray[0].length; y++) {
                if (!booleanArray[x][y]) {
                    return false;
                }
            }
        }
        return true;
    }

    public static int[][] bombenImNachbarfelder(int[][] array) {
        for (int x = 0; x < array.length; x++) {
            for (int y = 0; y < array[0].length; y++) {
                if (array[x][y] == 9) {
                    checkForBomb(array, x + 1, y);
                    checkForBomb(array, x + 1, y + 1);
                    checkForBomb(array, x + 1, y - 1);
                    checkForBomb(array, x - 1, y);
                    checkForBomb(array, x - 1, y + 1);
                    checkForBomb(array, x - 1, y - 1);
                    checkForBomb(array, x, y + 1);
                    checkForBomb(array, x, y - 1);
                }
            }
        }
        return array;
    }

    public static void checkForBomb(int[][] array, int x, int y) {
        if (x >= 0 && x < array.length &&
            y >= 0 && y < array[0].length &&
            array[x][y] != 9) {
            array[x][y]++;
        }
    }

    public static void placeBombs(int[][] array, int anzahlBomben) {
        Random random = new Random();
        int a = 0;
        while (a < anzahlBomben) {
            int spalte = random.nextInt(array.length);
            int zeile = random.nextInt(array[0].length);
            if (array[spalte][zeile] != 9) {
                array[spalte][zeile] = 9;
                a++;
            }
        }
    }

    public static int[][] createArray(int spalte, int zeile) {
        int[][] array = new int[spalte][zeile];
        return array;
    }

    public static void printBoard(int[][] array, boolean[][] booleanArray) {

//      Die Koordinaten mit dem entsprechenden Abstand anzeigen (X-Achse)
        int anzahlZiffern = (int) Math.log10(array.length) + 1;
        int anzahlLuecke = anzahlZiffern * 2 + 1;
        for (int positionKoordinatenXAchse = 0; positionKoordinatenXAchse <= anzahlLuecke; positionKoordinatenXAchse++) {
            System.out.print(" ");
        }
        for (int i = 0; i < array.length; i++) {
            int arrayAufsteigendPlusEins = (int) Math.log10(i + 1);
            System.out.print(i + 1);
            for (int b = 0; b < anzahlZiffern - arrayAufsteigendPlusEins; b++) {
                System.out.print(" ");
            }
        }
        System.out.println();

        // Grafic erste Zeile
        for (int erstePositionGraficZeichen = 0; erstePositionGraficZeichen <= anzahlZiffern; erstePositionGraficZeichen++) {
            System.out.print(" ");
        }
        System.out.print("┏━");
        int laengeDerGerade = (anzahlZiffern * array.length) + array.length;
        for (int i = 0; i < laengeDerGerade; i++) {
            System.out.print("━");
        }
        System.out.println("┓");

        // Koordinaten Y-Achse, mit Grafic und Array-Ausgabe
        for (int y = 0; y < array[0].length; y++) {
            System.out.print(y + 1);
            int arrayAufsteigendPlusEins = (int) Math.log10(y + 1);
            for (int b = 0; b < anzahlZiffern - arrayAufsteigendPlusEins; b++) {
                System.out.print(" ");
            }
            System.out.print("┃");
            for (int x = 0; x < array.length; x++) {
                for (int c = 0; c < anzahlZiffern; c++) {
                    System.out.print(" ");
                }
                if (booleanArray[x][y]) {
                    if (array[x][y] == 9) {
                        System.out.print("*");
                    } else if (array[x][y] == 0) {
                        System.out.print(" ");
                    } else {
                        System.out.print(array[x][y]);
                    }
                } else {
                    System.out.print("▒");
                }
            }
            System.out.println(" ┃");
        }
        for (int letzteZeilGrafic = 0; letzteZeilGrafic <= anzahlZiffern; letzteZeilGrafic++) {
            System.out.print(" ");
        }
        System.out.print("┗━");

        for (int i = 0; i < laengeDerGerade; i++) {
            System.out.print("━");
        }
        System.out.println("┛");
    }
}
```
