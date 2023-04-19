struct Account {
    string login;
    string password;
    string name;
    string surname;
    int height;
    int weight;
    string birth;
    string bloodtype;
    string ill;
    string period;
    string lastd;
    string days;
    string procedure;
};


void dataBase(vector <Account>& data) {
    
    data[0].login = "Toktomusheva";
    data[0].password = "12345678";
    data[0].name = "Gulkayir";
    data[0].surname = "Toktomusheva";
    data[0].height = 164;
    data[0].weight = 58;
    data[0].birth = "20.12.1970";
    data[0].bloodtype = "+2";
    data[0].ill = "bronchit";
    data[0].period = "22.09.2019 - 22.03.2023";
    data[0].lastd = "20.03.2023";
    data[0].days = "2";
    data[0].procedure = "enema";

    data[1].login = "kiara";
    data[1].password = "1234567";
    data[1].name = "Kiara";
    data[1].surname = "Minbaeva";
    data[1].height = 175;
    data[1].weight = 55;
    data[1].birth = "09.04.2004";
    data[1].bloodtype = "+3";
    data[1].ill = "astma";
    data[1].period = "30.10.2019 - 22.03.2022";
    data[1].lastd = "20.04.2023";
    data[1].days = "0";
    data[1].procedure = "narcosis";

    data[2].login = "milos";
    data[2].password = "134567";
    data[2].name = "Milos";
    data[2].surname = "Bikovich";
    data[2].height = 175;
    data[2].weight = 160;
    data[2].birth = "13.01.1988";
    data[2].bloodtype = "+1";
    data[2].ill = "overweight";
    data[2].period = "12.07.2011 - 22.03.2024";
    data[2].lastd = "20.04.2022";
    data[2].days = "30";
    data[2].procedure = "dialysis";
}

struct Accountassis {
    string type;
    string login;
    string password;
    string name;
    string surname;
    string datework;
    int zarik;
    
};

void dataBas(vector <Accountassis>& dat) {
    dat[0].type = "medassistance";
    dat[0].login = "amina";
    dat[0].password = "Qwerty";
    dat[0].name = "Amina";
    dat[0].surname = "Kyrgyzbaeva";
    dat[0].datework = "20.01.1999";
    dat[0].zarik = 250;
    
    dat[1].type = "medassistance";
    dat[1].login = "vafo";
    dat[1].password = "Qwertye";
    dat[1].name = "Vafo";
    dat[1].surname = "Parvani";
    dat[1].datework = "20.01.2003";
    dat[1].zarik = 222;
    
    dat[2].type = "medassistance";
    dat[2].login = "asyl";
    dat[2].password = "danilka";
    dat[2].name = "Asyl";
    dat[2].surname = "Abdrahmaniva";
    dat[2].datework = "31.12.2022";
    dat[2].zarik = 500;
    
    dat[3].type = "doctor";
    dat[3].login = "david";
    dat[3].password = "chert";
    dat[3].name = "David";
    dat[3].surname = "Ostapchenko";
    dat[3].datework = "20.02.2020";
    dat[3].zarik = 550;
    
    dat[4].type = "doctor";
    dat[4].login = "gigi";
    dat[4].password = "hadid23";
    dat[4].name = "Gigi";
    dat[4].surname = "Hadid";
    dat[4].datework = "11.02.2021";
    dat[4].zarik = 1500;
    
    dat[5].type = "doctor";
    dat[5].login = "Kendall";
    dat[5].password = "jenner202";
    dat[5].name = "Kendall";
    dat[5].surname = "Jenner";
    dat[5].datework = "01.02.1990";
    dat[5].zarik = 2200;
}
