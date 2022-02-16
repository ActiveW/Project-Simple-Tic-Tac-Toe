# Project-Simple-Tic-Tac-Toe
Java basics

package tictactoe;
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        // write your code here
        Scanner scanner = new Scanner(System.in);
        // System.out.print("Enter cells: ");
        String strUser = "         ";
        String[][] ticTacGrid;
        ticTacGrid = new String[3][3];
        boolean winX = false;
        boolean winO = false;

        int sum_ = 0;
        int k = 0;
        boolean gamerX = true;


        for (int i = 0; i < ticTacGrid.length; i++) {
            for (int j = 0; j < ticTacGrid[i].length; j++) {
                ticTacGrid[i][j] = strUser.substring(k, k + 1);
                k++;

            }

        }


        BildGrid(ticTacGrid); //Create strings from elements of array ticTacGrid


        while (true) {

            System.out.print("Enter the coordinates: ");
            if (scanner.hasNextInt()) {
                int coord_i = scanner.nextInt();

                if (scanner.hasNextInt()) {
                    int coord_j = scanner.nextInt();
                    if (coord_i > 3 || coord_i < 1 || coord_j > 3 || coord_j < 1) {
                        System.out.println("Coordinates should be from 1 to 3!");

                    } else if (" ".equals(ticTacGrid[coord_i - 1][coord_j - 1]) == false) {
                        System.out.println("This cell is occupied! Choose another one!");
                    } else {
                        if (gamerX == true) {
                            ticTacGrid[coord_i - 1][coord_j - 1] = "X";
                            sum_ = sum_ + 1;
                            gamerX = false;

                        } else {
                            ticTacGrid[coord_i - 1][coord_j - 1] = "O";
                            sum_ = sum_ + 1;
                            gamerX = true;

                        }

                        BildGrid(ticTacGrid); //Create strings from elements of array ticTacGrid

                        String line01 = ticTacGrid[0][0] + ticTacGrid[0][1] + ticTacGrid[0][2];
                        if ("XXX".equals(line01)){
                            winX = true;
                        } else if ("OOO".equals(line01)){
                            winO = true;
                        }
                        String line02 = ticTacGrid[1][0] + ticTacGrid[1][1] + ticTacGrid[1][2];
                        if ("XXX".equals(line02)){
                            winX = true;
                        } else if ("OOO".equals(line02)){
                            winO = true;
                        }
                        String line03 = ticTacGrid[2][0] + ticTacGrid[2][1] + ticTacGrid[2][2];
                        if ("XXX".equals(line03)){
                            winX = true;
                        } else if ("OOO".equals(line03)){
                            winO = true;
                        }
                        String line04 = ticTacGrid[0][0] + ticTacGrid[1][0] + ticTacGrid[2][0];
                        if ("XXX".equals(line04)){
                            winX = true;
                        } else if ("OOO".equals(line04)){
                            winO = true;
                        }
                        String line05 = ticTacGrid[0][1] + ticTacGrid[1][1] + ticTacGrid[2][1];
                        if ("XXX".equals(line05)){
                            winX = true;
                        } else if ("OOO".equals(line05)){
                            winO = true;
                        }
                        String line06 = ticTacGrid[0][2] + ticTacGrid[1][2] + ticTacGrid[2][2];
                        if ("XXX".equals(line06)){
                            winX = true;
                        } else if ("OOO".equals(line06)){
                            winO = true;
                        }
                        String line07 = ticTacGrid[0][0] + ticTacGrid[1][1] + ticTacGrid[2][2];
                        if ("XXX".equals(line07)){
                            winX = true;
                        } else if ("OOO".equals(line07)){
                            winO = true;
                        }
                        String line08 = ticTacGrid[2][0] + ticTacGrid[1][1] + ticTacGrid[0][2];
                        if ("XXX".equals(line08)){
                            winX = true;
                        } else if ("OOO".equals(line08)){
                            winO = true;
                        }


                        if (winO == true){
                            System.out.println("O wins");
                            break;
                        } else if (winX == true){
                            System.out.println("X wins");
                            break;
                        } else if (winO == false && winX == false && sum_ == 9){
                            System.out.println("Draw");
                            break;
                        }
                    }

                } else {
                    scanner.next();
                    scanner.next();
                    System.out.println("You should enter numbers!");
                }
            } else {
                scanner.next();
                scanner.next();
                System.out.println("You should enter numbers!");
            }



        }
    }
    private static void BildGrid (String[][] ticTacGrid) {
        System.out.println("---------");
        for (int i = 0; i < ticTacGrid.length; i++) {
            System.out.print("| ");
            for (int j = 0; j < ticTacGrid[i].length; j++) {
                System.out.print(ticTacGrid[i][j]);
                System.out.print(" ");
            }
            System.out.println("|");
        }
        System.out.println("---------");
    }
}

