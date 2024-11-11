# Laba1
package Laboratory;

import java.util.Scanner;

public class fs {
    public static int Random() {
        return (int) (Math.random() * 15);
    }

    public static int[] RandomArray() {
        int[] array = new int[Random()];
        for (int i = 0; i < array.length; i++) {
            array[i] = Random();
        }
        return array;
    }
    public static void arrayOutput(int[] array) {
        System.out.println("Ваш массив: ");
        for (int i = 0; i < array.length; i++)
            System.out.print(array[i] + " ");
        System.out.println();
    }

    public static int[] enteringAnArray() {
        Scanner scan = new Scanner(System.in);
        System.out.print("Введите длину массива: ");
        int[] array = new int[scan.nextInt()];
        System.out.println("Введите элементы массива: ");
        for (int i = 0; i < array.length; i++) {
            array[i] = scan.nextInt();
        }
        return array;
    }
    public static int tenth(int[] array) {
        int sum = 0;
        for (int i = 0; i < array.length; i++) {
            sum += array[i];
        }
        return sum;
    }

    public static int evenElements(int[] array) {
        int count = 0;
        for (int i = 0; i < array.length; i++) {
            if (array[i] % 2 == 0) {
                count++;
            }
        }
        return count;
    }

    public static int intervals(int[] array, int a, int b) {
        int count = 0;
        for (int i = 0; i < array.length; i++) {
            if (array[i] <= b && array[i] >= a) {
                count++;
            }
        }
        return count;
    }

    public static boolean positivElem(int[] array) {
        for (int item : array) {
            if (item <= 0) {
                return false;
            }
        }
        return true;
    }

    public static int[] reverseElem(int[] array) {
        int buffer;
        for (int i = 0; i < array.length / 2; i++) {
            buffer = array[i];
            array[i] = array[array.length - 1 - i];
            array[array.length - 1 - i] = buffer;
        }
        return array;
    }

    public static int choice() {
        Scanner scan = new Scanner(System.in);
        System.out.println("Введите номер задания: ");
        return scan.nextInt();
    }

    public static void main_old(String[] args) {
        switch (choice()) {
            case 8:
                arrayOutput(RandomArray());
                break;
            case 9:
                arrayOutput(enteringAnArray());
                break;
            case 10:
                System.out.println("Длина массива: " + tenth(enteringAnArray()));
                break;
            case 11:
                System.out.println("Количество четных чисел в массиве: " +  evenElements(enteringAnArray()));
                break;
            case 12:
                int[] array = {1, 3, 4, 5, 8};
                int[] array1 = {0, -1, 3, 7, -8};
                System.out.println("Количество элементов в массиве, принадлежащих указонному отрезку: " +  intervals(array, 0, 4));
                System.out.println("Количество элементов в массиве, принадлежащих указонному отрезку: " +  intervals(array1, 0, 4));
                System.out.println("Количество элементов в массиве, принадлежащих указонному отрезку: " +  intervals(enteringAnArray(), 0, 4));
                break;
            case 13:
                System.out.println("Положительны ли элементы массива? Ответ: " + positivElem(enteringAnArray()));
                break;
            case 14:
                arrayOutput(reverseElem(enteringAnArray()));
                break;

        }
    }
}
