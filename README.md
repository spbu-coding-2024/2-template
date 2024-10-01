# Задача 2

Реализовать приложение, которое позволяет запустить его из командной строки с параметрами вида *\-\-from=<параметр>* и *\-\-to=<параметр>* и отсортировать поступающий на вход в стандартный поток ввода набор целых чисел (не более 100 штук, это гарантируется).
Числа разделены пробелами, последним символом является перенос строки.

Если было введено менее одного параметра, приложение должно вернуть код возврата **-1**, если более двух — код **-2**.
Если один и тот же параметр введён более одного раза — код **-3**.
Выражения `--from=`, `--to=`, `--from=<не число>`, `--to=<не число>` следует трактовать как `--from=0` и `--to=0` соответственно, `--from=n<не число>`, `--to=n<не число>` равносильно `--from=n` и `--to=n`.
При наличии хотя бы одного корректного параметра выполнить работу приложения, используя этот параметр.
При наличии двух некорректных параметров вернуть код ошибки **-4**.

При этом в случае наличия первой специальной инструкции в сортировке участвуют лишь числа, строго большие параметра, а остальные, разделённые пробелами, выводятся в стандартный поток вывода.
В случае наличия второй инструкции в сортировке участвуют лишь числа строго меньше, а остальные, разделённые пробелами, выводятся в стандартный поток ошибок.

Процедура сортировки должна быть реализована на языке ассемблера *достаточно оптимальным образом*.
**Кодом возврата** приложения является количество элементов, участвовавших в сортировке и изменивших свою позицию.

#### Пример 1:
- *Args:* `--from=3`
- *Input:* `2 4 1 5 8 4`
- *Stdout:* `2 1`
- *Stderr:*
- *Exit code:* `3`
- (*Reduced:* `4` `5` `8` `4`, *Sorted:* `4` `4` `5` `8`)

#### Пример 2:
- *Args:* `--to=9 --from=3`
- *Input:* `4 7 10 5 1 6 8`
- *Stdout:* `1`
- *Stderr:* `10`
- *Exit code:* `3`
- (*Reduced:* `4` `7` `5` `6` `8`, *Sorted:* `4` `5` `6` `7` `8`)

#### Пример 3:
- *Args:* `--to=9 --from=3 --anotherOne`
- *Exit code:* `-2`
- (Приложение возвращает код возврата `-2`, больше ничего не делает)

### Дополнительные соглашения:
- В случае использования глобальных переменных в какой-либо функции их нужно явно инициализировать в ней, иначе возможна непредвиденная работа тестов. Но лучше их просто не использовать.
- Чтение поступающих на вход сортируемых элементов необходимо производить с помощью команды *scanf(...)*.
- Вывод данных в стандартный поток вывода осуществлять функцией *printf(...)* или *fprintf(stdout, ...)*, вывод с стандартный поток ошибок осуществлять функцией *fprintf(stderr, ...)*.
- Файлы с кодом приложения должен иметь расширение `.c`, файл с реализацией сортировки на ассемблере должен иметь расширение `.s`

### Работа с GitHub:
- Работа с Git и GitHub аналогична задаче 1 
- [Ссылка на тестирующую систему](https://github.com/spbu-coding-2024/2-grading-system) 
