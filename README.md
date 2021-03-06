# python_exam
Вам нужно написать обработчик файлов внутри директории (вложенность может быть сколь угодно большой). В файлах хранятся результаты иследований (первая строка header, далее в каждой строке набор имен и последовательность которую ученые открыли). Пример файла:

```
Names	Seq
Marina Bulusova	Alina Tarnakina	Arkadiy Verdiev	Mariya Teryshkova	CCCACTCCTAGGAACGGTTACGTCAGCGCTGTCAGTGCCGCATTT
```

Считать нужно все файлы, у которых выполнены условия (для этого нужно создать менеджер контекста, который принимает на вход путь к директории и будет возвращать подходящие файлы).
Пример:
```
with file_names as DirReader("dir"):
    ...
```

Условие для чтения файла - файл оканчивается на .txt.
Внутри файлов хранится информация по ученым, которые открыли новую последовательность. По этим данным постройте граф, 
в котором вершина - это имя ученого, а ребро будем проводить в случае, если два ученых открыли хотя бы одну последовательность.

Постройте итератор по кликам по полученному графу.

Пример
```
for сlique in GraphIterator(G):
    ...
```
    
Реализуйте декоратор print_iter для GraphIterator с аргументом для задания имени файла (по умолчанию 'result.txt'), 
который будет записывать имена ученых в файл во время итерирования по кликам.

```
@print_iter
class GraphIterator:
    ...
```

Задание нужно оформить в гит репозитории, с настроенным CI и тестированием. Основную сложность в данной задаче составляет покрытие тестами (созадние временных директорий с даннами под тест).
