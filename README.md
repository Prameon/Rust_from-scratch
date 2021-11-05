# Rust - Язык Програмирования.
*"Язык, позволяющий каждому создавать надёжное и эффективное программное обеспечение"*

Полезные ссылки:
- [Оффициальный Сайт](https://www.rust-lang.org/ru/)
- [Github](https://github.com/rust-lang/rust) 
- [Docs.rs](https://docs.rs/) 
- [Std](https://doc.rust-lang.org/std/) 
- [Crates.io](https://crates.io/)
- [Коды ошибок](https://doc.rust-lang.org/error-index.html)
---
## Установка Rust.
- [Инструкция](https://www.rust-lang.org/ru/tools/install)
- [или Инструкция на doc.rust-lang.ru](https://doc.rust-lang.ru/book/ch01-01-installation.html)

Oбновить Rust:
 ```
 $  rustup update
 ```
---
Учебники:

- [Rust book](https://doc.rust-lang.org/book/)
- [Rust book - на русском](https://doc.rust-lang.ru/book/)
- [Rust by Example](https://doc.rust-lang.org/stable/rust-by-example/)
- [Rust by Example - на русском](https://doc.rust-lang.ru/stable/rust-by-example/)

- [Тур по Rust](https://tourofrust.com/00_ru.html)
- [Учебник Roguelike - In Rust ](https://bfnightly.bracketproductions.com/chapter_0.html)
# Глава 1. Первый проект.
## Создать и запустить проект с помощью Cargo.
__Cargo__ является системой сборки и менеджером пакетов в Rust.
***
__Терминал(powershell):__
```
$ cargo new name
$ cd name
$ cargo run
( $ cargo build ) 
```
Вывод терминала:
```  
Hello, world!
```
Файлы проекта:
 - name \ src \ main.rs (вход в программу, вы пишете код приложения)
 - name \ Cargo.toml (для подлючения стороних библиотек)
***


### Cоздаем первый проект __name__.

__1. Для создания проекта нужно воспользоваться териминалом.__
```cargo 
$ cargo new name
```
*где __name__ назване вашего проекта.
(также я нахожусь в папке C:\Coding\Rust\)*

```cargo
далее нужно перейти в каталог name:
$ cd name

(вернутся назад)
$ cd..
```
2. Запустить проект команда в каталоге проекта.
```cargo 
$ cargo run
```
или так, но запустить в ручную файл name.exe. 

В папке:
...\name\target\debug\name.exe
```cargo 
$ cargo build 
```

### Выводит:
```cargo  
$ cargo run     
   Compiling name v0.1.0 (C:\Coding\Rust\name)
    Finished dev [unoptimized + debuginfo] target(s) in 1.22s
     Running `target\debug\name.exe`
Hello, world!
```
Вывод в консоли:
```  
Hello, world!
```
### Проект name.
Разберем проект который мы создали с выше.
- папка __\src__ (с нашим кодом)
- Cargo.toml (для подлючения стороних библиотек)


файл src\main.rs
```rust
fn main() {
    println!("Hello, world!"); 
}
// fn main(){} вход в программу
// println!("") макрос для печати текста
// Hello, world! текст для печати.
// ;
``` 

файл Cargo.toml
```toml  
[package]
name = "name" 
version = "0.1.0" 
edition = "2021" 

#Смотрите больше ключей и их определений на https://doc.rust-lang.org/cargo/reference/manifest.html

[dependencies]
# ниже добовляются стороние библиотеки 
```
`edition = "2021"` - указывает год выпуска стадильной версии Rust, которую я сейчас использую.

Выводы:

- Мы создали проект
- запустили проект. . . и посмотрели что выводит.
- посморели файлы которые были созданы.   

## Вход в программу `fn main()`
`fn main()` - Это главная функция с которой происходи запуск программы.

файл src\main.rs
```rust
fn main() {

}
``` 
В это функции мы пишем код. а точней мы пишим в фигурных скобках `{..}`, это тело функции. 

`{}` после того как программа дойдет до закрытия скобок, она выполнится полностью и закроется, а также данные которые находятся в теле функции  будут очищены.

## Вывод в консоль.`println!("Вывод в консоль:{}", x);`
В данном случае наша программа ничего не делает, но при создании проекта с помощью cargo. Мы получаем код который выводить в консоли текст "Hello, world!".
```rust
fn main() {
    println!("Hello, world!"); 
}
``` 
имено с этой фразы начинается любое програмиирование.

мы часто будем использовать макрос `println!("Вывести число:{}", a)` вывод в консоль, для проверки и получения результата.

 `"Вывести число:"` - в ковычках указыватся текст.  
 `"{}", a` - данные в переменой `a`, подставытся в `{}`.

 можно использовать несколько  
 `println!("Вывести числа a {} и b {}", a, b)` 

## Комнетарии. `// `, `/* */`
Комнетарии служит для заметок или описания сложных кусков кода. Часть с комнетарии пропускается компилятором.

*.rs*
```rust
// Однострочные
/*
  Много строчные
*/
/// Документация
//! Документация
```
*.toml*
```toml  
# Однострочные
```
> Именно на коментарии новичкам нужно обращать внимание или находить докуметацию.
# Глава 2
В первой главе мы создали проект. Далее мы будем работать в файле `main.rs`. в папке `src`.

## 1. Переменые `let _name`
```rust
let snake_case = 1; //Переменая с данными
let _snake_case; //Переменая без данных
``` 
Переменые - владеют какими-то данными, которые хранятся в памяти. 
Мы называем переменую ( даем имя ) и присваеваем или создаём данные. Когда мы передаем переменую, мы передаем сами данные.

- `let` - создает переменную
- `name` - это имя переменной, мы сами выбираем имя. (пишутся в нижнем регистре `let snake_case`, если мы не используем намерено то пишем `_` перед переменой `let _snake_case`)
- `=` - оператор присваивания, т.е. это имя будет ровно этим данным. 
- `1` - сами данные которыми владеем переменная.
- `;` - символ завершения оператора.


Раберем на примере:

Возьмём 1000 рублей, которые мы должны сохронить. 
эти данные мы явно запомним... 

1. __Дано: 1000.__

2. Теперь нам нужно *название* для неё.

Что это будет?

Может, это просто данные - *data*,
может что это деньги - *cash*,
название должно быть любым, но интуитивно понятным для другого программиста.
но влюбом случае для чего-то сложного можно оставит и коментарий.
```rust
fn main() {
    let cash = 1000; //рублей 
}
``` 
Переменая :
```rust
cash
```
Данные которыми владеет переменая:
```rust
1000
```
Сделаем ввывод в консоль
```rust
fn main() {
    let cash = 1000;
    println!("Сохранили {} рублей", cash);  
}
// println!("") макрос для печати 
// println!("{}", cash); подставить данные в текст.
``` 
Теперь можем скомпилировать и запустить
```cargo 
$ cargo run
```

### 1.1. `mut` или способы изменить пременую.
По умолчанию все Rust переменные являются неизменяемыми.
чтобы дать возможность изменять данные в переменой нужен `mut`.
```rust
let mut cash = 1000;
cash = 500;
``` 
>теперь не будет ошибок когда изменим переменую. если тип совпадает

### 1.2. `Затенение` или способы изменить пременую.
Можно объявить переменную с тем же именем которое было использовано раньше и такая новая переменная заменит(затеняет) предыдущую.

```rust
let cash = 1000;
let cash = cash + 500; //1000+500
let cash = 500;//500
``` 
 
# 2. Типы Данных.

Rust является статически типизированным языком. Это означает, что он должен знать типы всех переменных во время компиляции.

Ранее мы записали не указывая тип потому что компилятор сам понимает какой тип данных мы передаем, но иногда компилятору нужно помочь.

Cоздается переменая и указывается её имя `let _name`, заним указыкается тип данных `:type`,
делее уже происходит присваевание и т.д.

Примеры типов: 
```rust
//Связаные с числами
let _name:i32 = 1; //Целочисленный от -.. до +..
let _name:u32 = 1; //Целочисленный от 0 до ..
let _name:f64 = 1.0; //Числа с плавающей запитой

//Булевые(Логические) значения (Правда/Лож)(1/0)
let _name:bool = true; //Булевые 
let _name:bool = false; //Булевые

//Связаные с симвалами
let _name:char = "С"; //Посимвольные (один символ)
let _name:String = "Строки"; //Строки 
let _name:&str = "Срезы"; //Срезы

//Сложные/Сотавные типы (Группы из выше перечисленых типов)
let _name:[i32; 5] = [1, 2, 3, 4, 5]; //Массивы 
let _name:(i32, f64, u8) = (1, 1.0, 1); //Кортежи
let _name:NewType = NewType::new(); //Cвой тип созданый с помощью struct или enum
```

## 3. Функции `fn name(){..}`.
В первой главе мы уже немного познакимились с функцией `fn main(){..}` - это вход в программу. Компилятор запускает первой функцию `main();`- это значит запускает код внутри фигурнных скобках.
```rust
fn main(){
  /*
  Код, который будет запущен.
  */
}
```
Мы можем создать свои функции и поместить в её код, а затем вызвать эту функцию.
```rust
fn main(){
    func();
    //..
}
fn func(){
   /*
  Код, который будет запущен.
  */
}
```
1. компилятор вызывает `main()`
2. `main()` доходит `{` 
3. `main()` вызывает `func();` 
4. `func()`запускает код `{/*Код, который будет запущен.*/}`
5. `//..`
6. `main()` доходит до`}`
7. программа завершается.

### Задачи функции:

### Функция - запускает код, внутри фигурных скобок `{..}`, при вызове фунции. 

Вызов функции:
```rust
func();
```
Функция:
```rust
fn func(){
    //ничего не делает
}
```
```rust
fn func(){
    println!("function");//печатает в консоли "function"
}
```
### Функция - Возвращает данные, мы их запишим в переменую.

Вызов функции:
```rust
let foo = func();
```
Функция:
```rust
fn func() ->i32{
    1
}
```
### Функция - Принимает, обрабатывает и возвращает данные.
Вызов функции:
```rust
let foo = func(1);
```
Функция:
```rust
fn func_print(x: i32) ->i32{
    let y = x + 1; //обрабатывает
    y //возвращает
}
```
- `fn` - Создает функцию.
- `main` - Это имя функцию, мы сами выбираем имя. (пишутся в нижнем регистре `snake_case`)
- `()` - В вскобки мы принимаем, переменые для использования в фигурных скобках`{}`.
- Примеры:
- 1. `()` непринимаем аргументы.
- 2. `(name: i32)` пременые.
- 3. `(&name: i32)` ссылки на переменые.
- 4. `(&mut name: i32)` изменяемые ссылки на переменые.
- `->i32` Тип данных, которые фунция возвращает. (`->`и тип данных). Можно не указывать, если функция ничего не возвращает(по умолчанию `->()`).
- `{..}` - Тело функции. 
- 1. `..` - Сам код.
- 2. `{__;}`- этот код запускает, при вызове функции.
- 3. `{x}` - этот код возвращает, данные при вызове функции. не ставятся `;` - когда функция возвращает данные.
