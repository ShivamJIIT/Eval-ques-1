#include <iostream>
#include <vector>
using namespace std;
void printPolynomial(const vector<int>& coeffs) {
    bool first = true;
    for (int i = coeffs.size() - 1; i >= 0; --i) {
        if (coeffs[i] != 0) {
            if (!first) {
                cout << (coeffs[i] > 0 ? " + " : " - ");
            }
            first = false;
            if (i == 0 || coeffs[i] != 1) {
                cout << std::abs(coeffs[i]);
            }
            if (i > 0) {
                cout << "x";
                if (i > 1) {
                    cout << "^" << i;
                }
            }
        }
    }
    cout << endl;
}

vector<int> computeDerivative(const vector<int>& coeffs) {
    vector<int> derivative;
    for (int i = 1; i < coeffs.size(); ++i) {
        derivative.push_back(coeffs[i] * i);
    }
    return derivative;
}

int main() {
    int degree;
    cout << "Enter the degree of the polynomial (up to 5): ";
    cin >> degree;

    if (degree < 0 || degree > 5) {
        cout << "Degree must be between 0 and 5." << endl;
        return 1;
    }

    vector<int> coeffs(degree + 1);

    cout << "Enter the coefficients from highest degree to constant term:" << endl;
    for (int i = degree; i >= 0; --i) {
        cout << "Coefficient of x^" << i << ": ";
        cin >> coeffs[i];
    }

    cout << "Original polynomial: ";
    printPolynomial(coeffs);

    vector<int> derivative = computeDerivative(coeffs);

    cout << "Derivative polynomial: ";
    if (derivative.empty()) {
        cout << "0" << endl;
    } else {
        printPolynomial(derivative);
    }

    return 0;
}
