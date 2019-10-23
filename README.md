#include<iostream>
#include<stdlib.h>
#include<windows.h>
#include<stdio.h>
#include<iomanip>
#include<string>
#include<vector>
#include<cmath>
#include<array>
#include<conio.h>
#define ARREGLO_MAX 100


using namespace std;

//Binario a DEcimal
string Text_Bin(string tex);
int convertirBinarioaDecimal(long long);
string Dec_Bin(int num);
long long n;
int convertirBinarioaDecimal(long long)
{
	int numeroDecimal = 0, i = 0, recordatorio;
	while (n != 0)
	{
		recordatorio = n % 10;
		n /= 10;
		numeroDecimal += recordatorio * pow(2, i);
		++i;
	}
	return numeroDecimal;
}

string Dec_Bin(int num) {
	string binari;
	int potencia = 0;
	for (int i = 0; pow(2, i) <= num; i++)
	{
		potencia = i + 1;
	}
	for (int i = 0; i <= potencia; i++)
	{
		if (num >= pow(2, potencia - i))
		{
			num -= pow(2, potencia - i);
			binari += "1";
		}
		else
		{
			binari += "0";
		}
		if (binari != "0")
		{
			binari.erase(0, 0);
		}
	}
	return binari;
}


string Text_Bin(string tex) {
	vector <int> letras;
	vector <string> bina;
	string texto;
	
	for (int i = 0; i < tex.length(); i++)
	{
		letras.push_back(tex[i]);
		bina.push_back(Dec_Bin(letras[i]));
		texto += bina[i] + " ";
	}
	return texto;

}
//Moverse en pantalla
void gotoxy(int x, int y) {
	HANDLE hcon;
	hcon = GetStdHandle(STD_OUTPUT_HANDLE);
	COORD dwPos;
	dwPos.X = x;
	dwPos.Y = y;
	SetConsoleCursorPosition(hcon, dwPos);
}




//Material cedido por Roberto Bueno.
//== = Reseteadores == =
//== = Texto Default == =
//Texto
#define DEFAULT0 "\x1b[0m"
//Color
#define DEFAULT1 "\x1b[39m"
//Fondo
#define DEFAULTF "\x1b[49m"
//== = Colores == =
//== = Texto == =
//-Rojo
#define RED "\x1b[31m"
//- Verde
#define GREEN "\x1b[32m"
//- Negro
#define BLACK "\x1b[30m"
//- Azul
#define BLUE "\x1b[34m"
//- Amarillo
#define YELLOW "\x1b[33m"
//- Magenta
#define MAGENTA "\x1b[35m"
//- Cyan
#define CYAN "\x1b[36m"
//- Blanco
#define WHITE "\x1b[37m"
//- Gris Claro
#define LIGHT_GRAY "\x1b[90m"
//- Rojo Claro
#define LIGHT_RED "\x1b[91m"
//- Verde Claro
#define LIGHT_GREEN "\x1b[92m"
//- Amarillo Claro
#define LIGHT_YELLOW "\x1b[93m"
//- Azul Claro
#define LIGHT_BLUE "\x1b[94m"
//- Magenta Claro
#define LIGHT_MAGENTA "\x1b[95m"
//- Cyan Claro
#define LIGHT_CYAN "\x1b[96m"
//- Blanco Claro
#define LIGHT_WHITE "\x1b[97m"
//== = Modificadores == =
//== = Texto == =
//-Dim(No identificado aun)
#define DIM "\x1b[2m"
//- Reverse(Si el fondo es negro, el texto sera blanco y al contrario)
#define REVERSE "\x1b[7m"
//- Hidden(No identificado aun)
#define HIDDEN "\x1b[8b"
//- Bold(ON / OFF) (No identificado aun)
#define BOLD_ON "\x1b[1m"
#define BOLD_OFF "\x1b[21m"
//- Underline(ON / OFF) (Subraya el texto)
#define UNDERLINE_ON "\x1b[4m"
#define UNDERLINE_OFF "\x1b[24m"
//- Blink(ON / OFF) (No identificado aun)
#define BLINK_ON "\x1b[5m"
#define BLINK_OFF "\x1b[25m"
//== = Fondos == =
//== = Texto == =
//-Negro
#define BLACKF "\x1b[40m"
//- Rojo
#define REDF "\x1b[41m"
//- Verde
#define GREENF "\x1b[42m"
//- Amarillo
#define YELLOWF "\x1b[43m"
//- Azul
#define BLUEF "\x1b[44m"
//- Magenta
#define MAGENTAF "\x1b[45m"
//- Cyan
#define CYANF "\x1b[46m"
//- Blanco
#define WHITEF "\x1b[47m"
//- Gris Claro
#define LIGHT_GRAYF "\x1b[100m"
//- Rojo Claro
#define LIGHT_REDF "\x1b[101m"
//- Verde Claro
#define LIGHT_GREENF "\x1b[102m"
//- Amarillo Claro
#define LIGHT_YELLOWF "\x1b[103m"
//- Azul Claro
#define LIGHT_BLUEF "\x1b[104m"
//- Magenta Claro
#define LIGHT_MAGENTAF "\x1b[105m"
//- Cyan Claro
#define LIGHT_CYANF "\x1b[106m"
//- Blanco Claro
#define LIGHT_WHITEF "\x1b[107m"

int main()
{
	void pausa();
	{
		//Titulo de cuadro
		gotoxy(50, 12); cout << WHITEF BLACK" Calculadora de conversiones " DEFAULT0;
		gotoxy(48, 10); cout << CYANF "                                 " DEFAULT0 << endl;
		gotoxy(48, 11); cout << CYANF "  " DEFAULT0;
		gotoxy(48, 12); cout << CYANF "  " DEFAULT0;
		gotoxy(48, 13); cout << CYANF "  " DEFAULT0;
		gotoxy(48, 14); cout << CYANF "  " DEFAULT0;
		gotoxy(48, 12); cout << CYANF "  " DEFAULT0;
		gotoxy(48, 15); cout << CYANF "                                 " DEFAULT0 << endl;

		gotoxy(79, 11); cout << CYANF "  " DEFAULT0;
		gotoxy(79, 12); cout << CYANF "  " DEFAULT0;
		gotoxy(79, 13); cout << CYANF "  " DEFAULT0;
		gotoxy(79, 14); cout << CYANF "  " DEFAULT0;


		//Fondo del titulo
		gotoxy(50, 11); cout << WHITEF "                             " DEFAULT0;
		gotoxy(50, 13); cout << WHITEF "                             " DEFAULT0;
		gotoxy(50, 14); cout << WHITEF "                             " DEFAULT0;


		getwchar();
	}

	//Cuerpo de opciones

	system("cls");
	gotoxy(40, 4);
	cout << LIGHT_CYANF "                                                  " DEFAULT0 << endl;
	gotoxy(40, 5);
	cout << LIGHT_CYANF "  " DEFAULT0;
	cout << LIGHT_CYANF "\t\t\t\t\t\t" DEFAULT0 << LIGHT_CYANF "  " DEFAULT0 << endl;
	gotoxy(40, 6);
	cout << LIGHT_CYANF "  " DEFAULT0;
	cout << LIGHT_CYANF "\t\t\t\t\t\t" DEFAULT0 << LIGHT_CYANF "  " DEFAULT0 << endl;
	gotoxy(40, 7);
	cout << LIGHT_CYANF "  " DEFAULT0;
	cout << LIGHT_CYANF "" DEFAULT0 << GREEN"\tQue Conversion quieres realizar?:" DEFAULT0 << LIGHT_CYANF "\t" DEFAULT0 << LIGHT_CYANF "  " DEFAULT0 << endl;
	gotoxy(40, 8);
	cout << LIGHT_CYANF "  " DEFAULT0;
	gotoxy(88, 8);
	cout << LIGHT_CYANF "  " DEFAULT0;
	gotoxy(40, 9);
	cout << LIGHT_CYANF "  " DEFAULT0 << UNDERLINE_ON"\t1.-Binario--Decimal" DEFAULT0 << LIGHT_CYANF "\t\t\t" DEFAULT0 << LIGHT_CYANF "  " DEFAULT0 << endl;
	gotoxy(40, 10);
	cout << LIGHT_CYANF "  " DEFAULT0 << UNDERLINE_ON"\t2.- Decimal--Binario" DEFAULT0 << LIGHT_CYANF "\t\t\t" DEFAULT0 << LIGHT_CYANF "  " DEFAULT0 << endl;
	gotoxy(40, 11);
	cout << LIGHT_CYANF "  " DEFAULT0 << UNDERLINE_ON"\t3.- Binario--Octal" DEFAULT0 << LIGHT_CYANF "\t\t\t" DEFAULT0 << LIGHT_CYANF "  " DEFAULT0 << endl;
	gotoxy(40, 12);
	cout << LIGHT_CYANF "  " DEFAULT0 << UNDERLINE_ON"\t4.- Binario--Hexadecimal" DEFAULT0 << LIGHT_CYANF "\t\t" DEFAULT0 << LIGHT_CYANF "  " DEFAULT0 << endl;
	gotoxy(40, 13);
	cout << LIGHT_CYANF "  " DEFAULT0 << UNDERLINE_ON"\t5.- Texto--binario" DEFAULT0 << LIGHT_CYANF "\t\t\t" DEFAULT0 << LIGHT_CYANF "  " DEFAULT0 << endl;
	gotoxy(40, 14);
	cout << LIGHT_CYANF "  " DEFAULT0;
	cout << LIGHT_CYANF "\t\t\t\t\t\t" DEFAULT0 << LIGHT_CYANF "  " DEFAULT0 << endl;
	gotoxy(40, 15);
	cout << LIGHT_CYANF "  " DEFAULT0;
	cout << LIGHT_CYANF "\t\t\t\t\t\t" DEFAULT0 << LIGHT_CYANF "  " DEFAULT0 << endl;
	gotoxy(40, 16);
	cout << LIGHT_CYANF "  " DEFAULT0;
	cout << LIGHT_CYANF "\t\t\t\t\t\t" DEFAULT0 << LIGHT_CYANF "  " DEFAULT0 << endl;
	gotoxy(40, 17);
	cout << LIGHT_CYANF "  " DEFAULT0;
	cout << LIGHT_CYANF "\t\t\t\t\t\t" DEFAULT0 << LIGHT_CYANF "  " DEFAULT0 << endl;
	gotoxy(40, 18);
	cout << LIGHT_CYANF "  " DEFAULT0;
	cout << LIGHT_CYANF "\t\t\t\t\t\t" DEFAULT0 << LIGHT_CYANF "  " DEFAULT0 << endl;
	gotoxy(40, 19);
	cout << LIGHT_CYANF "  " DEFAULT0;
	cout << LIGHT_CYANF "\t\t\t\t\t\t" DEFAULT0 << LIGHT_CYANF "  " DEFAULT0 << endl;
	gotoxy(40, 20);
	cout << LIGHT_CYANF "  " DEFAULT0;
	cout << LIGHT_CYANF YELLOW "                                                " DEFAULT0 << endl;
	gotoxy(45, 15);
	cout << "Que tipo de conversion quieres realizar? ";
	gotoxy(45, 17);
	int conv;
	cin >> conv;

	getwchar();

	//Cuerpo de  cases
	switch (conv)
	{
	case 1:

		system("cls");
		system("color 1f");
		gotoxy(39, 12);
		cout << LIGHT_GREENF "                                               " DEFAULT0 << endl;
		gotoxy(38, 12);
		cout << LIGHT_GREENF "  ";
		gotoxy(38, 11);
		cout << LIGHT_GREENF "  ";
		gotoxy(38, 10);
		cout << LIGHT_GREENF "  ";
		gotoxy(38, 9);
		cout << LIGHT_GREENF "  ";
		gotoxy(38, 8);
		cout << LIGHT_GREENF "  ";
		gotoxy(38, 7);
		cout << LIGHT_GREENF "  ";
		gotoxy(84, 7);
		cout << LIGHT_GREENF "  ";
		gotoxy(84, 8);
		cout << LIGHT_GREENF "  ";
		gotoxy(84, 9);
		cout << LIGHT_GREENF "  ";
		gotoxy(84, 10);
		cout << LIGHT_GREENF "  ";
		gotoxy(84, 11);
		cout << LIGHT_GREENF "  ";
		gotoxy(84, 12);
		cout << LIGHT_GREENF "  ";
		gotoxy(40, 9);
		cout << BLUEF "Elegiste la conversion de Binario a decimal" << endl;
		gotoxy(40, 10);
		cout << BLUEF"Ingresa el numero binario a convertir :";
		gotoxy(39, 7);
		cout << LIGHT_GREENF "                                               " DEFAULT0 << endl;
		gotoxy(41, 11);
		cin >> n;
		gotoxy(43, 13);
		cout << n << " en binario = " << convertirBinarioaDecimal(n) << " en decimal";
		gotoxy(38, 13);
		cout << LIGHT_GREENF "  ";
		gotoxy(84, 13);
		cout << LIGHT_GREENF "  ";
		gotoxy(38, 14);
		cout << LIGHT_GREENF "                                                " DEFAULT0 << endl;

		getwchar();
		getwchar();
		
		break;
	case 2:
		system("cls");
		system("color E0");
		int m;
		m = 0;
		gotoxy(30, 10);
		cout << "**********************************************";
		gotoxy(30, 13);
		cout << "**********************************************";
		gotoxy(30, 11);
		cout << "Elegiste la conversion de Decimal a Binario";
		gotoxy(30, 12);
		cout << "Ingresa el numero que quieres convertir a binario :";
		gotoxy(40, 14);
		cin >> m;
		gotoxy(30, 15);
		cout <<"El resultado de la conversion es :" << Dec_Bin(m);

		getwchar();
		getwchar();

		break;
		
	case 3:
	{
		system("cls");
		string a;
		int bi[ARREGLO_MAX];
		int i;
		int num;
		string res[ARREGLO_MAX];
		gotoxy(39, 12);
		cout << LIGHT_GREENF "                                               " DEFAULT0 << endl;
		gotoxy(38, 6);
		cout << LIGHT_GREENF "                                                " DEFAULT0 << endl;
		gotoxy(38, 12);
		cout << LIGHT_GREENF "  " DEFAULT0;
		gotoxy(38, 11);
		cout << LIGHT_GREENF "  " DEFAULT0;
		gotoxy(38, 10);
		cout << LIGHT_GREENF "  " DEFAULT0;
		gotoxy(38, 9);
		cout << LIGHT_GREENF "  " DEFAULT0;
		gotoxy(38, 8);
		cout << LIGHT_GREENF "  " DEFAULT0;
		gotoxy(38, 7);
		cout << LIGHT_GREENF "  " DEFAULT0;
		gotoxy(84, 7);
		cout << LIGHT_GREENF "  " DEFAULT0;
		gotoxy(84, 8);
		cout << LIGHT_GREENF "  " DEFAULT0;
		gotoxy(84, 9);
		cout << LIGHT_GREENF "  " DEFAULT0;
		gotoxy(84, 10);
		cout << LIGHT_GREENF "  " DEFAULT0;
		gotoxy(84, 11);
		cout << LIGHT_GREENF "  " DEFAULT0;
		gotoxy(84, 12);
		cout << LIGHT_GREENF "  " DEFAULT0;
		gotoxy(42, 9);
		cout << "Elegiste la conversion de Binario a octal" << endl;
		gotoxy(42, 10);
		cout << "ingrese el numero de pares de 3:" << endl;
		gotoxy(42, 11);
		cin >> num;

		for (i = 1; i <= num; i++) {
			cout << "Ingresa tres digitos de numeros: " << endl;
			cin >> bi[i - 1];
	
		}
		for (i = 0; i <= num; i++) {
			switch (bi[i - 1]) {
			case 000:
				res[i - 1] = "0";
				break;
			case 001:
				res[i - 1] = "1";
				break;
			case 010:
				res[i - 1] = "2";
				break;
			case 011:
				res[i - 1] = "3";
				break;
			case 100:
				res[i - 1] = "4";
				break;
			case 101:
				res[i - 1] = "5";
				break;
			case 110:
				res[i - 1] = "6";
				break;
			case 111:
				res[i - 1] = "7";
				break;
			}
		}
		for (i = 1; i <= num; i++) {
			a = a + res[i - 1];
		}
		gotoxy(43, 13);
		cout << "El resultado de la conversion a octal es : ";
		gotoxy(43, 14);
		cout << a << endl;

		getwchar();
		getwchar();

		break;
	}
	case 4:
		system("cls");
		system("color 35");
		gotoxy(40,13);
		cout << "Elegiste la conversion de Binario a hexadecimal";
		{
			int exp, digito, decimal;
			double binario;
			int num, temp, i = 1, j, r;
			char hex[50];

			gotoxy(40, 14);
			cout << "Ingresa un numero binario: " << endl;
			gotoxy(40, 16);
			cin >> binario;

			exp = 0;
			decimal = 0;

			while (((int)(binario / 10) != 0))
			{
				digito = (int)binario % 10;
				decimal = decimal + digito * pow(2.0, exp);
				exp++;
				binario = (int)(binario / 10);
			}

			num = decimal + binario * pow(2.0, exp);

			//system pause
			temp = num;
			while (temp != 0)
			{
				r = temp % 16;
				if (r < 10)
					hex[i++] = r + 48;
				else
					hex[i++] = r + 55;
				temp = temp / 16;
			}
			gotoxy(40, 17);
			cout << "\n El equivalente Hexadecimal del numero binario es : ";
			for (j = i; j > 0; j--)
				cout << hex[j];

			getwchar();
			getwchar();

			break;
		}
	case 5:
		system("cls");
		system("color 2f ");


		string z;
		gotoxy(38, 9);
		cout << "******************************************";
		gotoxy(38, 12);
		cout << "******************************************";
		gotoxy(40, 10);
		cout << BLACK "Elegiste la opcion de Texto a Binario";
		gotoxy(40, 11);
		cout << "Ingresa el texto a convertir :";
		getline(cin, z);
		gotoxy(40, 14);
		cout << "El resultado de la conversion es :";
		gotoxy(40, 15);
		cout << Text_Bin(z);

		getwchar();
		getwchar();

		break;
		
	}
	

		//Cuerpo de Creditos 

	    system("cls");

		cout << LIGHT_CYANF "  " DEFAULT0;                                           cout << LIGHT_CYANF "\t\t\t\t\t\t" DEFAULT0 << LIGHT_CYANF "  " DEFAULT0 << endl;

		cout << LIGHT_CYANF "  " DEFAULT0;                                           cout << LIGHT_CYANF "\t\t\t\t\t\t" DEFAULT0 << LIGHT_CYANF "  " DEFAULT0 << endl;

		cout << LIGHT_CYANF "  " DEFAULT0;
		cout << LIGHT_CYANF "" DEFAULT0 << "\tProyeto hecho por:" << LIGHT_CYANF "\t\t\t" DEFAULT0 << LIGHT_CYANF "  " DEFAULT0 << endl;
		cout << LIGHT_CYANF "  " DEFAULT0 << UNDERLINE_ON"\t Brenda Guadalupe Grajeda Lopez" DEFAULT0 << LIGHT_CYANF "\t\t" DEFAULT0 << LIGHT_CYANF "  " DEFAULT0 << endl;
		cout << LIGHT_CYANF "  " DEFAULT0 << UNDERLINE_ON"\t Edwin Yahir Carrillo Sanchez" DEFAULT0 << LIGHT_CYANF "\t\t" DEFAULT0 << LIGHT_CYANF "  " DEFAULT0 << endl;
		cout << LIGHT_CYANF "  " DEFAULT0 << UNDERLINE_ON"\t Heber Peleg Perez Martinez" DEFAULT0 << LIGHT_CYANF "\t\t" DEFAULT0 << LIGHT_CYANF "  " DEFAULT0 << endl;
		cout << LIGHT_CYANF "  " DEFAULT0 << UNDERLINE_ON"\t Saydel Pablo Tenoch Santos Perez" DEFAULT0 << LIGHT_CYANF "\t" DEFAULT0 << LIGHT_CYANF "  " DEFAULT0 << endl;
		cout << LIGHT_CYANF "  " DEFAULT0 << UNDERLINE_ON"\t Mauricio Chavez Mancilla" DEFAULT0 << LIGHT_CYANF "\t\t" DEFAULT0 << LIGHT_CYANF "  " DEFAULT0 << endl;
		cout << LIGHT_CYANF "  " DEFAULT0;
		cout << LIGHT_CYANF "\t\t\t\t\t\t" DEFAULT0 << LIGHT_CYANF "  " DEFAULT0 << endl;
		cout << LIGHT_CYANF "  " DEFAULT0;                                            cout << LIGHT_CYANF "\t\t\t\t\t\t" DEFAULT0 << LIGHT_CYANF "  " DEFAULT0 << endl;

		cout << LIGHT_CYANF "  " DEFAULT0;                                            cout << LIGHT_CYANF "\t\t\t\t\t\t" DEFAULT0 << LIGHT_CYANF "  " DEFAULT0 << endl;

		cout << LIGHT_CYANF "  " DEFAULT0;                                            cout << LIGHT_CYANF "\t\t\t\t\t\t" DEFAULT0 << LIGHT_CYANF "  " DEFAULT0 << endl;

		cout << LIGHT_CYANF "  " DEFAULT0;                                            cout << LIGHT_CYANF "\t\t\t\t\t\t" DEFAULT0 << LIGHT_CYANF "  " DEFAULT0 << endl;

		cout << LIGHT_CYANF "  " DEFAULT0;                                            cout << LIGHT_CYANF "\t\t\t\t\t\t" DEFAULT0 << LIGHT_CYANF "  " DEFAULT0 << endl;

		cout << LIGHT_CYANF "  " DEFAULT0;
		cout << LIGHT_CYANF YELLOW "                                                " DEFAULT0 << endl;

		getwchar();




		return 0;
	}
