# EXP-8

# Aim : -

To study and implement C++ 2D array matrices.

# Theory: -
The theory behind 2D array matrices in C++ centers on organizing data into a grid structure with rows and columns, which allows for efficient access and manipulation. A 2D array can be thought of as an array of arrays, where each element is accessed using a pair of indices, (i, j), representing its row and column positions. In memory, these arrays are stored in contiguous blocks, following a row-major order, meaning that elements are stored row by row. This layout affects how quickly and efficiently data can be accessed and modified.

Operations on 2D arrays include traversal (iterating through elements), addition or subtraction of matrices by combining corresponding elements, and multiplication which involves summing products of rows and columns from two matrices. Transposing a matrix involves flipping it over its diagonal, effectively swapping rows and columns.

Dynamic allocation allows for flexible handling of matrices when their size is not known at compile time. By using pointers and memory management techniques, C++ enables the creation and manipulation of 2D arrays whose dimensions can be determined during runtime.

While 2D arrays offer simplicity and direct indexing, they have limitations such as fixed size constraints and the potential for manual memory management errors. To overcome these limitations and enhance functionality, standard libraries like std::vector or specialized libraries like Eigen can be employed. These theoretical foundations are essential for applying 2D arrays in practical contexts such as mathematical computations, computer graphics, and data analysis.

# 1.Entering elements of matrix : 
~~~
//Name: Srihari Nair
//Prn: 23070123131
//Class: EnTC B-2
#include <iostream>
using namespace std;

int main() {
    int temp[3][3], i, j,k,l;
    for (i=0 ; i<3 ; i++){
        for (j=0;j<3;j++){
            cout<<" Enter element-("<<i<<j<<"):";
            cin>>temp[i][j];
        }
    }
    for(k-0; k<3; k++){
        for (l=0;l<3;l++){
            cout<<temp[k][l];
            cout<<" ";
    }
    cout <<endl;
    }
}
~~~

# Output: -

<img width="510" alt="image" src="https://github.com/user-attachments/assets/5309c748-8c56-45d4-8e2b-87a393be3247">

# 2. Addition of two matrices: 
~~~
//Name: Srihari Nair
//Prn: 23070123131
//Class: EnTC B-2
#include <iostream>
using namespace std;

int main() {
    // Define matrix dimensions
    int r1 = 3, c1 = 3;
    int r2 = 3, c2 = 3;
    int m1[r1][c1], m2[r2][c2], sum[r1][c1];
    cout << "Enter elements of the first matrix:" << endl;
    for (int i = 0; i < r1; ++i) {
        for (int j = 0; j < c1; ++j) {
            cout << "Enter element at position (" << i << ", " << j << "): ";
            cin >> m1[i][j];
        }
    }
    cout << "Enter elements of the second matrix:" << endl;
    for (int i = 0; i < r2; ++i) {
        for (int j = 0; j < c2; ++j) {
            cout << "Enter element at position (" << i << ", " << j << "): ";
            cin >> m2[i][j];
        }
    }
    for (int i = 0; i < r1; ++i) {
        for (int j = 0; j < c1; ++j) {
            sum[i][j] = m1[i][j] + m2[i][j];
        }
    }
    cout << endl << "Sum of matrices:" << endl;
    for (int i = 0; i < r1; ++i) {
        for (int j = 0; j < c1; ++j) {
            cout << sum[i][j] << " ";
        }
        cout << endl;
    }
    return 0;
}
~~~

# Output: 

<img width="570" alt="image" src="https://github.com/user-attachments/assets/a1587372-e166-401a-9dc2-29fe3d720c6e">

# 3. Subtraction of two matrices : 
~~~
//Name: Srihari Nair
//Prn: 23070123131
//Class: EnTC B-2
#include <iostream>
using namespace std;

int main() {
    int r1 = 3, c1 = 3;
    int r2 = 3, c2 = 3;
    if (r1 != r2 || c1 != c2) {
        cout << "Error: Matrices must have the same dimensions for subtraction." << endl;
        return 1; 
    }

    int m1[r1][c1], m2[r2][c2], difference[r1][c1];

    cout << "Enter elements of the first matrix:" << endl;
    for (int i = 0; i < r1; ++i) {
        for (int j = 0; j < c1; ++j) {
            cout << "Enter element at position (" << i << ", " << j << "): ";
            cin >> m1[i][j];
        }
    }
    cout << "Enter elements of the second matrix:" << endl;
    for (int i = 0; i < r2; ++i) {
        for (int j = 0; j < c2; ++j) {
            cout << "Enter element at position (" << i << ", " << j << "): ";
            cin >> m2[i][j];
        }
    }
    for (int i = 0; i < r1; ++i) {
        for (int j = 0; j < c1; ++j) {
            difference[i][j] = m1[i][j] - m2[i][j];
        }
    }
    cout << "Difference of matrices:" << endl;
    for (int i = 0; i < r1; ++i) {
        for (int j = 0; j < c1; ++j) {
            cout << difference[i][j] << " ";
        }
        cout << endl;
    }

    return 0;
}
~~~

# Output: - 

<img width="529" alt="image" src="https://github.com/user-attachments/assets/eccfbbb7-2616-43bb-8b37-4c4bf1bd3f1d">

# 4. Multiplication of two matrices: 
~~~
//Name: Srihari Nair
//Prn: 23070123131
//Class: EnTC B-2
#include <iostream>
using namespace std;

int main() {
    int r1, c1, r2, c2;
    cout << "Enter rows and columns for the first matrix: ";
    cin >> r1 >> c1;
    cout << "Enter rows and columns for the second matrix: ";
    cin >> r2 >> c2;
    if (c1 != r2) {
        cout << "Matrix multiplication not possible!" << endl;
        return 0;
    }
    int m1[r1][c1], m2[r2][c2], result[r1][c2];
    cout << "Enter elements of the first matrix:" << endl;
    for (int i = 0; i < r1; ++i) {
        for (int j = 0; j < c1; ++j) {
            cout << "Enter element at position (" << i << ", " << j << "): ";
            cin >> m1[i][j];
        }
    }
    cout << "Enter elements of the second matrix:" << endl;
    for (int i = 0; i < r2; ++i) {
        for (int j = 0; j < c2; ++j) {
            cout << "Enter element at position (" << i << ", " << j << "): ";
            cin >> m2[i][j];
        }
    } 
    for (int i = 0; i < r1; i++) {
        for (int j = 0; j < c2; j++) {
            result[i][j] = 0;
        }
    }
    for (int i = 0; i < r1; i++) {
        for (int j = 0; j < c2; j++) {
            for (int k = 0; k < c1; k++) {
                result[i][j] += m1[i][k] * m2[k][j];
            }
        }
    }
    cout << "Resultant matrix:\n";
    for (int i = 0; i < r1; i++) {
        for (int j = 0; j < c2; j++) {
            cout << result[i][j] << " ";
        }
        cout << endl;
    }

    return 0;
}
~~~

# Output: 

<img width="389" alt="image" src="https://github.com/user-attachments/assets/bcb17a72-3ba2-4aa7-a708-d8482031ae93">

# 5. Transpose of a matrix: 
~~~
//Name: Srihari Nair
//Prn: 23070123131
//Class: EnTC B-2
#include <iostream>
using namespace std;

int main() {
    int r, c ;
    cout << "Enter the number of rows and columns of the matrix: ";
    cin >> r  >> c ;
    int m[r][c], transpose[c][r];
    cout << "Enter elements of the first matrix:" << endl;
    for (int i = 0; i < r; ++i) {
        for (int j = 0; j < c; ++j) {
            cout << "Enter element at position (" << i << ", " << j << "): ";
            cin >> m[i][j];
        }
    }
    for(int i = 0; i < r; ++i) {
        for(int j = 0; j < c; ++j) {
            transpose[j][i] = m[i][j];
        }
    }
    cout << "\nTranspose of the matrix:" << endl;
    for(int i = 0; i < c; ++i) {
        for(int j = 0; j < r; ++j) {
            cout << transpose[i][j] << " ";
        }
        cout << endl;
    }
    return 0;
}
~~~

# Output:  

<img width="431" alt="image" src="https://github.com/user-attachments/assets/fb63433c-0c99-4dfa-b1c0-77a47536868d">

# 6. Diagnol addition of a matrix: 
~~~
//Name: Srihari Nair
//Prn: 23070123131
//Class: EnTC B-2
#include <iostream>
using namespace std;

const int MAX = 100;
void printDiagonalSums(int mat[][MAX], int n) 
{ 
    int principal = 0;
    for (int i = 0; i < n; i++)  
    { 
        // Condition for principal diagonal 
        principal += mat[i][i]; 
    } 
    cout << "Sum of the diagonal elements is: " << principal << endl; 
} 
int main() 
{ 
    int a[][MAX] = {{1, 2, 3, 4},  
                    {5, 6, 7, 8},  
                    {1, 2, 3, 4},  
                    {5, 6, 7, 8}}; 
    printDiagonalSums(a, 4); 
return 0;
}
~~~

# Output: 

<img width="403" alt="image" src="https://github.com/user-attachments/assets/31863fba-5515-4ccd-ae53-ed3eff183ea0">

# CONCLUSION: 
This experiment provides valuable insight into fundamental concepts in programming, particularly in handling data structures that require multi-dimensional organization. Through this process, we gain a deeper understanding of how to: <br>
* Efficiently Store and Manipulate Data: Using 2D arrays, we can efficiently store data in a tabular format, making it easier to perform operations like addition, subtraction, and multiplication of matrices.
* Develop Problem-Solving Skills: Implementing matrix operations enhances logical thinking and problem-solving skills, as it requires careful consideration of indices, loops, and data handling.
* Understand Memory Management: Working with 2D arrays in C++ also provides an understanding of how memory is allocated and accessed in programming, especially in managing rows and columns of data.
* Apply Concepts in Real-World Scenarios: Matrix operations are fundamental in various fields such as engineering, computer graphics, machine learning, and scientific computing. Understanding how to implement these in C++ prepares us to tackle more complex problems in these domains.
