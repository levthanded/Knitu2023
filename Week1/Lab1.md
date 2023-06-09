# Лабораторная 1 - Рост популяции

>Вы можете сотрудничать с одним или двумя одногруппниками в этой лабораторной работе, хотя ожидается, что каждый студент в любой такой группе вносит равный вклад в лабораторную работу.

\- **Задача - определите, сколько времени требуется, чтобы популяция достигла определенного размера.**

```
$ ./population
Start size: 100
End size: 200
Years: 9
```

--------------

## Условия Задачи

Скажем, у нас есть популяция лам. Каждый год рождается `n / 3` новых лам, а `n / 4` лам умирает.

Например, если бы мы начали с `n = 1200` лам, то в первый год родились бы `1200/3 = 400` новые ламы, а `1200/4 = 300` лам умерли бы. В конце этого года у нас будет `1200 + 400 - 300 = 1300` лам.
.

Другой пример: если бы мы начали с `n = 1000` лам, то в конце года у нас было бы `1000 / 3 = 333,33` новых ламы. Однако у нас не может быть десятичной части ламы, поэтому мы усекаем десятичную часть, чтобы родилось `333` новых ламы.
`1000 / 4 = 250` лам умрут, так что в итоге мы получим `1000 + 333 - 250 = 1083` ламы на конец года.

-----

## За Работу!

Напоминаю, что **Visual Studio Code** (он же **VS Code**) — это популярная «интегрированная среда разработки» (**IDE**), с помощью которой вы можете писать код. Чтобы вам не приходилось загружать, устанавливать и настраивать собственную копию VS Code, вместо этого мы будем использовать облачную версию, в которой предварительно установлено все необходимое.

1. 1. Войдите в [code.cs50.io](https://code.cs50.io/), используя свою учетную запись GitHub, и следуйте инструкциям на экране, чтобы настроить собственную «среду разработки» для Visual Studio Code. Как только ваша среда разработки загрузится (окна прогружаются постепенно, не пугайтесь, терпение), вы должны увидеть, что по умолчанию VS Code разделен на три области. В верхней части VS Code находится ваш «текстовый редактор», где вы будете писать все свои программы. Внизу находится «окно терминала», интерфейс командной строки (CLI), который позволяет вам просматривать файлы и каталоги вашего пространства кода (или папки), компилировать код и запускать программы. А слева ваш файл «проводник» графический пользовательский интерфейс (GUI), с помощью которого вы также можете исследовать файлы и каталоги вашего кодового пространства.
2. После загрузки пространства кода закройте все вкладки **Добро пожаловать** , которые могли открываться по умолчанию.
3. Запустите `update50` в окне терминала вашего пространства кода, чтобы убедиться, что ваше пространство кода обновлено, и, если будет предложено, нажмите **Перестроить сейчас**.

После завершения начните с нажатия внутри окна терминала, а затем запустите cd самостоятельно. Вы должны обнаружить, что его «подсказка» похожа на приведенную ниже.

```
$
```

Щелкните внутри этого окна терминала, а затем введите

```
mkdir population
```

а затем нажмите Enter, чтобы создать каталог под названием «население» в вашем кодовом пространстве. Будьте осторожны, чтобы не упустить пробел между `mkdir` и `population` или любым другим символом в этом отношении!

Здесь, чтобы выполнить (т. Е. Запустить) команду, нужно ввести ее в окно терминала, а затем нажать Enter. Команды чувствительны к регистру,
поэтому убедитесь, что вы не печатаете в верхнем регистре, когда вы имеете в виду строчные или наоборот.

Теперь выполните

```
cd population
```

чтобы переместиться в (т.е. открыть) этот каталог. Теперь ваша строка ввода должна выглядеть так, как показано ниже.

```
population/ $
```

Щелкните внутри этого окна терминала, а затем введите

```
wget https://raw.githubusercontent.com/levthanded/Knitu2023/main/Week1/src/population.c
```

затем нажмите Enter, чтобы загрузить файл шаблона с именем `population.c` в ваше кодовое пространство. Будьте осторожны, не упускайте из виду пробел между `wget` и следующим URL-адресом или любой другой символ в этом отношении! Если все прошло успешно, вы должны выполнить

```
ls
```

и увидеть файл с именем `population.c`. Выполнение кода `population.c` должно открыть файл, в котором вы будете вводить код для этой лабораторной работы. Если нет, повторите свои шаги и посмотрите, сможете ли вы определить, где вы ошиблись!

---------

## Детали Реализации

Завершите реализацию `population.c`, чтобы он вычислил количество лет, необходимое для роста населения от начального размера до конечного размера.

- Ваша программа должна сначала запросить у пользователя начальный размер популяции.
    - Если пользователь вводит число меньше 9 (минимально допустимая численность населения), пользователю должно быть повторно предложено ввести начальный размер популяции, пока он не введет число, которое больше или равно 9. (Если мы начнем с менее чем 9 лам, популяция лам быстро станет неизменной!)
- Затем ваша программа должна запрашивать у пользователя конечный размер популяции.
    - Если пользователь вводит число, меньшее, чем начальный размер совокупности, пользователю следует повторно предлагать ввести конечный размер совокупности до тех пор, пока он не введет число, которое больше или равно начальному размеру совокупности. (Ведь мы хотим, чтобы популяция лам росла!)
- Затем ваша программа должна вычислить (целое) количество лет, необходимое для того, чтобы население достигло по крайней мере размера конечного значения.
- Наконец, ваша программа должна вывести количество лет, необходимое для того, чтобы популяция лам достигла конечного размера, например, выводя на терминал `Годы: n`, где `n` – количество лет.

-----

### [Видеоразбор]

>Видео с подробным пошаговым решением будет здесь уже совсем скоро.

----

### Советы По Решению

- Если вы хотите повторно запрашивать у пользователя значение переменной до тех пор, пока не будет выполнено какое-либо условие, вы можете использовать цикл `do ... while` . Например, вспомните следующий код из лекции, который неоднократно запрашивает пользователя, пока он не введет положительное целое число.
  
    ```
      int n;
      do
      {
          n = get_int("Положительное целое число: ");
      }
      while (n < 1);
    ```
    > Как можно адаптировать этот код, чтобы обеспечить начальный размер не менее 9 и конечный размер не менее начального размера?

- Чтобы объявить новую переменную, обязательно укажите ее тип данных, имя переменной и (необязательно) ее начальное значение.
	-   Например, вы можете создать переменную, чтобы отслеживать, сколько лет прошло.
   
- Чтобы рассчитать, сколько лет потребуется, чтобы популяция достигла конечного размера, может оказаться полезным еще один цикл! Внутри цикла вы, вероятно, захотите обновить размер популяции в соответствии с формулой в фоновом режиме, и обновить количество прошедших лет.

-   Чтобы вывести целое число `n` на терминал, вспомните, что вы можете использовать такую строку кода
    ```
    printf("Моё число это %i\n", n);
    ```
    чтобы указать, что переменная `n` должна заполнять заполнитель `%i`.

----

### Как Протестировать Свой Код

Ваша программа должна вести себя в соответствии с приведенными ниже примерами.

```
$ ./population
Start size: 1200
End size: 1300
Years: 1
```

```
$ ./population
Start size: -5
Start size: 3
Start size: 9
End size: 5
End size: 18
Years: 8
```

```
$ ./population
Start size: 20
End size: 1
End size: 10
End size: 100
Years: 20
```

```
$ ./population
Start size: 100
End size: 1000000
Years: 115
```

------

## Как Сдавать Работу

В ближайшее время мы синхронизируем ваши GitHub аккаунты со списком студентов, и научимся отправлять задания прямо туда. А пока что просто присылайте готовый код файлом `population.c` в личку [Льву в Тг](https://t.me/levthanded), скачать файл вы можете щелкнув правой кнопкой мыши по файлу в проводнике.

>![Скачивание файла](https://github.com/levthanded/Knitu2023/blob/main/Week1/src/img-1.png)

### Удачи!
