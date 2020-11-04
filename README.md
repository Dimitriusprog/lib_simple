# lib_simple

//#pragma once
#include <iostream>
#include <Windows.h>
#include <string>
#include <fstream>
using namespace std;

int key(unsigned char s, int x){
keybd_event(s, 0,0,0);
Sleep(x);
return 0;
}
 


void mouse(int x){
mouse_event(MOUSEEVENTF_LEFTDOWN,0,0,0,0);
Sleep(x);
mouse_event(MOUSEEVENTF_LEFTUP,0,0,0,0);
}



 
void mousest(int x, int y,n){
SetCursorPos(x, y);
for(int i;i<n;i++){
mouse_event(MOUSEEVENTF_LEFTDOWN,0,0,0,0);
mouse_event(MOUSEEVENTF_LEFTUP,0,0,0,0);
}
}




void rus(){
setlocale (LC_ALL,"rus");
}

void SetColor(int text,int bg){
HANDLE hStdOut = GetStdHandle(STD_OUTPUT_HANDLE);
SetConsoleTextAttribute(hStdOut, (WORD)((bg<<4)| text));
}


void setE(){
for(int i;i<1;i++){
if(LOWORD(GetKeyboardLayout(0))==1049){
PostMessage(GetForegroundWindow(), WM_INPUTLANGCHANGEREQUEST, 2, 0);
}
}}




void setR(){
setlocale (LC_ALL,"rus");
for(int i;i<1;i++){
if(LOWORD(GetKeyboardLayout(0))==1033){
PostMessage(GetForegroundWindow(), WM_INPUTLANGCHANGEREQUEST, 2, 0);
}
}}


using namespace std;
void text(string path,string text){
ofstream fout;
fout.open(path);
while (!fout.is_open()){
cout<<"ERROR"<<endl;
}
fout<<text;
fout.close();
}

#include <Windows.h>
using namespace std;
int load(int t,int g){
cout<<"LOADING [";
for(int i;i<t;i++){
Sleep(g);
cout<<"&";
}
cout<<"]"<<"  FINISH"<<'\n';    
return 0; 
}
