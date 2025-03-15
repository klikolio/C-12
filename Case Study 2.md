---
title: 'Case Study II - Function'

---

# Case Study II - Function

> Pembuat Soal: GI

```bash
Nama    : Tinasha
NPM     : 2312345678
```

## Deskripsi Soal

Ketertarikan Oscar sekarang membuatnya ingin membuat sebuah fungsi rekursif. Dimana fungsi rekurisf adalah sebuah fungsi yang memanggil dirinya sendiri. Oscar meminta bantuan anda untuk membuat sebuah program untuk menghitung jumlah kuadrat dari bilangan non-negatif yang diberikan oleh user. Selain itu, Oscar tentu memberikan beberapa batasan dari program yang akan kalian buat nantinya, yaitu:

- Program pertama-tama akan meminta jumlah test case yang ingin diinputkan oleh user
- Selanjutnya, program akan meminta input lagi untuk berapa banyak bilangan yang ingin dihitung
- Program akan meminta lagi input berupa bilangan non-negatif yang ingin dihitung sejumlah yang telah ditentukan sebelumnya (point kedua)
- Program akan menghitung jumlah kuadrat dari bilangan non-negatif yang diberikan oleh user
- Untuk fungsi yang dibuat, **wajib** menggunakan fungsi rekursif
- Program hanya menerima input berupa bilangan bulat (integer) dan tidak menerima input berupa bilangan desimal (float) ataupun string

### Contoh Input dan Output

| Contoh | Contoh | Contoh | 
| --- | --- | --- |
| ![picture-1](http://cdn.digilabdte.com/u/SQYMKK.png) | ![picture-2](http://cdn.digilabdte.com/u/wxx37d.png) | ![picture-3](http://cdn.digilabdte.com/u/CMl16I.png) |

### Bantuan Penjelasan

#### Test Case 1

Terlihat pada gambar yang diberikan, seperti berikut

```bash
3 # Input jumlah test case
4 # Input jumlah bilangan yang ingin dihitung
-1 -2 3 4 # Input bilangan yang ingin dihitung
Output: 25 # Hasil dari 3^2 + 4^2 = 9 + 16 = 25
3 # Input jumlah bilangan yang ingin dihitung
1 2 -3 # Input bilangan yang ingin dihitung
Output: 5 # Hasil dari 1^2 + 2^2 = 1 + 4 = 5
5 # Input jumlah bilangan yang ingin dihitung
5 -5 6 -6 7 # Input bilangan yang ingin dihitung
Output: 110 # Hasil dari 5^2 + 6^2 + 7^2 = 25 + 36 + 49 = 110
```

#### Test Case 2

Terlihat pada gambar yang diberikan, seperti berikut

```bash
2 # Input jumlah test case
2 # Input jumlah bilangan yang ingin dihitung
-1 2 # Input bilangan yang ingin dihitung
Output: 4 # Hasil dari 2^2 = 4
4 # Input jumlah bilangan yang ingin dihitung
1 2 -3 4 # Input bilangan yang ingin dihitung 
Output: 21 # Hasil dari 1^2 + 2^2 + 4^2 = 1 + 4 + 16 = 21
```

## Jawaban

### Source Code

```c
#include <stdio.h>


int sum_of_squares(int arr[], int n) {
    if (n == 0) {
        return 0;
    }

    if (arr[n - 1] < 0) {
        return sum_of_squares(arr, n - 1);
    }

    return (arr[n - 1] * arr[n - 1]) + sum_of_squares(arr, n - 1);
}

int main() {
    int test_cases;
    scanf("%d", &test_cases);
    
    for (int t = 0; t < test_cases; t++) {
        int n;
        scanf("%d", &n);
        
        int numbers[n];
        for (int i = 0; i < n; i++) {
            scanf("%d", &numbers[i]);
        }
        
        int result = sum_of_squares(numbers, n);
        printf("Output: %d\n", result);
    }
    
    return 0;
}
```

### Screenshot Program Perjalan


> Test case yang digunakan adalah test case yang sama dengan contoh input dan output yang diberikan

| Input//Output |
| --- |
| ![Test Case 1](https://raw.githubusercontent.com/klikolio/C-12/refs/heads/main/test-1.png) |
| ![Test Case 2](https://raw.githubusercontent.com/klikolio/C-12/refs/heads/main/test-2.png) |
