# JPO1

import java.util.Locale;
import java.util.Scanner;

class punktmaterialny {						//Tworzy klase 
	
	int masa;						
	int r=0;
	int promien;
											//Zmienne klasy
	
	
	
	public punktmaterialny(int m,int R)		//konstryktor
	{
		masa=m;
		promien=R;
		
	}
	
	
	public int moment()					// funkcja licząca moment punktu
	{
		 int I = r*masa*masa;
		 return I;
	}
	
	public int steiner()				//funkcja liczaca moment wzgledem nowej osi
	{
	int Is = promien*masa*masa+moment();
	return Is;
	}
	
	public void opis()				//funkcja opisujaca punkt
	{
			
		
	System.out.println("masa punktu="+ masa );
		
	System.out.println("moment bezwladnosci="+ moment());
		
	System.out.println("moment bezwladnosci wzgledem noewj osi="+ steiner());
	}
	
	
	public static void main(String[] args) {
		
		int x;
		int y;
		
		
		System.out.println("Opis punktu materialnego z domyślnymi wartosciami:\n");
		
		punktmaterialny p1= new punktmaterialny(1,1);		//towrzy nowy obiekt o wartosciach domyslnych
		
		int masa=p1.moment();
		
		p1.opis();										//wywolanie funkcji opisujacej
		
		
		
		System.out.println("\nPodaj wartosc masy drugiego punktu:");
		 
		Scanner masa1 = new Scanner(System.in);			//odczytanie zmiennej z klawiatury
	    
		x = masa1.nextInt();
	     
	    System.out.println("Podaj odleglosc pomiedzy osia glowna a nowa osia obrotu:\n");
	     
	    Scanner odleglosc1 = new Scanner(System.in);
	    
	    y = odleglosc1.nextInt();
	     
	    punktmaterialny p2= new punktmaterialny(x,y);
			
	    System.out.println("Opis punktu materialnego z wybranymi parametrami:\n");
		
	    p2.opis();
		 
		
	    
	    punktmaterialny[] p= new punktmaterialny[10];		//stworzenie tablicy 10 elementowej
		 
		for(int i=1;i<=9;i++)
		{
		System.out.println("\nOpis punktu z Tablicy nr."+i);
		p[i] = new punktmaterialny(i,i);
		p[i].opis();
			 
		}
	}
	}
		 
	
