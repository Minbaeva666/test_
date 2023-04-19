void medaslist(vector <Accountassis>& dat, int countassis){
    cout << endl << "Medassistans List:" << endl << endl;
    for (int i = 0; i < countassis; i++){
        if (dat[i].type == "medassistance"){
        cout << endl << dat[i].name << " " << dat[i].surname << endl << dat[i].datework << endl << dat[i].zarik << "$" << endl << endl;
        }
    }
}

void doclist(vector <Accountassis>& dat, int countassis){
    cout << endl << "Doctors List:" << endl << endl;
    for (int i = 0; i < countassis; i++){
        if (dat[i].type == "doctor"){
        cout << endl << dat[i].name << " " << dat[i].surname << endl << dat[i].datework << endl << dat[i].zarik << "$" << endl << endl;
        }
    }
}

void patnum(int count){
    cout << "The number of patient is: " << count << endl;
}

void maxwage(vector <Accountassis>& dat, int countassis, int max){
    for ( int i = 0; i < countassis; i++){
        if(dat[i].zarik >= max){
            max = dat[i].zarik;
        }
    }
    for ( int i = 0; i < countassis; i++){
        if(max == dat[i].zarik){
            cout << endl << "Employee maximum wage: " << endl << dat[i].surname << " " << dat[i].name << endl << dat[i].type << endl << dat[i].zarik << "$" << endl;
        }
    }
    
}

void minwage(vector <Accountassis>& dat, int countassis, int min){
    min = dat[0].zarik;
    for ( int i = 0; i < countassis; i++){
        if(dat[i].zarik <= min){
            min = dat[i].zarik;
        }
    }
    for ( int i = 0; i < countassis; i++){
        if(min == dat[i].zarik){
            cout << endl << "Employee minimum wage: " << endl << dat[i].surname << " " << dat[i].name << endl << dat[i].type << endl << dat[i].zarik << "$" << endl;
        }
    }
}

void mainDocMenu(){
    cout << endl << endl << "Hello, dear Main Doctor!\n Please choose the menu number to work with the program, if finished, then dial 5:\n";
    cout << "1.Medassistants list;\n2.Doctors list;\n3.Number of patients;\n4.Employee maximum wage;\n5.Employee minimum wage;\n6.Exit;\n" << endl;
}

void checkForMaindoc(string login, string password){
    cout << "Enter your login: "; cin >> login;
    cout << "Enter your password: "; cin >> password;
    if (login == "Dr.Ahmed" && password == "1234"){
        mainDocMenu();
    }else{
        cout << "Incorrect login or password!";
        exit(0);
    }
}

void maindoctormenu(vector <Accountassis>& dat, string login, string password, int maindocchoise, int countassis, int count, int max, int min){
    checkForMaindoc(login, password);
    while (maindocchoise != 6){
        cout << endl << "Choose an option: " << endl;
        cin >> maindocchoise;
        switch (maindocchoise)
        {
        case 1:
            medaslist(dat, countassis);
            break;
        case 2:
            doclist(dat, countassis);
            break;
        case 3:
            patnum(count);
            break;
        case 4:
            maxwage(dat, countassis, max);
            break;
        case 5:
            minwage(dat, countassis, min);
            break;
        case 6:
            cout << endl << endl << "The program is finished, glad to see you again!";
            exit(6);
        default:
            cout << endl << "Sorry, but we did not find this type of command.";
            break;
        }
    }
}

