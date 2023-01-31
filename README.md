package org.example;

public class JvmComprehension {

    public static void main(String[] args) {
        int i = 1;                      // 1 после вызова метода мэйн созджается переменная i со значением установленной в строке = 1
        Object o = new Object();        // 2 В фрейм мэйна создается переменная о с ссылкой, а в хипе создаётся Object
        Integer ii = 2;                 // 3 В хипе создаётся Integer со значением 2, а в фрейме мэйна создается переменная ii с ссылкой
        printAll(o, i, ii);             // 4 В стаке создается новый фрейм printALL и в него записываются переменные, описанные выше.
        System.out.println("finished"); // 7 В стаке создаётся фрейм для println, куда передаются ссылки на созданные в хипе стринг с текстовым значением "finished"
    }

    private static void printAll(Object o, int i, Integer ii) {
        Integer uselessVar = 700;                   // 5 В хипе создается Integer со значением 700, а во фрейме printAll переменная uselessVar
        System.out.println(o.toString() + i + ii);  // 6 В стаке создается println, куда направляются все ссылки переменных из фреймов мэйна, т.е. Object o, int i, Integer ii, затем это всё стрингуется через фрейм toString.
    }
}