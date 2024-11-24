# Fuzzing_Lab
# Задание №1.
Произведём контрольное суммирование исполняемого файла выбранного проекта. Для этого скомпилируем его, получим файл main. Воспользуемся хэш-функцией md5 для того, чтобы взять контрольную сумму.
![изображение](https://github.com/user-attachments/assets/c04df6d7-27a1-4fe0-ac40-eb8d79cba5fe)
# Задание №2.
Выполним фаззинг-тестирование с обратной связью. Для этого воспользуемся командой git clone и скачаем проект AFLplusplus. Соберём его командой make.Скачаем выбранный для фаззинга проект https://github.com/p-ranav/csv2/tree/master csv2. В качестве точки входа будем использовать предложенный как пример в проекте файл benchmark/main.cpp, настроим соответствующим образом CMakeLists.txt. После соберём код с подменёнными компиляторами и вставим датчики, выполним make. После можно приступать к фаззингу.
![изображение](https://github.com/user-attachments/assets/733fc255-d852-413d-87c4-ddca05c7cc2a)
![изображение](https://github.com/user-attachments/assets/10de0363-c807-40d6-aa36-c167b87019a6)
В качестве входного корпуса возьмём небольшой csv-файл.
![изображение](https://github.com/user-attachments/assets/4d82ee0c-4b81-4937-a51f-85d6fc0c84b1)
Отметим, что большая скорость выполнения фаззинга связана с малым объёмом самого исполняемого файла main.cpp.
Рассмотрим результаты фаззинга.
![изображение](https://github.com/user-attachments/assets/cc41aeb7-aefa-443e-a811-8addb9e99dba)
Здесь представлены мутации исходного корпуса. Как пример мутации возьмём случайный корпус из каталога out.
![изображение](https://github.com/user-attachments/assets/d937edd7-ac45-4ccc-97da-745769e5e17c)
![изображение](https://github.com/user-attachments/assets/976bdefa-9535-4fac-8883-705876f5ee63)
Ниже представлены общие параметры проведённого процесса.
![изображение](https://github.com/user-attachments/assets/f7606f0a-f5c3-4654-a45f-5f882c8bf4b8)
![изображение](https://github.com/user-attachments/assets/1a3e946b-6a02-456a-871d-7f003982deae)
Затем попробуем минимизировать количество корпусов.
![изображение](https://github.com/user-attachments/assets/31fa31e3-5d4e-4b61-80b6-02b7af9fe1bf)
# Задание №3.
Выполним проверку покрытия кода. Для этого пересоберём проект с использованием g++ --coverage.
![изображение](https://github.com/user-attachments/assets/72aa3cae-6f86-42be-bc33-d225b1e50b09)
После чего пройдёмся по корпусам для создания покрытия и с помощью lcov создадим отчёт о покрытии.
![изображение](https://github.com/user-attachments/assets/0163ff53-12d1-4368-b013-4930409d141e)













