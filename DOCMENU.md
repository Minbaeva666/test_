void patnumForDoc(int count){
    cout <<  "The number of patient is: " << count << endl;
}

void menud(){
    cout << "Hello, dear Doctor!\n Please choose the menu number to work with the program, if finished, then dial 8:\n";
    cout << "1.Patients list;\n2.Number of patients;\n3.Medassistance task list\n4.Create medassistance task list;\n5.Fishished task list;\n6.Patient search;\n7.Diagnose a patient;\n8.Exit;\n";
}

void tasklist(){
    cout << "-Preparing patients for examination.\n-Collecting and preparing laboratory specimens.\n-Make laboratory test";
}
void createtask(char newTask[100]){
    cout << "Enter new task:";
    cin.ignore();
    cin.getline(newTask,100);
    cout << "Your task was created! Updated tasklist: ";
    tasklist();
    cout << endl << newTask;
}
void donetasklist(){
    cout << "1.Check up of all parients.\n2.Help me with documents.";
}

void searchpat(vector<Account> &data, string name, string surname, int count){
    cout << "Please enter patient name:"; cin >> name;
    cout << endl << "Surname:"; cin >> surname;
    for (int i = 0; i < count; i++) {
        if(name == data[i].name && surname == data[i].surname){
        cout << endl << "Name: " << data[i].name << endl << "Surname: " << data[i].surname << endl << "Height: " << data[i].height << endl << "Weight:"<< data[i].weight << endl << "Birth:" <<  data[i].birth << endl << "Bloodtype: " << data[i].bloodtype << endl << "Illness: "<< data[i].ill << endl << " History of desiase:" << data[i].period << endl << "Amount days of treatment: " << data[i].days;
        }
    }
}

void checkForDoc(vector <Accountassis>& dat, string login, string password, int countassis, string check){
    cout << "Enter your login: "; cin >> login;
    cout << "Enter your password: "; cin >> password;
    for (int i = 0; i < countassis; i++){
        if (dat[i].type == "doctor" && login == dat[i].login && password == dat[i].password ){
            check = "true";
        }
    }if(check == "true"){
        menud();
    }else{
        cout << "Incorrect login or password!";
        exit(0);
    }
}

void patlist(vector <Account>& data, int count){
    cout << endl << "Patient List:" << endl << endl;
    for (int i = 0; i < count; i++){
        cout << endl << data[i].name << " " << data[i].surname << endl;
    }
}
void diagnose(vector<Account> &data, string name, string surname, int count, string newDiagnose){
    cout << "Please enter patient name: "; cin >> name;
    cout << endl << "Surname: "; cin >> surname;
    cout << "Diagnose: "; cin >> newDiagnose;
    for (int i = 0; i < count; i++) {
        if(name == data[i].name && surname == data[i].surname){
        cout << endl << "Updated patient info: " << endl << "Name: " << data[i].name << endl << "Surname: " << data[i].surname << endl << "Illness: "<< newDiagnose << endl;
        }
    }
}
void doctormenu(vector <Accountassis>& dat, vector <Account>& data, string login, string password, int docchoise, int countassis,int count, string check, char newTask[100], string name, string surname, string newDiagnose){
    checkForDoc(dat, login, password, countassis, check);
    while (docchoise != 9){
        cout << endl << "Choose an option: ";
        cin >> docchoise;
        switch (docchoise){
        case 1:
            patlist(data, count);
            break;
        case 2:
            patnumForDoc(count);
            break;
        case 3:
            tasklist();
            break;
        case 4:
            createtask(newTask);
            break;
        case 5:
            donetasklist();
            break;
        case 6:
            searchpat(data, name, surname, count);
            break;
        case 7:
            diagnose(data, name, surname, count, newDiagnose);
            break;
        case 8:
            cout << endl << endl << "The program is finished, glad to see you again!";
            exit(0);
        default:
            cout << "Sorry, but we did not find this type of command.";
            break;
        }
    }
}
