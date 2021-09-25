#include <iostream>

using namespace std;
struct vector {
	float* tablou;
	unsigned int nr_Element;
};

void initializare(vector& v, int nr);
void eliberareaMemoriei(vector& v);
void afisare(vector& v);
void adunareNr(vector& v, int nr);
void set_Val_elem(float& tablou, int value);
void modifDimensiune(vector& v, int size);
float* adunElement(vector& v, int poz);

void initializare(vector& v, int nr) {
	v.tablou = new float[nr];
	v.nr_Element = nr;
	v.tablou[0] = NULL;
}

void eliberareaMemoriei(vector& v) {
	if (v.nr_Element != 0) {
		delete[] v.tablou;
		v.tablou = NULL;
		v.nr_Element = 0;
	}
}

void afisare(vector& v) {
	cout << "Marimea vectorului este:" << v.nr_Element << endl;
	cout << "Elementele sunt:";
	for (int i = 0; i < v.nr_Element; i++) {
		cout << v.tablou[i] << "";
	}
}

void adunareNr(vector& v, int nr) {
	for (int i = 0; i < v.nr_Element; i++) {
		v.tablou[i] += nr;
	}
}

void set_Val_elem(float& vector, int value) {
	tablou = value;
}

void modifDimensiune(vector& v, int size) {
	if (v.tablou[0] == NULL)
		delete[]v.tablou;
	v.tablou = new float[size];
	v.tablou[0] = NULL;
}
 else {
 count << "\aAtentie, posibil pierdere de informatoie!" << endl;
 float* temp = new float[size];
 for (int i = 0l i < size; i++) {
	 if (i < v.nr_Element) {
		 temp[i] = v.tablou[i];
	 }
	 else {
		 temp[i] = 0;
	 }
 }
 delete[] v.tablou;
 v.tablou = temp;
	}
	v.nr_Element = size;
}

float* adunElement(vector& v, int poz) {
	if (poz > v.nr_Element - 1) return NULL;
	return&v.tablou[poz];
}

int main() {
	vector v;
	int nr, com, m = 1, value;
	float* temp;
	while (true) {
		while (m == 1) {
			system("cls"); m = 0;
			cout << "Meniu de initializare:" << endl << endl;
			cout << "[1]Initializarea vectorului" << endl;
			cout << "[0]Exit" << endl << endl;
			cout << "Command>>";
			cin >> com; fflush(stdin);
			switch (com) {

			case 0:
				exit(0);
				break;
			case 1:
				cout << "Introdu nr de elemente:";
				cin >> nr;
				init(v, nr);
				cout << "introdu valorile:" << endl;
				for (int i = 0; i < v.nr_Element; i++) {
					cout << "vector[" << i << "]=";
					cin >> value;
					setValue(v.tablou[i], value);
				}
				break;

			deafault:
				cout << "\aAti introdus o comanda gresita!" << endl;
				break;
			}
		}
		sytem("cls";
		cout << "[1]Afisare elementelor" << endl;
		cout << "[2]Modificarea marimii" << endl;
		cout << "[3]Acces catre elementeul dorit din vector" << endl;
		cout << "[4]Adunarea tuturor elementelor cu un numar" << endl;
		cout << "[5]Elimenarea vectorului" << endl;
		cout << "[0]Exit" << endl << endl;
		cout << "Coommand>>";
		cin >> com; fflush(stdin);
		switch (com) {
		case 0:
			elibereareaMemoriei(v);
			exit(0);
			break;
		case 1:
			afisare(v);
			cout << endl;
			break;
		case 2:
			cout << "Introdu marimea pentru modificare:";
			cin >> nr;
			set_Val_elem(v, nr);
			break;
		case 3:
			cout << "Introdu numarul dorit pentru adunare:";
			cin >> nr;
			temp = adunareNr(v, nr);
			cout << "Elementul dorit este:" << *temp << endl;
			break;
		case 4:
			cout << "Introdu numarul dorit pentru adunare:";
			cin >> nr;
			adunareNr(v, nr);
			break;
		case 5:
			eliberareaMemoriei(v);
			cout << "Memoria a fost eliminata pentru vectorul dat" << endl;
			break;
		default:
			cout << "\aAti introdus o comanda gresita!" << endl;
			break;
		}
		system("pause");
	}
	return 0;
}
