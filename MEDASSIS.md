void menuMedassis(){
    cout << "Hello, dear Medassistance!\n Please choose the menu number to work with the program, if finished, then dial 6:\n";
    cout << "1.List of procedure;\n2.Find patient;\n3.Medassistance task list;\n4.Execute the task;\n5.Finished task list;\n6.Exit\n";
}
void checkForMedassis(vector <Accountassis>& dat, string &login, string &password, int countassis, string check, int medassisChoise){
    cout << "Enter your login: "; cin >> login;
    cout << "Enter your password: "; cin >> password;
    for (int i = 0; i < countassis; i++){
        if (dat[i].type == "medassistance" && login == dat[i].login && password == dat[i].password ){
            check = "true";
        }
    }if (check == "true"){
        menuMedassis();
    }else{
        cout << "Incorrect login or password!";
        exit(0);
    }
}

void procedList(vector <Account>& data, string login, string password, int count){
    for (int i = 0; i < count; i++){
        cout << "Name: " << data[i].name << endl << "Surname: " << data[i].surname << endl << "Prosedure: " << data[i].procedure;
        }
    }

void searchpatt(vector<Account>& data, string name, string surname, int count){
    cout << "Please enter patient name:"; cin >> name;
    cout << endl << "Surname:"; cin >> surname;
    for (int i = 0; i < count; i++) {
        if(name == data[i].name && surname == data[i].surname){
        cout << endl << "Name: " << data[i].name << endl << "Surname: " << data[i].surname << endl << "Height: " << data[i].height << endl << "Weight:"<< data[i].weight << endl << "Birth:" <<  data[i].birth << endl << "Bloodtype: " << data[i].bloodtype << endl << "Illness: "<< data[i].ill << endl << " History of desiase:" << data[i].period << endl << "Amount days of treatment: " << data[i].days;
        }
    }
}
void donetasklistt(){
    cout << "1.Check up of all parients.\n2.Help me with documents.";
}

void executeTask(char doneTask[100]){
    cout << "Enter done task:";
    cin.ignore();
    cin.getline(doneTask,100);
    cout << "Your done tasklist was corrected! Updated donetasklist: ";
    donetasklistt();
    cout << endl << doneTask;
}

void medassismenu(vector <Accountassis>& dat, vector <Account>& data, string login, string password, int docchoise, int countassis,int count, string check, string newTask, string name, string surname, int medassisChoise, char doneTask[100]){
    checkForMedassis(dat, login, password, countassis, check, medassisChoise);
    while (medassisChoise != 7){
        cout << endl << "Choose an option: ";
        cin >> medassisChoise;
    switch (medassisChoise)
    {
    case 1:
        procedList(data, login, password, count);
        break;
    case 2:
        searchpatt(data, name, surname, count);
        break;
    case 3:
        tasklist();
        break;
    case 4:
        executeTask(doneTask);
        break;
    case 5:
        donetasklist();
    case 6:
        exit(0);
    default:
        cout << "Sorry, but we did not find this type of command.";
        break;
    }
    }
    return;
}
