int main()
{
    int count = 3;
    int countassis = 6;
    int max = -1;
    int min;
    string check = "false";
    vector<Accountassis> dat(countassis);
    dataBas(dat);
    vector<Account> data(count);
    dataBase(data);
    string password;
    string login;
    string name;
    string surname;
    int patmenuchoise;
    int who;
    int maindocchoise;
    int docchoise;
    char newTask[100];
    int medassisChoise;
    string newDiagnose;
    char doneTask[100];
    
    cout << "***please choose your account type ***\n";

    cout << "press 1 for maindoctor \n";
    cout << "press 2 for doctor\n";
    cout << "press 3 for medassistance\n";
    cout << "press 4 for patient\n";
    cout << "press 0 for exit\n";
  
    cin >> who;
    switch (who)
    {
    case 1:
        maindoctormenu(dat, login, password, maindocchoise, countassis, count, max, min);
        break;
    case 2:
        doctormenu(dat, data, login, password, docchoise, countassis, count, check, newTask, name, surname, newDiagnose);
        break;
    case 3:
        medassismenu(dat, data, login, password, docchoise, countassis, count, check, newTask, name, surname, medassisChoise, doneTask);
        break;
    case 4:
        patientmenu(data, login, password, patmenuchoise, count, check);
        break;
    case 0:
        exit(0);
    default:
        cout << "Sorry, but we did not find this type of account";
        break;
    }
    return 0;
}