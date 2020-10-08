# Trazo-de-lineas
Programa en java - Trazo de figuras a partir de lineas y herramientas directas de dibujo

package TrazoFiguras;

import java.awt.BorderLayout;
import java.awt.Color;
import java.awt.Container;
import java.awt.Graphics;
import javax.swing.JFrame;
import javax.swing.JPanel;

public class Figuras extends JPanel {

    // ventana
    private JFrame ventana;
    // contenedor
    private Container contenedor;

    public Figuras() {
// inicializar la ventana
        ventana = new JFrame("Dibujando icono");
        // definir tamaño a ventana
        ventana.setSize(800, 600);
        ventana.setVisible(true);
        ventana.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        ventana.setResizable(false);
        ventana.setLocationRelativeTo(null);

        contenedor = ventana.getContentPane();
        contenedor.setSize(800, 600);
        // agregar la ventana en el contenedor
        contenedor.add(this, BorderLayout.CENTER);
    }

    @Override
    protected void paintComponent(Graphics g) {
        super.paintComponent(g); 
        
        //trazo de lineas
        g.setColor(Color.RED);
        g.drawLine(100, 50, 200, 50);
        g.drawLine(200, 50, 200, 100);
        g.drawLine(100, 50, 100, 100);
        g.drawLine(100, 100, 200, 100);
        
        g.setColor(Color.DARK_GRAY);
        g.drawLine(100, 50, 150, 20);
        g.drawLine(200, 50, 150, 20);
        
        //Trazo de rectangulos
        g.setColor(Color.BLUE);
        g.drawRect(280, 50, 100, 50);
        g.fillRect(280, 110, 100, 50);
        
        //Trazo de rectanguloa redondeados (ovalos)
        g.setColor(Color.BLACK);
        g.drawRoundRect(450, 50, 100, 50, 50, 50);
        g.fillRoundRect(450, 110, 100, 50, 20, 20);
        
        //Trazo de circulos
        g.setColor(Color.ORANGE);
        g.drawOval(100, 200, 80, 80);
        g.fillOval(100, 290, 50, 50);
        
        //Trazo de ovalos (circunferencias)
        g.setColor(Color.GREEN);
        g.drawOval(280, 200, 80, 40);
        g.fillOval(280, 290, 40, 80);
        
        //Trazo de triangulos
        g.setColor(Color.PINK);
        g.drawLine(450, 300, 550, 300);
        g.drawLine(450, 300, 500, 250);
        g.drawLine(550, 300, 500, 250);
        
        //Dibujo de cadenas de texto
        g.setColor(Color.BLACK);
        g.drawString("Ejemplo de trazo de figuras basicas", 200, 400);
        
        //Trazo de arcos        
        //Figura 1: Solo contorno        
        g.setColor(Color.BLACK);
        g.drawArc(100, 400, 100, 100, 100, 70);
        
        //Figura 1: Relleno
        g.fillArc(80, 450, 100, 100, 100, 90);
    }   
}

package TrazoFiguras;

public class Principal {

    public static void main(String[] args) {
        new Figuras();
    }    
}
