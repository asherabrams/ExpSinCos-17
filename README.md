# ExpSinCos-17
/******************************************************************************

                              Online C++ Compiler.
               Code, Compile, Run and Debug C++ program online.
Write your code in this editor and press "Run" button to compile and execute it.

*******************************************************************************/

#include <iostream>
using namespace std;

double a;
// Real number (a) is user-supplied argument.
double b = 1;
// Real number (b) is the sum of successive (m) terms.
double c = 1;
// Real number (c) is the (m)th term.
double d = 1;
// Real number (d) is the (m)th power of (a).
double m;
// We declare (m) as a double because we're going to divide by it.
double n;
// User-supplied limit of (n) terms.
double p = 1;
// Integer (p) is the factorial of (m).
int intm;
// We also need (m) to function as an integer.
int parm;
// Parity of (m) is 1 if odd, 0 if even.
int sigm;
// Sign of the (m)th term in the Sin and Cos series.
// Value is 1 if positive, 0 if negative.
// These are alternating pairs of positive and negative terms.
// We declare it as an int because we're going to divide (intm) by 2 and throw away the remainder.
// This gives us the 1,1,0,0,1,1... pattern that drives the +/- operations.
double outExp;
// The output for (e^a) is just b.  We give it a new name for clarity.
double outSin = 0;
// We initialize the Sine function at 0.
// Odd terms get added to Sine.
double outCos = 1;
// We initialize the Cosine function at 1.
// Even terms go into Cosine.

double func01(double){
    cout << "Enter a degree of precision (integer n):\n";
    cin >> n;
    cout << "Enter an argument (real number a):\n";
    cin >> a;
    for (m = 1; m <= n; m++){
        d = d * a;
        p = p * m;
        c = d / p;
        b = b + c;
        intm = int(m);
        parm = intm % 2;
        sigm = ((intm/2) + 1) % 2;
        outExp = b;
        (parm) ?  ((sigm) ? (outSin = outSin + c) : (outSin = outSin - c)) : 
                  ((sigm) ? (outCos = outCos + c) : (outCos = outCos - c));
     // For odd terms (parm=1), add and subtract alternating terms to Sin.
     // For even terms (parm=0), add and subtract alternating terms to Cos.
        cout << "Iteration (m):  " << m << '\n';
        cout << "Parity (int m mod 2):  " << parm << '\n';
        cout << "Sign of (m):  " << sigm << '\n';
        cout << "Exponent (e^a):  " << outExp << '\n';
        cout << "Sine:  " << outSin << '\n';
        cout << "Cosine:  " << outCos << "\n\n";
        
    }
}


int main()
{
    cout<<"Hello Sin Cos Exp\n\n";
func01(a);
    return 0;
}
