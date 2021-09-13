#include <iostream>
#include <iomanip>
using namespace std;
main() { 
     
    char empid[ 100 ][ 12 ];     
    char fname[ 100 ][ 14 ],  lastname [ 100 ][ 15 ];
    int hw [ 100 ];
  double gp[ 100 ], np[ 100 ], hr[ 100 ], taxrate[ 100 ], taxamt[ 100 ];
  int counter = 0;
  int i;
  cout<<"ENTER EMP ID, FNAME, LNAME, HRS WORKED, HRLY RATE ctrl z to end"<<endl;
  while(cin>>empid[counter]>>fname[counter]>>lastname[counter]>>hw[counter]>> hr[counter])
  counter=counter+1;
  for (i=0; i<counter; i++){
  gp[i] = hw[i] * hr[i];
}
    //end grosspay for loop
 for (i=0; i<counter; i++){
 if (gp[i]>500) taxrate[i] = .30;
 else if (gp[i]>200) taxrate[i]=.20;
 else taxrate[i] = .10;
 }// FOR
 for (i=0; i<counter; i++){
 taxamt[i] = gp[i] * taxrate[i];}//end taxamount for loop
 for (i=0; i<counter; i++){  
 np[i] = gp[i] - taxamt[i];}//end netpay for loop
 cout<<endl;
 cout<<setw(14)<<"EMPLOYEE ID"<<setw(16)<<"FIRST  NAME"<<setw(17)
 <<"LAST NAME" <<setw(4)<<"HW"<<setw(5)<<"HR"<<setw(6)
 <<"GROSS"<<setw(6)<<"TAX"<<setw(9)<<"NET PAY"<<endl<<endl;
 for (i=0; i<counter; i++){
 cout<<setw(14)<<empid[i]<<setw(16)<<fname[i]<<setw(17)<<lastname[i]<<setw(4)
  <<hw[i]<<setw(5)<<hr[i]<<setw(6)<<gp[i]<<setw(6)<<taxamt[i]<<setw(9)<<np[i]<<endl;
  }// FOR
 return 0;

 }//MAIN
