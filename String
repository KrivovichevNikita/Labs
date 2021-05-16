#include <iostream>
using namespace std;
class Mystring 
{
public:

	Mystring()
	{ 
		str = nullptr;
		length = 0;
	}

	Mystring( const char *str) //создание
	{
		length = strlen(str);
		this->str = new char[length + 1];

		for (int i=0; i<length; i++)
		{
			this->str[i] = str[i];
		}

		this->str[length] = '\0';
	}

	~Mystring() // деструктор
	{
		delete[] this->str;
	}


	Mystring(const Mystring& other) //копирование
	{
		length = strlen(other.str);
		this->str = new char[length + 1];

		for (int i = 0; i < length; i++)
		{
			this->str[i] = other.str[i];
		}

		this->str[length] = '\0';
	}

	Mystring& operator=(const Mystring &other) //присваивание
	{
		if (this->str != nullptr)
		{
			delete[] str;
		}
		length = strlen(other.str);
		this->str = new char[length + 1];

		for (int i = 0; i < length; i++)
		{
			this->str[i] = other.str[i];
		}

		this->str[length] = '\0';
		return *this;
	}

	Mystring  operator+(const Mystring& other) //сложение
	{
		Mystring newStr;

		int thislenght = strlen(this->str);
		int otherlenght = strlen(other.str);

		newStr.length = thislenght + otherlenght;

		newStr.str = new char[thislenght + otherlenght + 1];
		int i = 0;
		for (; i < thislenght; i++)
		{
			newStr.str[i] = this->str[i];
		}
		for (int j=0; j < otherlenght; j++, i++)
		{
			newStr.str[i] = other.str[j];
		}
		newStr.str[thislenght + otherlenght] = '\0';
		return newStr;
	}

	void Print() //вывод
	{
		cout << str;
	}

	int len() //длина
	{
		return length;
	}
	
	char& operator [](int ind) //обращение к элементу
	{
		return this->str[ind];
	}
	

private:
	char* str;
	int length;
};

int main() 
{
	Mystring str("Hello");
	Mystring sum;
	sum = "Well";
	sum.Print();
	sum = str + "World";
	str = sum;
	cout << " ";
	str.Print(); 
	str[0] = 'P';
	cout << " ";
	str.Print();
	cout << " " << str.len();
	cout << " " << sum[0];
	return 0;
}
