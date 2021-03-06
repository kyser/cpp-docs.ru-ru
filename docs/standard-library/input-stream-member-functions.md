---
title: Функции — члены потока ввода | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- input stream objects
- input streams, member functions
ms.assetid: b4b9465d-0da9-4ccf-859d-72a68418982e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 41ab041fe3cee9a3b6065f22e5f96a44a56af030
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="input-stream-member-functions"></a>Функции-члены потока ввода

Функции — члены потока ввода используются для дисковых операций ввода. К этим функциям относятся:

- [Функция open для потоков ввода](#vclrftheopenfunctionforinputstreamsanchor11)

- [Get](#vclrfthegetfunctionanchor12)

- [Getline](#vclrfthegetlinefunctionanchor13)

- [Операция чтения](#vclrfthereadfunctionanchor14)

- [Функции seekg и tellg](#vclrftheseekgandtellgfunctionsanchor7)

- [Функция close для потоков ввода](#vclrftheclosefunctionforinputstreamsanchor15)

## <a name="vclrftheopenfunctionforinputstreamsanchor11"></a> Функция open для потоков ввода

При использовании входного файлового потока (ifstream) этот поток необходимо связать с конкретным файлом на диске. Это можно сделать в конструкторе или через функцию **open**. В любом случае аргументы одни и те же.

Как правило, задают флаг [ios_base::openmode](../standard-library/ios-base-class.md#openmode) при открытии файла, связанного с потоком ввода (режим по умолчанию — **ios::in**). Список **open_mode** флаги, в разделе [открытия](#vclrftheopenfunctionforinputstreamsanchor11). Флаги могут быть объединены с помощью побитового оператора OR (&#124;).

Для чтения файла сначала используйте функцию-член **fail**, чтобы определить, существует ли этот файл:

```cpp
istream ifile("FILENAME");

if (ifile.fail())
// The file does not exist ...
```

## <a name="vclrfthegetfunctionanchor12"></a> Get

Неформатированная функция **get** аналогична оператору **>>** с двумя исключениями. Во-первых, функция **get** включает знаки пробела, а функция извлечения исключает пробелы, если флаг **skipws** установлен (по умолчанию). Во-вторых, функция **get** с меньшей вероятностью вызовет сброс на диск связанного потока вывода (например, `cout`).

Разновидность функции **get** указывает адрес буфера и максимальное число символов для чтения. Это полезно для ограничения количества символов, отправленных в конкретную переменную, как показано в примере:

```cpp
// ioo_get_function.cpp
// compile with: /EHsc
// Type up to 24 characters and a terminating character.
// Any remaining characters can be extracted later.
#include <iostream>
using namespace std;

int main()
{
   char line[25];
   cout << " Type a line terminated by carriage return\n>";
   cin.get( line, 25 );
   cout << line << endl;
}
```

### <a name="input"></a>Входные данные

```Input
1234
```

### <a name="sample-output"></a>Пример результатов выполнения

```Output
1234
```

## <a name="vclrfthegetlinefunctionanchor13"></a> Getline

Функция-член **getline** аналогична функции **get**. Обе функции допускают третий аргумент, который указывает завершающий символ для входных данных. Значение по умолчанию — символ новой строки. Обе функции резервируют один символ для необходимого завершающего символа. Однако **get** оставляет завершающий символ в потоке, а **getline** удаляет его.

В следующем примере задается завершающий символ для потока ввода:

```cpp
// getline_func.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main( )
{
   char line[100];
   cout << " Type a line terminated by 't'" << endl;
   cin.getline( line, 100, 't' );
   cout << line;
}
```

### <a name="input"></a>Входные данные

```Input
test
```

## <a name="vclrfthereadfunctionanchor14"></a> Операция чтения

Функция-член **read** читает байты из файла в указанную область памяти. Аргумент length определяет количество прочтенных байтов. Если этот аргумент не указан, чтение останавливается при достижении физического конца файла или, в случае файла в текстовом режиме, при чтении встроенного символа `EOF`.

Этот пример считывает двоичную запись из файла заработной платы в структуру:

```cpp
#include <fstream>
#include <iostream>
using namespace std;

int main()
{
   struct
   {
      double salary;
      char name[23];
   } employee;

   ifstream is( "payroll" );
   if( is ) {  // ios::operator void*()
      is.read( (char *) &employee, sizeof( employee ) );
      cout << employee.name << ' ' << employee.salary << endl;
   }
   else {
      cout << "ERROR: Cannot open file 'payroll'." << endl;
   }
}
```

Программа предполагает, что записи данных имеют формат, точно как указано в структуре, без завершающих символов возврата каретки или перевода строки.

## <a name="vclrftheseekgandtellgfunctionsanchor7"></a> Функции seekg и tellg

Потоки входного файла хранят внутренний указатель на позицию в файле, с которой будет продолжаться чтение. Этот указатель можно установить функцией `seekg`, как показано ниже:

```cpp
#include <iostream>
#include <fstream>
using namespace std;

int main( )
{
   char ch;

   ifstream tfile( "payroll" );
   if( tfile ) {
      tfile.seekg( 8 );        // Seek 8 bytes in (past salary)
      while ( tfile.good() ) { // EOF or failure stops the reading
         tfile.get( ch );
         if( !ch ) break;      // quit on null
         cout << ch;
      }
   }
   else {
      cout << "ERROR: Cannot open file 'payroll'." << endl;
   }
}
```

Для использования `seekg` при реализации систем управления данными на базе записей, умножьте размер записи фиксированной длины на номер записи, чтобы получить позицию байта относительно конца файла, а затем используйте объект **get** для чтения записи.

Функция-член `tellg` возвращает текущую позицию в файле для чтения. Это значение имеет тип `streampos`, `typedef`, определенное в \<iostream>. В следующем примере выполняется чтение файла и показ сообщения с позициями пробелов.

```cpp
#include <fstream>
#include <iostream>
using namespace std;

int main( )
{
   char ch;
   ifstream tfile( "payroll" );
   if( tfile ) {
       while ( tfile.good( ) ) {
          streampos here = tfile.tellg();
          tfile.get( ch );
          if ( ch == ' ' )
             cout << "\nPosition " << here << " is a space";
       }
   }
   else {
      cout << "ERROR: Cannot open file 'payroll'." << endl;
   }
}
```

## <a name="vclrftheclosefunctionforinputstreamsanchor15"></a> Функция close для потоков ввода

Функция-член **close** закрывает файл на диске, связанный с входным файловым потоком, и освобождает дескриптор файла операционной системы. Деструктор [Ifstream](../standard-library/basic-ifstream-class.md) закрывает файл, но можно использовать функцию **close**, если нужно открыть другой файл для того же объекта потока.

## <a name="see-also"></a>См. также

[Входные потоки](../standard-library/input-streams.md)<br/>
