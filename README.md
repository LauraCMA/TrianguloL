# TrianguloL
Software de tres coordenadas 

import javax.swing.*;
public class Evaluacion4FM {

    public static void main(String[] args) {
        int x1, x2, x3, y1, y2, y3;
        double la1, la2, la3;
        double per, area, s;
        String tipoT;
        double ang1, ang2, ang3;
        //PRIMERA COORDENADA
        x1 = Integer.parseInt(JOptionPane.showInputDialog("Escribe la coordenada 'x' del primer punto:"));
        y1 = Integer.parseInt(JOptionPane.showInputDialog("Escribe la coordenada 'y' del primer punto:"));
        //SEGUNDA COORDENADA
        x2 = Integer.parseInt(JOptionPane.showInputDialog("Escribe la coordenada 'x' del segundo punto:"));
        y2 = Integer.parseInt(JOptionPane.showInputDialog("Escribe la coordenada 'y' del segundo punto:"));
        //TERCERA COORDENADA
        x3 = Integer.parseInt(JOptionPane.showInputDialog("Escribe la coordenada 'x' del tercer punto:"));
        y3 = Integer.parseInt(JOptionPane.showInputDialog("Escribe la coordenada 'y' del tercer punto:"));
 //CALCULAR LA DISTANCIA
        la1 = Math.sqrt(Math.pow(x2 - x1, 2) + Math.pow(y2 - y1, 2));
        la2 = Math.sqrt(Math.pow(x3 - x2, 2) + Math.pow(y3 - y2, 2));
        la3 = Math.sqrt(Math.pow(x1 - x3, 2) + Math.pow(y1 - y3, 2));
            //VER EL TIPO DE TRIANGULO QUE ES, DE ACUERDO A SUS LADOS
        if (la1 == la2 && la2 == la3) {
            tipoT = "Equilátero";
        } else if (la1 == la2 || la2 == la3 || la1 == la3) {
            tipoT = "Isósceles";
        } else {
            tipoT = "Escaleno";
        }
       //PERIMETRO
        per = la1 + la2 + la3;
        //SEMIPERIMETRO
        s = per / 2;
        //AREA POR LA FORMULA DE HERON  
        area = Math.sqrt(s * (s - la1) * (s - la2) * (s - la3));
        //CALCULAR ANGULOS CON LA LEY DE COSENOS--HACIENDO A RADIANES--
        ang1 = Math.toDegrees(Math.acos((la2 * la2 + la3 * la3 - la1 * la1) / (2 * la2 * la3)));
        ang2 = Math.toDegrees(Math.acos((la1 * la1 + la3 * la3 - la2 * la2) / (2 * la1 * la3)));
        ang3 = 180 - ang1 - ang2;
        //MOSTRAR LOS DATOS 
        JOptionPane.showMessageDialog(null, "Tipo de triángulo: " + tipoT + "\nPerímetro: "
                 + per + "\nÁrea: " + area + "\nÁngulo 1: " + ang1 + "\nÁngulo 2: " + ang2 + "\nÁngulo 3: " + ang3);
    }
}
