Архітектури обчислювальних систем | Проект: варіант 1 | Колесник Іван КН-4


Частина перша (мова високого рівня)


Постановка задачі
Прочитати з stdin N рядків до появи EOF (макс довжина рядка 255 символів,максимум 100 рядків), у масив з рядків. Рядки розділяються АБО послідовністю байтів 0x0D та 0x0A (CR LF), або одним символом - 0x0D чи 0x0A.
Як зберігати рядки, неважливо (ASCIIZ або Pascal string або якось ще). Або не зберігати взагалі, якщо робити наступний крок line-by-line.
Знайти всі входження вказанного підрядка (1й аргумент командного рядка) в кожному з рядків. Може бути більше одного входження на рядок.
Входження не мають перетинатися, наприклад кількість входжень підрядка "aa" в "aaa" = 1.
Відсортувати знайдені результати алгоритмом bubble sort (якщо merge sort - буде додатковий бал) по кількості входженнь (asc), та вивести в консоль (stdout) 
"<кількість входжень> <індекс рядка у текстовому файлі починаючи з 0>".
Наприклад (виклик програми із параметром aa):

aaaaa bbaa
aaz a
Результат:

1 1
3 0

Хід роботи 

Програма включає дві основні функції:

bubbleSort(arr): Ця функція сортує масив за допомогою алгоритму сортування бульбашкою.
countSubstringOccurrences(substring, string): Ця функція рахує кількість входжень підстрічки в рядок.
Скрипт спочатку створює інтерфейс для зчитування введення користувача за допомогою модуля readline, а потім, коли введення закінчиться (close event), він обробляє кожен рядок, знаходить кількість входжень заданої підстрічки та індекси рядків, у яких вона зустрілася. Потім ці пари кількостей індексів сортуються за кількістю входжень, і виводяться на консоль.

Частина друга (мова низького рівня)

Як реалізувати

Підпрограма, що виводить в stdout десяткове число 

Структури даних

Один буфер для читання з stdin, який накопичує символи одного рядка, в якому будемо шукати входження підрядка. 
це може бути або один масив структур, що складаються з двох слів (індекс_рядку, кількість_входжень)
або можна зробити 2 масиви з слів, один для значень індексів рядків, інший для кількості входжень
