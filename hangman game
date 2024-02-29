#include <iostream>
#include <stdlib.h>
#include <ctime>
using namespace std;

int tries=3;
string message="\t\t\tYou have 3 chances";

void hang_man(char state){
    string head_string="|";
    string lever="/";
    string base="=============";
    if(state=='f'){
        head_string=" ";
    }

    else if(state=='h'){
        base="==         ==";
        lever="\\";
    }
    cout<<"\t\t\t\t______________________"<<endl;
    cout<<"\t\t\t\t        "<<head_string<<"            |\t"<<endl;
    cout<<"\t\t\t\t        "<<head_string<<"            |\t"<<endl;
    cout<<"\t\t\t\t        O            |\t"<<endl;
    cout<<"\t\t\t\t       / \\           |\t"<<"  "<<message<<endl;
    cout<<"\t\t\t\t        |            |\t"<<"\t         /"<<endl;
    cout<<"\t\t\t\t       / \\           |\t         O"<<endl;
    cout<<"\t\t\t\t  "<<base<<"      |\t        / \\"<<endl;
    cout<<"\t\t\t\t  |           |\t     |    "<<lever<<"      |  "<<endl;
    cout<<"\t\t\t\t  |           |\t     |  ====    / \\"<<endl;
    cout<<"\t\t\t\t========================|==|========"<<endl;
}

int CheckGuess(char guess, string real_month, string &hidden_month){
    int matches=0;
    int len=real_month.length();
    for(int i=0; i<len; i++){
        if(guess==hidden_month[i]){
            return 0;
        }
        if(guess==real_month[i]){
            hidden_month[i]=guess;
            matches++;
        }
    }
    return matches;
}

int main() {
    char letter;
    string month;
    string months[]={"January", "February", "March", "April","May", "June", "July", "August","September", "October",
                  "November", "December"};
    srand(time(NULL));
    int month_no=rand()%12;
    month=months[month_no];
    string hide_month(month.length(), 'X');

    system("clear");

    while(tries!=0){
        hang_man('n');
        cout<<"\t\t\t\tLife: "<<tries<<endl;
        cout<<"\t\t\t\tYour word is: "<<endl;
        cout<<"\t\t\t\t"<<hide_month<<endl;
        cout<<"\t\t\t\tGuess a letter: ";
        cin>>letter;
        cout<<"\n";
        system("clear");

        if(CheckGuess(letter, month, hide_month)==0){
            message="\t\t\tIncorrect Letter!";
            tries--;
        }
        else{
            message="\t\t\tNice, Correct Guess!";
        }
        if(hide_month==month){
            message="\t\t\tYou are free!!";
            hang_man('f');
            cout<<"\t\t\t\tLife: "<<tries<<endl;
            cout<<"\t\t\t\tthe month is: "<<month<<endl;
            break;
        }
    }
    if(tries==0){
        message="\t\t\tYou are hanged!";
        hang_man('h');
        cout<<"\t\t\t\tLife: "<<tries<<endl;
        cout<<"\t\t\t\tthe month is: "<<month<<endl;
    }
    return 0;
}


