# tank_war.github.io

package com.mashibing.tank;

import java.awt.Frame;
import java.awt.Graphics;
import java.awt.event.KeyAdapter;
import java.awt.event.KeyEvent;
import java.awt.event.WindowAdapter;
import java.awt.event.WindowEvent;

public class TankFrame extends Frame{
	
	Tank myTank = new Tank(200,200,Dir.DOWN);
	
	/* int x=200,y=200;
	Dir dir=Dir.DOWN;
	private static final int SPEED =10;
	*/
	
	
	public TankFrame() {
		setSize(800,600);
		setResizable(false);
		setVisible(true);
		setTitle("tank war");
		this.addKeyListener(new MyKeyListener());
		
		addWindowListener(new WindowAdapter(){
			@Override
			public  void windowClosing(WindowEvent e){
				
				System.exit(0);					
	}
});
}
	public void paint(Graphics g) {
		
		myTank.paint(g);
	}
	
	
		
		//x += 10;
		//y += 10;
		
	class MyKeyListener extends KeyAdapter{
		
		boolean bL=false;
		boolean bU=false;
		boolean bR=false;
		boolean bD=false;
		
			@Override
			public void keyPressed(KeyEvent e) {
				
				int key=e.getKeyCode();
				switch(key) {
				case KeyEvent.VK_LEFT:
					//x -=10;
					bL=true;
				    break;
				case KeyEvent.VK_UP:
					//y -=10;
					bU=true;
				    break;
				case KeyEvent.VK_RIGHT:
					//x +=10;
					bR=true;
				    break;
				case KeyEvent.VK_DOWN:
					//y +=10;
					bD=true;
				    break;
				
				default:
				    break;  
				
				
				
				//x +=10;
				//y +=10;
							
				//System.out.println("key pressd");
				//x +=200;
				//repaint();
				}
				setMainTankDir();
				
			}
	
			@Override
			public void keyReleased(KeyEvent e) {
				
				int key=e.getKeyCode();
				switch(key) {
				case KeyEvent.VK_LEFT:
					//x -=10;
					bL=true;
				    break;
				case KeyEvent.VK_UP:
					//y -=10;
					bU=true;
				    break;
				case KeyEvent.VK_RIGHT:
					//x +=10;
					bR=true;
				    break;
				case KeyEvent.VK_DOWN:
					//y +=10;
					bD=true;
				    break;
				
				default:
				    break; 
				}
				
				//System.out.println("key released");
				
				setMainTankDir();
				
			}

			private void setMainTankDir() {
				if(bL) myTank.setDir(Dir.LEFT);
				if(bU) myTank.setDir(Dir.UP);
				if(bR) myTank.setDir(Dir.RIGHT);
				if(bD) myTank.setDir(Dir.DOWN);
			}
						
		}
}
