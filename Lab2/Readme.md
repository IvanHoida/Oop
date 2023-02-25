#include <iostream>
using namespace std;

class ComplexNumber {
private:
    double real; // дійсна частина
    double imaginary; // уявна частина
public:
    // конструктор з нульовим значенням
    ComplexNumber() {
        real = 0.0;
        imaginary = 0.0;
    }

    // конструктор з параметрами
    ComplexNumber(double r, double i) {
        real = r;
        imaginary = i;
    }

    // метод для встановлення дійсної частини
    void setReal(double r) {
        real = r;
    }

    // метод для встановлення уявної частини
    void setImaginary(double i) {
        imaginary = i;
    }

    // метод для отримання дійсної частини
    double getReal() {
        return real;
    }

    // метод для отримання уявної частини
    double getImaginary() {
        return imaginary;
    }

    //метод для виводу комплексних чисел у вигляді (a + ib)
    void PrintComplexNumber() {
        cout << "(" << this->getReal() << " + i" << this->getImaginary() << ")"<<endl;
    }

    // дружня функція для додавання двох комплексних чисел
    friend ComplexNumber frd(ComplexNumber num1, ComplexNumber num2);
};

// дружня функція для додавання двох комплексних чисел
ComplexNumber frd(ComplexNumber num1, ComplexNumber num2) {
    double real = num1.real + num2.real;
    double imaginary = num1.imaginary + num2.imaginary;
    return ComplexNumber(real, imaginary);
}

int main() {
    ComplexNumber x1 = ComplexNumber();
    ComplexNumber x2 = ComplexNumber(3,1);
    x1.setReal(3);
    x1.setImaginary(7);
    x1.PrintComplexNumber();
    x2.PrintComplexNumber();
    ComplexNumber x3 = frd(x1, x2);
    x3.PrintComplexNumber();
}