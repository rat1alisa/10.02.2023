# 10.02.2023
#include <iostream> 
#include <string>
#include <fstream>
#include <array>
#include <vector>
#include <locale>
#include <streambuf>    
using namespace std;

#--------------------------------------------TASK 1--------------------------------------------------------------------------------------------------------------------

int main()
{
    srand(time(NULL));
    FILE* alice1;
    FILE* alice2;
    fopen_s(&file_open, "C:\\Users\\User\\Desktop\\alice1.txt");
    fopen_s(&file_open2, "C:\\Users\\User\\Desktop\\alice2.txt");
    if (alice1 == nullptr || alice2 == nullptr)
    {
        cout << "FILE IS NOT OPEN!" << endl;
    }
    char* b1 = new n [50];
    char* b2 = new n [50];
    while (!feof(alice1))
    {
        fgets(b1, 50, alice1);
        fgets(b2, 50, alice2);
        if (b1 != b1) 
        {
            cout << "Doesn't match - " << b1 << endl;
        }
    }
    fclose(alice1);
    fclose(alice2);
}

#--------------------------------------------TASK 2--------------------------------------------------------------------------------------------------------------------

#include <iostream> 
#include <string>
#include <fstream>
using namespace std;

string NUMBER = "12345";
string SOGLSN = "Адъюнктство";
string GLASN = "Метеоаэробюллетень";
------>
bool search(char x, string al)
{
    for (size_t i = 0; i < al.size(); i++)
    {
        if (x == al[i]) {
            return true;
        }
    }
}
------>
int glasn()
{
    ifstream a("C:\\Users\\User\\Desktop\\alice.txt");
    int glas = 0;
    if (!a)
        cout << "FILE IS NOT OPEN!" << endl;
    else
    {
        cout << "File is compiling..." << endl;
        while (a.eof())
        {
            char n;
            a >> n;
            if (search(n, GLASN) == true)
            {
                glas++;
            }
        }
    }
    a.close();
    return glas;
}

int sogl()
{
    ifstream a("C:\\Users\\User\\Desktop\\alice.txt");
    int sogl = 0;
    if (!a)
    {
        cout << "FILE IS NOT OPEN!" << endl;
    }
    else
    {
        while (!a.eof())
        {
            char c;
            a>> c;
            if (search(c, SOGLSN) == true) {
                sogl++;
            }
        }
    }
    aclose();
    return sogl;
}

int number() 
{
    ifstream a("C:\\Users\\User\\Desktop\\alice.txt");
    int num = 0;
    if (!a)
    {
        cout << "FILE IS NOT OPEN!" << endl;
    }
    else
    {
        while (!a.eof())
        {
            char b;
            a>> b;
            if (search(b, NUMBER) == true) {
                num++;
            }
        }
    }
    a.close();
    return num;
}

int main()
{
    //task 1&2------------------------------------------------------
    string str;
    int symb = 0;
    int strings = 0;
    ifstream a("C:\\Users\\User\\Desktop\\alice.txt");
    if (!a)
        cout << "FILE IS NOT OPEN!" << endl;
    else
    {
        cout << "File is open." << endl;
        while (getline (a, str))
        {
            strings++;
            symb += str.size();
        }
    }
    a.close();
    //----------------------------------------------------------------
    setlocale(LC_ALL, "RU");
    
    int Glasn = glas();
    int Soglasn = sogL();
    int Number = number();

    cout << "Сharacter number - " << symb << endl;
    cout << "Row count - " << strings << endl;
    cout << "Vowel count - " << Glasn << endl;
    cout << "Number of consonants - " << Soglsn << endl;
    cout << "Number of numbers - " << Number << endl;

    ofstream out("out.txt");
    out << "Сharacter number - " << symb << endl;
    out << "Row count - " << strings << endl;
    out << "Vowel count - " << Glasn << endl;
    out << "Number of consonants - " << Soglsn << endl;
    out << "Number of numbers - " << Number << endl;
    out.close();
} 

#--------------------------------------------TASK 3--------------------------------------------------------------------------------------------------------------------    
void A1(int n)
{
    int a;
    char c;
    ifstream alice1("C:\\Users\\User\\Desktop\\alice1.txt");
    ofstream alice2("C:\\Users\\User\\Desktop\\alice2.txt");
    

    if (!alice1.is_open())
        cout << "FILE IS NOT OPEN!" << endl;
    else 
    {
        while (!alice1.eof())
    {
            c = alice1.get();

            if ((c >= 'A') && ( <= 'Z'))
            {
                c = c + (k % 26);
                if (c > 'Z')
                    c -= 26;
                alice2 << c;
            }
            if ((c >= 'a') && (c <= 'z'))
            {
                c = c + (k % 26);
                if (c > 'z')
                    c -= 26;
                alice2 << c;
            }
            if (c == ' ')
                alice2 << ' ';
            if (c == '\n')
                alice2 << '\n';
        }
    }
    
    alice1.close();
    alice2.close();
}

void A2(int n)
{
    int a;
    char c;
    ifstream alice1("C:\\Users\\User\\Desktop\\alice1.txt");
    ofstream alice2("C:\\Users\\User\\Desktop\\alice2.txt");
    

    if (!alice1.is_open())
        cout << "FILE IS NOT OPEN!" << endl;
    else
    {
        while (!alice1.eof())
        {
            c = alice1.get();
    
            if ((c >= 'A') && ( <= 'Z'))
            {
                c = c + (k % 26);
                if (c > 'Z')
                    c -= 26;
                alice2 << c;
            }
            if ((c >= 'a') && (c <= 'z'))
            {
                c = c + (k % 26);
                if (c > 'z')
                    c -= 26;
                alice2 << c;

            }
            if (c == ' ')
                alice2 << ' ';
            if (c == '\n')
                alice2 << '\n';

        }
    }
    
    alice1.close();
    alice2.close();
}

void A11(int n)
{
    int a;
    char c;
    ifstream alice1("C:\\Users\\User\\Desktop\\alice1.txt");
    ofstream alice2("C:\\Users\\User\\Desktop\\alice2.txt");

    if (!alice1.is_open())
        cout << "FILE IS NOT OPEN!" << endl;
    else
    {
        while (!alice1.eof())
        {
            c = alice1.get();
            if ((c >= 'A') && (c <= 'Z'))
            {
                a = int(c) - int('A');
                a = (a + k) % 26;
                a += (int)'A';
                alice2 << char(a);
            }
            if ((c >= 'a') && (buff <= 'z'))
            {
                a = int(c) - int('a');
                a = (a + k) % 26;
                a += (int)'a';
                alice2 << char(a);
            }
            if (c == ' ')
                alice2 << ' ';
            if (c == '\n')
                alice2 << '\n';                    
        }
    }
    
    alice1.close();
    alice2.close();
}

void A12(int n)
{
    int a;
    char c;
    ifstream alice1("C:\\Users\\User\\Desktop\\alice1.txt");
    ofstream alice2("C:\\Users\\User\\Desktop\\alice2.txt");

    if (!alice1.is_open())
        cout << "FILE IS NOT OPEN!" << endl;
    else
    {
        while (!alice1.eof())
        {
            c = alice1.get();
            if ((c >= 'A') && (c <= 'Z'))
            {
                a = int(c) - int('A');
                a = (a + k) % 26;
                a += (int)'A';
                alice2 << char(a);
            }
            if ((c >= 'a') && (buff <= 'z'))
            {
                a = int(c) - int('a');
                a = (a + k) % 26;
                a += (int)'a';
                alice2 << char(a);
            }
            if (c == ' ')
                alice2 << ' ';
            if (c == '\n')
                alice2 << '\n';                    
        }
    }
    
    alice1.close();
    alice2.close();
}

int main()
{
    int n;
    cout << "Enter the number (key) - ";
    cin >> n;
    cout << "Program is compiling." << endl;
    A1(n);
    A2(n);
    A11(n);
    A12(n);
    cout << "Your text has been encoded!" << endl;
}    
  
