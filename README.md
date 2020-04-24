# Game-Dev-TC-modul-2
Modul 2 Komunitas Game Dev TC 2020

## Tujuan
1. Peserta memahami konsep Pemrograman Berorientasi Objek
2. Peserta dapat mengimplementasi Pemrograman Berorientasi Objek
3. Peserta dapat memahami bahasa C#
4. Peserta dapat menggunakan bahasa C#

## Apa itu Pemrograman Berorientasi Objek ?
Pemrograman berorientasi objek adalah teknik pemrograman dimana setiap fungsi dan data akan dikelompokkan. Tujuan dari pemrograman ini, adalah untuk mengurangi *code duplication* dan *dependency* yang merupakan kekurangan *procedural programming*.
Dalam *procedural programming*, akan disediakan fitur seperti variabel dan fungsi. Namun, fungsi dan variabel ini dapat diakses di semua scopenya. Jadi kita tidak bisa menyembunyikan variabel atau fungsi. Ini sangat tidak praktis, jika ada project besar dengan ratusan variabel dimana semua variabel dapat diakses dimanapun. Ini adalah permasalahan yang ingin diselesaikan oleh *object oriented programming*.
Dengan *object oriented programming*, kita dapat mengelompokkan fungsi dan variabel ini sesuai dengan yang membutuhkan mereka.
Liat contoh *procedural programming* berikut :
```
#include <stdio.h>

void Move(int * x, int * y, int deltaX, int deltaY){
    *x+=deltaX;
    *y+=deltaY;
}

int main(){
    int playerX, playerY;
    int playerHealth = 10;
    int enemyX, enemyY;
    int enemyHealth = 10;
    ...
    
}
```
Bandingkan dengan contoh *object oriented programming* berikut :
```
class Player {
    private int x, int y;
    private int health;

    public void Move(int deltaX, int deltaY){
        x+=deltaX;
        y+=deltaY;
    }
}

class Main{
    public static void main(String[] args){
        Player player = new Player();
        player.Move(1, 1);
        ...
    }
}
```
## 4 Prinsip dalam Pemrograman Berorientasi Objek
Pemrograman berorientasi objek mempunyai 4 prinsip, yaitu *Encapsulation*, *Abstraction*, *Inheritance*, dan *Polymorphism*. Setiap bahasa pemrograman berorientasi objek harus mensupport 4 prinsip tersebut.

### Encapsulation
### Abstraction
### Inheritance
### Polymorphism

## C#

### Data hiding

### class vs struct

### Interface vs abstract class

### Reference

### Mengenal IEnumerable dan IEnumerator



Sumber : 
https://medium.com/from-the-scratch/oop-everything-you-need-to-know-about-object-oriented-programming-aee3c18e281b
https://livebook.manning.com/book/c-sharp-in-depth-fourth-edition/chapter-2/367