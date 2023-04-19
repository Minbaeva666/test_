void lastdate(vector<Account> &data,string login, string password, int count) {
    for (int i = 0; i < count; i++) {
        if(login == data[i].login && password == data[i].password){
        cout << data[i].lastd;
        }
    }
}
void treatmentday(vector<Account> &data,string login, string password, int count) {
    for (int i = 0; i < count; i++) {
        if(login == data[i].login && password == data[i].password){
        cout << data[i].days;
        }
    }
}

void drschedule(){
    cout << "Dr.Minbaeva Mon-Wed 11:00 - 13:00";
    cout << endl << "Dr.Omusheva Fri     9:00 - 18:00";
    cout << endl << "Dr.Gogo     Wed,Fri 8:00 - 12:00";
    cout << endl << "Dr.Henry    Fri-Sun 13:00 - 19:00";
}

void infome(vector<Account> &data,string login, string password, int count) {
    for (int i = 0; i < count; i++) {
        if(login == data[i].login && password == data[i].password){
        cout << data[i].surname << " " << data[i].name << endl;
        cout << "Height,weight:" << " " << data[i].height <<","<< " " << data[i].weight << endl;;
        cout << "Birth date:" << " " << data[i].birth << endl;
        cout << "Blood type:" << " " << data[i].bloodtype;
        }
    }
}

void medhistor(vector<Account>& data, string login, string password, int count){;
    for (int i = 0; i < count; i++){
        if (login == data[i].login && password == data[i].password){
            cout << data[i].ill << endl << data[i].period;
         }
    }
}
void patMenu(){
    cout << "Hello, dear Patient!\n Please choose the menu number to work with the program, if finished, then dial 6:\n";
    cout << "1.Medical history;\n2.Last date of illness;\n3.Days of treatment;\n4.Doctor's schedule;\n5.Information for me;\n6.Exit\n";
}
void checkForPat(vector <Account>& data, string &login, string &password, int count, string check, int patmenuchoise){
    cout << "Enter your login: "; cin >> login;
    cout << "Enter your password: "; cin >> password;
    for (int i = 0; i < count; i++){
        if (login == data[i].login && password == data[i].password ){
            check = "true";
        }
    }if(check == "true"){
        patMenu();
    }else{
        cout << "Incorrect login or password!";
        exit(0);
    }
}

void patientmenu(vector<Account>& data, string login, string password, int patmenuchoise, int count, string check) {
    checkForPat(data, login, password, count, check, patmenuchoise);
    while (patmenuchoise != 7){
        cout << endl << "Choose an option: ";
        cin >> patmenuchoise;
    switch (patmenuchoise)
    {
    case 1:
        medhistor(data, login, password, count);
        break;
    case 2:
        lastdate(data, login, password, count);
        break;
    case 3:
        treatmentday(data, login, password, count);
        break;
    case 4:
        drschedule();
        break;
    case 5:
        infome(data, login, password, count);
        break;
    case 6:
        cout << endl << endl << "The program is finished, glad to see you again!";
        exit(6);
    default:
        cout << "Sorry, but we did not find this type command";
        break;
    }
    }
}
