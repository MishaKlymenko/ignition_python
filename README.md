# ignition_python

## Задача 1. Конвертер валют  
Написати функцію `convert_currency(amount, rate)`, яка перетворює суму `amount` з однієї валюти в іншу за курсом `rate`.
`print(convert_currency(100, 39.5))  # 3950.0 (наприклад, USD → UAH)`

## Задача 2. Валідатор паролю
Написати функцію `check_password(password)`, яка перевіряє, чи містить пароль щонайменше 8 символів, одну цифру та одну велику літеру.

## Задача 3. Форматування номера телефону
Написати функцію `format_phone(number)`, яка перетворює введений номер телефону в стандартний формат `+38 (XXX) XXX-XX-XX`.

## Задача 4. Генератор паролів
Написати функцію `generate_password(length)`, яка створює випадковий пароль заданої довжини.
`print(generate_password(12))  # Наприклад: G#2f@9dL!kM8`

## Задача 5. Аналіз витрат за категоріями
Написати функцію `analyze_expenses(transactions)`, яка приймає список витрат у форматі  
`[("Їжа", 200), ("Транспорт", 150), ("Їжа", 300), ("Розваги", 500)]`  
і повертає словник із загальними витратами по кожній категорії.

## Задача 6. Пошук найприбутковішого товару
Написати функцію `best_selling_product(sales)`, яка приймає список продажів у форматі
`[("Ноутбук", 5, 1000), ("Телефон", 10, 500), ("Планшет", 3, 700)]`
і повертає назву товару, який приніс найбільший дохід.

## Задача 7. Перетворення числа в текст (до 999)
Написати функцію `number_to_words(n)`, яка перетворює число (1-999) у текстовий формат.
(Наприклад, 123 → "сто двадцять три")

## Задача 8. Аналіз коментарів (середня довжина)
Написати функцію `average_comment_length(comments)`, яка приймає список коментарів і повертає середню довжину одного коментаря.


----------------------------------------------------------------------------------------

### 1. Списки (Lists)
Список — це впорядкована, змінна (mutable) колекція елементів. Елементи можуть бути різного типу.

#### Основні характеристики:
- Створюється за допомогою квадратних дужок `[]` або функції `list()`.
- Елементи індексуються (починаючи з 0).
- Можна змінювати: додавати, видаляти, змінювати елементи.

#### Створення списків:
```python
список = [1, 2, 3, "текст", True]  # Різні типи даних
порожній_список = []
ще_один_список = list("слово")  # ['с', 'л', 'о', 'в', 'о']
```

#### Основні методи:
- `append(x)` — додає елемент `x` у кінець списку.
- `insert(i, x)` — вставляє `x` на позицію `i`.
- `remove(x)` — видаляє перше входження `x`.
- `pop(i)` — видаляє і повертає елемент за індексом `i` (за замовчуванням останній).
- `index(x)` — повертає індекс першого входження `x`.
- `count(x)` — підраховує кількість входжень `x`.
- `sort()` — сортує список (тільки для однотипних даних).
- `reverse()` — перевертає список.

#### Приклади:
```python
фрукти = ["яблуко", "банан"]
фрукти.append("апельсин")  # ['яблуко', 'банан', 'апельсин']
фрукти.insert(1, "груша")  # ['яблуко', 'груша', 'банан', 'апельсин']
фрукти.remove("банан")     # ['яблуко', 'груша', 'апельсин']
print(фрукти.pop())        # 'апельсин', список: ['яблуко', 'груша']
print(фрукти[0])           # 'яблуко'
```

#### Зрізи (slicing):
```python
числа = [0, 1, 2, 3, 4]
print(числа[1:4])  # [1, 2, 3]
print(числа[:3])   # [0, 1, 2]
print(числа[::2])  # [0, 2, 4] (крок 2)
```

---

### 2. Кортежі (Tuples)
Кортеж — це впорядкована, незмінна (immutable) колекція елементів.

#### Основні характеристики:
- Створюється за допомогою круглих дужок `()` або функції `tuple()`.
- Елементи індексуються (починаючи з 0).
- Не можна змінювати після створення.

#### Створення кортежів:
```python
кортеж = (1, 2, 3, "текст")
порожній_кортеж = ()
один_елемент = (5,)  # Кома потрібна, інакше це не кортеж
ще_кортеж = tuple([1, 2, 3])  # (1, 2, 3)
```

#### Основні методи:
- `index(x)` — повертає індекс першого входження `x`.
- `count(x)` — підраховує кількість входжень `x`.

#### Приклади:
```python
кортеж = (1, 2, 2, 3)
print(кортеж[1])      # 2
print(кортеж.count(2)) # 2
print(кортеж.index(3)) # 3
# кортеж[0] = 5  # Помилка! Кортеж незмінний
```

#### Використання:
Кортежі корисні, коли потрібна незмінна структура (наприклад, для ключів у словниках).

---

### 3. Словники (Dictionaries)
Словник — це невпорядкована колекція пар "ключ: значення". Ключі унікальні, значення можуть повторюватися.

#### Основні характеристики:
- Створюється за допомогою фігурних дужок `{}` або функції `dict()`.
- Ключі можуть бути будь-яким незмінним типом (рядки, числа, кортежі).
- Змінний (можна додавати/видаляти пари).

#### Створення словників:
```python
словник = {"імя": "Олег", "вік": 25}
порожній_словник = {}
ще_словник = dict(імя="Аня", вік=22)
```

#### Основні методи:
- `get(key)` — повертає значення за ключем (або None, якщо ключа немає).
- `keys()` — повертає всі ключі.
- `values()` — повертає всі значення.
- `items()` — повертає пари (ключ, значення).
- `pop(key)` — видаляє і повертає значення за ключем.
- `update()` — оновлює словник новими парами.

#### Приклади:
```python
людина = {"імя": "Марта", "вік": 30}
print(людина["імя"])       # 'Марта'
людина["зріст"] = 1.65     # Додає нову пару
людина.pop("вік")          # Видаляє 'вік'
print(людина.get("стать", "невідомо"))  # 'невідомо'
print(людина.keys())       # dict_keys(['імя', 'зріст'])
print(людина.items())      # dict_items([('імя', 'Марта'), ('зріст', 1.65)])
```

---

### 4. Множини (Sets)
Множина — це невпорядкована колекція унікальних елементів.

#### Основні характеристики:
- Створюється за допомогою фігурних дужок `{}` (без пар) або функції `set()`.
- Змінна (можна додавати/видаляти елементи).
- Не підтримує індексацію, бо немає порядку.

#### Створення множин:
```python
множина = {1, 2, 3, 3}  # {1, 2, 3} (дублікати видаляються)
порожня_множина = set()  # Не {} — це словник!
ще_множина = set([1, 2, 2, 3])  # {1, 2, 3}
```

#### Основні методи:
- `add(x)` — додає елемент `x`.
- `remove(x)` — видаляє `x` (помилка, якщо немає).
- `discard(x)` — видаляє `x` (без помилки, якщо немає).
- `union()` або `|` — об’єднання множин.
- `intersection()` або `&` — перетин множин.
- `difference()` або `-` — різниця множин.

#### Приклади:
```python
множина = {1, 2, 3}
множина.add(4)         # {1, 2, 3, 4}
множина.discard(2)     # {1, 3, 4}
множина2 = {3, 4, 5}
print(множина | множина2)  # {1, 3, 4, 5}
print(множина & множина2)  # {3, 4}
print(множина - множина2)  # {1}
```

---

### Порівняння
| Тип          | Змінність     | Порядок | Унікальність | Синтаксис         |
|--------------|---------------|---------|--------------|-------------------|
| Список       | Змінний       | Є       | Ні           | `[]`             |
| Кортеж       | Незмінний     | Є       | Ні           | `()`             |
| Словник      | Змінний       | Ні      | Ключі — так  | `{ключ: значення}` |
| Множина      | Змінний       | Ні      | Так          | `{}` або `set()` |

---

### Практичне застосування
- **Списки**: для зберігання впорядкованих даних (наприклад, список завдань).
- **Кортежі**: для фіксованих наборів (наприклад, координати x, y).
- **Словники**: для асоціацій (наприклад, інформація про людину).
- **Множини**: для унікальних елементів і операцій типу об’єднання/перетину.