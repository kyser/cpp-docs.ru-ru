---
title: Класс recursive_mutex | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- mutex/std::recursive_mutex
- mutex/std::recursive_mutex::recursive_mutex
- mutex/std::recursive_mutex::lock
- mutex/std::recursive_mutex::try_lock
- mutex/std::recursive_mutex::unlock
dev_langs:
- C++
ms.assetid: eb5ffd1b-7e78-4559-8391-bb220ead42fc
author: corob-msft
ms.author: corob
helpviewer_keywords:
- std::recursive_mutex [C++]
- std::recursive_mutex [C++], recursive_mutex
- std::recursive_mutex [C++], lock
- std::recursive_mutex [C++], try_lock
- std::recursive_mutex [C++], unlock
ms.workload:
- cplusplus
ms.openlocfilehash: 89c39f006cee8c62c22f3caf7e2c10ee9a0c1d03
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="recursivemutex-class"></a>Класс recursive_mutex

Представляет *тип мьютекса*. В отличие от класса [mutex](../standard-library/mutex-class-stl.md), поведение вызовов методов блокировки для объектов, которые уже заблокированы, четко определено.

## <a name="syntax"></a>Синтаксис

```cpp
class recursive_mutex;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[recursive_mutex](#recursive_mutex)|Создает объект `recursive_mutex`.|
|[Деструктор ~recursive_mutex](#dtorrecursive_mutex_destructor)|Освобождает все ресурсы, используемые объектом `recursive_mutex`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[lock](#lock)|Блокирует вызывающий поток до тех пор, пока этот поток не получит права владельца мьютекса.|
|[try_lock](#try_lock)|Попытки получить права владельца мьютекса без блокировки.|
|[unlock](#unlock)|Освобождает права владения мьютексом.|

## <a name="requirements"></a>Требования

**Заголовок:** \<мьютекс >

**Пространство имен:** std

## <a name="lock"></a>  lock

Блокирует вызывающий поток до тех пор, пока этот поток не получит права владельца объекта `mutex`.

```cpp
void lock();
```

### <a name="remarks"></a>Примечания

Если вызывающий поток уже владеет `mutex`, метод немедленно возвращает значение и предыдущая блокировка остается в силе.

## <a name="recursive_mutex"></a>  recursive_mutex

Создает объект `recursive_mutex`, который не заблокирован.

```cpp
recursive_mutex();
```

## <a name="dtorrecursive_mutex_destructor"></a>  ~recursive_mutex

Освобождает все ресурсы, используемые объектом.

```cpp
~recursive_mutex();
```

### <a name="remarks"></a>Примечания

Если при выполнении деструктора объект заблокирован, поведение не определено.

## <a name="try_lock"></a>  try_lock

Попытки получить права владельца объекта `mutex` без блокировки.

```cpp
bool try_lock() noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

`true`, если метод успешно получает права владельца `mutex` или если вызывающий поток уже владеет `mutex`; в противном случае — `false`.

### <a name="remarks"></a>Примечания

Если вызывающий поток уже владеет `mutex`, метод немедленно возвращает `true` и предыдущая блокировка остается в силе.

## <a name="unlock"></a>  unlock

Освобождает права владения мьютексом.

```cpp
void unlock();
```

### <a name="remarks"></a>Примечания

Этот метод освобождает владение `mutex` только после его вызова столько раз, сколько [lock](#lock) и [try_lock](#try_lock) были успешно вызваны для объекта`recursive_mutex`.

Если вызывающий поток не является владельцем `mutex`, поведение не определено.

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<mutex>](../standard-library/mutex.md)<br/>
