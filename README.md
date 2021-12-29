# java-project
java project
import java.awt.*;
import java.awt.event.*;
import javax.swing.*;
import java.util.*;

public class DDA1 extends JFrame
{
	Graphics g; 
	DDA1()
	{
		setTitle("DDA");
		setSize(500,500);
		setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		setVisible(true);
		g=getGraphics();
		
	}
	
	public void procedureLine(float xa,float ya,float xb,float yb, String col)
	{
		String colo=col;
		float dx = xb-xa;
		float dy = yb-ya;
		float step;
		
		if(Math.abs(dx) > Math.abs(dy))
			
			step =Math.abs(dx);
		
		else
			step =Math.abs(dy);
		
	
		
		if(colo=="RED"){
			g.setColor(Color.RED);
		}
		else if(colo=="GREEN"){
			g.setColor(Color.GREEN);
		}
		else if(colo=="BLUE"){
			g.setColor(Color.BLUE);
		}
		else if(colo=="ORANGE"){
			g.setColor(Color.ORANGE);
		}
		else{
			g.setColor(Color.WHITE);
		}
		
	
		float x = xa;
		float y = ya;
		float xinc =(dx/step);
		float yinc =(dy/step);
		
		for(int i=1;i<=step;i++)
		{
			x=x+xinc;
			y=y+yinc;
			
			g.drawLine(Math.round(x),Math.round(y),Math.round(x),Math.round(y));
		}
		
	}
	
	public static void main(String arg[])
	{
		DDA1 d=new DDA1();
		
		d.procedureLine(100,100,200,200,"RED");
		d.procedureLine(200,200,100,100,"RED");
		d.procedureLine(100,200,400,200,"ORANGE");
		d.procedureLine(100,200,100,400,"GREEN");
		d.procedureLine(100,400,400,400,"GREEN");
		d.procedureLine(400,200,400,400,"GREEN");
		d.procedureLine(200,400,300,400,"BLUE");
		d.procedureLine(200,300,200,400,"BLUE");
		d.procedureLine(300,300,300,400,"BLUE");
		d.procedureLine(200,300,300,300,"BLUE");
		d.procedureLine(250,100,400,200,"RED");
		d.procedureLine(100,200,250,100,"RED");
		d.procedureLine(100,200,400,200,"ORANGE");
		
	}
}
