# CasoVotantes
Votantes y encuesta de satisfacción en la gestión del gobierno.
package asd;

import java.util.Random;
import javax.swing.JOptionPane;

public class Asd {

    public static void main(String[] args) {
        Random r = new Random();
        int AprobacionHombres = 0, DesaprobacionMujeres = 0, Aprobacion = 0;
        int Votos = r.nextInt(200) + 50;
        System.out.println(Votos);
        char[][] Votantes = new char[2][Votos];
        for (int i = 0; i < 2; i++) {
            for (int j = 0; j < Votos; j++) {
                Votantes[i][j] = (char) (r.nextInt(3) + 'a');
                if (String.valueOf(Votantes[0][j]).equals("a")) {
                    AprobacionHombres++;
                }
                if (String.valueOf(Votantes[1][j]).equals("b")) {
                    DesaprobacionMujeres++;
                }
                if (String.valueOf(Votantes[i][j]).equals("a")) {
                    Aprobacion++;
                }
            }
        }
        double AprobacionTotal = (Aprobacion * 100 / Votos);
        JOptionPane.showMessageDialog(null, "Rl numero de hombres que aprueban la gestion es: " + AprobacionHombres
                + "\n" + "El numero de mujeres que desaprueban la gestion es :" + DesaprobacionMujeres
                + "\n" + "El Porcentaje de aprobacion a la gestion es :" + (Aprobacion * 100 / (Votos * 2)) + "%"
                + "\n" + "El total de votantes es: " + Votos);
    }

}
