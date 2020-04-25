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
    Move(&playerX, &playerY, 1, 1);
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
*Encapsulation* adalah mekanisme untuk *membungkus* variabel dan fungsi yang mempunyai tujuan atau tanggung jawab yang sama. Dengan ini, beberapa variabel atau fungsi dapat *dilindungi* dari luar. Perlindungan ini, membuat kita mengurangi dependency antar class.
Hanya beberapa fungsi atau variabel saja yang dapat diakses dari luar memudahkan untuk refactor code atau memperbaiki suatu fitur. Dengan beberapa fungsi yang tersembunyi ini, bisa diubah tanpa merusak keseluruhan program karena fungsi fungsi tersebut hanya dipanggil di *scope* class saja.
Contoh kode tidak menerapkan *encapsulation* :
```
#include <stdio.h>

void Attack(int attack, int * opponentHP){
    *oponentHP -= attack;
}

int main(){
    ...
    int playerAttack = 5;
    int playerBuff = 1;
    int enemyArmour = 2;
    int enemyHealth = 10;
    Attack(playerAttack+playerBuff-enemyArmour, &enemyHealth);
    ...
    
}
```
Contoh kode menerapkan *encapsulation* :
```
class Enemy{
    ...
    private int health = 10;
    private int armour = 4;

    public void Damaged(int ap){
        health -= ap-armour;
    }
}

class Player{
    ...
    private int attackPoint = 4;
    private int attackBuff = 2;

    public void Attack(Enemy enemy){
        enemy.Damaged(attackPoint + attackBuff);
    }
}

public class Main{
    public static void main(String[] args){
        Player player = new Player();
        Enemy enemy = new Enemy();
        player.Attack(enemy);
    }
}
```

### Abstraction
*Abstraction* adalah proses untuk menyembunyikan implementasi suatu fungsi, namun tetap memberikan fungsionalitas ke user. Dengan ini, programmer tidak perlu mengetahui cara kerja fungsi tersebut, hanya perlu tahu apa fungsi dari fungsi tersebut.
Dalam *object oriented programming* sangat dianjurkan implementasi itu di implementasikan di class namun di definisikan di abstract class atau interface. Abstraksi sangat diperlukan untuk mengurangi detail yang perlu diketahui user.
Contoh dalam mobil, ada pedal gas dan rem. Kita tidak mempedulikan bagaimana mobil menggerakkan mesinnya, tapi kita hanya peduli bahwa pedal gas kalau ditekan akan menggerakkan mobil kedepan.
Contoh kode yang tidak mengimplementasi *abstraction* :
```
class Enemy{
    ...
    public int health = 10;
    public int armour = 4;

    public void Die(){
        ...
    }
}

class Player{
    ...
    private int attackPoint = 4;
    private int attackBuff = 2;

    public void Attack(Enemy enemy){
        enemy.health -= attackPoint + attackBuff - enemy.armour;
        if(enemy.health < 0){
            enemy.Die();
        }
    }
}

public class Main{
    public static void main(String[] args){
        Player player = new Player();
        Enemy enemy = new Enemy();
        player.Attack(enemy);
    }
}
```
contoh kode yang mengimplementasi *abstraction* :
```
class Enemy{
    ...
    private int health = 10;
    private int armour = 4;

    public void Damaged(int ap){
        health -= ap-armour;
        if(health < 0){
            Die();
        }
    }

    private void Die(){
        ...
    }
}

class Player{
    ...
    private int attackPoint = 4;
    private int attackBuff = 2;

    public void Attack(Enemy enemy){
        enemy.Damaged(getAttackPoint());
    }

    private int getAttackPoint(){
        return attackPoint + attackBuff;
    }
}

public class Main{
    public static void main(String[] args){
        Player player = new Player();
        Enemy enemy = new Enemy();
        player.Attack(enemy);
    }
}
```
### Inheritance
*Inheritance* adalah saat dimana satu class mendapatkan properti atau fungsi dari class parent atau class yang diturunkan. Konsep *inheritance* adalah seperti kucing dan anjing adalah mamalia. Dimana semua mamalia akan menyusui dan bernapas dengan paru-paru. Jika kucing dan anjing tidak *inherit* mamalia, maka kita harus menulis ulang fungsi-fungsi yang sama tadi.
Jadi tujuan utama inheritance adalah mengurangi *code duplication*. Akan tetapi dengan adanya inheritance harus dipahami juga bahwa akan ada dependency antara child class dan parent class. Jadi inheritance harus d
### Polymorphism


## C#

### class vs struct

### Object

### Data hiding

### Interface vs abstract class

### Reference

### Mengenal IEnumerable dan IEnumerator



Sumber : 
https://medium.com/from-the-scratch/oop-everything-you-need-to-know-about-object-oriented-programming-aee3c18e281b
https://livebook.manning.com/book/c-sharp-in-depth-fourth-edition/chapter-2/367