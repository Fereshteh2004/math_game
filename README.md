
#include <iostream>
#include <cstdlib> 
#include <ctime> 
#include <cmath>
using namespace std;

void menu(){
    cout<<"\t--------------------------welcom back-----------------------------------\n";
    
    cout<<"\t|\t1.START      2.ABOUT US       3.HELP       4.SETING            |\n";
    
    cout<<"\t------------------------------------------------------------------------\n";   
    cout<<"\t                          power of = 0\n";
    
    
}
void ABOUTUS(){
	
	cout<<"\t------------------------------------------------------------------------\n";
	cout<<"\t                          about us\n";
	cout<<"First Name : Fereshteh\n" 
	    <<"Last Name : Tabeei\n"
	    <<"Email : fe.tabeei@gmail.com\n"
	    <<"statistics student\n";
	
}
void HELP(){
	cout<<"\t------------------------------------------------------------------------\n";
	cout<<"\t                          HELP\n";
	cout<<"Three Level:"
	    <<"level 1: addition of one-digit numbers.\n"
	    <<"level 2: addition of two-digit numbers.\n"
	    <<"level 3: addition of three-digit numbers.\n";
}
void SETING(){
	
    cout<<"\t------------------------------------------------------------------------\n";
    cout<<"\t                          SETING\n";
    
    cout<<"\t   color   |   code   \n";
    cout<<"\t----------------------\n";
    cout<<"\t   black   |   0      \n";
    cout<<"\t   blue    |   1      \n";
    cout<<"\t   green   |   2      \n";
    cout<<"\t   cyan    |   3      \n";
    cout<<"\t   red     |   4      \n";
    cout<<"\t   purple  |   5      \n";
    
	int x,y;
	cout<<"enter your background color:\n";
	cin>>x;
	
	cout<<"enter your text color:\n";
	cin>>y;
	
	if(x==0){
		switch(y){
			case 0 : system("color 00");break;
			case 1 : system("color 01");break;
			case 2 : system("color 02");break;
			case 3 : system("color 03");break;
			case 4 : system("color 04");break;
			case 5 : system("color 05");break;
		}
	}else if(x==1){
		switch(y) {
		
			case 0 : system("color 10");break;
			case 1 : system("color 11");break;
			case 2 : system("color 12");break;
			case 3 : system("color 13");break;
			case 4 : system("color 14");break;
			case 5 : system("color 15");break;
	    }
	}else if(x==2){
		switch(y){
			case 0 : system("color 20");break;
			case 1 : system("color 21");break;
			case 2 : system("color 22");break;
			case 3 : system("color 23");break;
			case 4 : system("color 24");break;
			case 5 : system("color 25");break;
		}
	}else if (x==3){
		switch(y){
			case 0 : system("color 30");break;
			case 1 : system("color 31");break;
			case 2 : system("color 32");break;
			case 3 : system("color 33");break;
			case 4 : system("color 34");break;
			case 5 : system("color 35");break;
		}
	}else if (x==4){
		switch(y){
			case 0 : system("color 40");break;
			case 1 : system("color 41");break;
			case 2 : system("color 42");break;
			case 3 : system("color 43");break;
			case 4 : system("color 44");break;
			case 5 : system("color 45");break;
		}
	}else if(x==5){
		switch(y){
			case 0 : system("color 50");break;
			case 1 : system("color 51");break;
			case 2 : system("color 52");break;
			case 3 : system("color 53");break;
			case 4 : system("color 54");break;
			case 5 : system("color 55");break;
		}
		
	}else
	    cout<<"invalid data.";


}


bool question(int level){
   int answer;
    
   srand((unsigned)time(0)); 
    int i,j;
    int power = pow(10,level-1);
    i = (rand()%(10*power-power))+power;
    j = (rand()%(10*power-power))+power;
    cout << i << "+" << j << "\n";  
    cin >> answer;
    if(answer == (i+j)) return 1;
    return 0;
}
void game(int level){
     cout << "you are on level " << level << endl;
     int point = 0 ;
     for(int i=0;i<10;i++){
        cout << "question " << i+1 << " :" << endl;
        point += question(level);
     }
     cout << "point: " << point << endl;
     if(point >= 8){
        cout << "you did it!" << endl;
        if(level<3)
        game(level+1);
        else{
        	cout << "you have finished all of the levels! " << endl;
            cout << "if you wanna try again press 1 and if you wanna go to menu press 2";
            int x;
            cin >> x;
            if(x==1) game(level);
		}
        
     }
     else{
      cout << "you lose game" << endl;
      cout << "if you wanna try again press 1 and if you wanna go to menu press 2: ";
      int x;
      cin >> x;
      if(x==1) game(level);
      
     }
}


main(){
	int n;
	

	if(n==0)
	exit(0);
	while(n!=0){
		menu();
    	cout<<"what is your choise";
        cin>>n;
		if(n==1){
			game(1);
			 
			
		}else if(n==2){
			ABOUTUS();
			
		}else if(n==3){
			HELP();
			
		}else if(n==4){
			SETING();
			
		}
    }
    

		
	}
    




