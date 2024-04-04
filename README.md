# Labbaf
#1 (2)
def convert_currency(amount_in_uah, exchange_rate_eur, exchange_rate_usd):
    amount_in_eur = amount_in_uah / exchange_rate_eur
    amount_in_usd = amount_in_uah / exchange_rate_usd
    return amount_in_eur, amount_in_usd

def main():
    amount_in_uah = float(input("Введіть суму в гривнях: "))
    exchange_rate_eur = 32.5  # Припустимий курс обміну євро
    exchange_rate_usd = 27.8  # Припустимий курс обміну долара

    amount_in_eur, amount_in_usd = convert_currency(amount_in_uah, exchange_rate_eur, exchange_rate_usd)

    print(f"{amount_in_uah} грн = {amount_in_eur:.2f} євро")
    print(f"{amount_in_uah} грн = {amount_in_usd:.2f} доларів")

if name == "__main__":
    main()
#2 (9)
def calculate_unit_price(total_price, quantity):
    if quantity == 0:
        return "Помилка: кількість не може дорівнювати нулю"
    unit_price = total_price / quantity
    return unit_price

def main():
    total_price = float(input("Введіть загальну вартість товару: "))
    quantity = int(input("Введіть кількість товару: "))

    unit_price = calculate_unit_price(total_price, quantity)

    if isinstance(unit_price, str):
        print(unit_price)
    else:
        print(f"Вартість одиниці товару: {unit_price:.2f}")

if name == "__main__":
    main()
#3 (3)
def days_in_month(month):
    if month == 2:
        return 28
    elif month in [4, 6, 9, 11]:
        return 30
    elif month in [1, 3, 5, 7, 8, 10, 12]:
        return 31
    else:
        return None

def main():
    month = int(input("Введіть номер місяця: "))

    days = days_in_month(month)

    if days is not None:
        print(f"Кількість днів у місяці: {days}")
    else:
        print("Помилка: невірно введений номер місяця")

if name == "__main__":
    main()
#4 (8)
def main():
    numbers = []
    while True:
        try:
            num = float(input("Введіть число (або 'q' для виходу): "))
            numbers.append(num)
        except ValueError:
            if input("Ви впевнені, що хочете завершити введення? (y/n): ").lower() == "y":
                break

    if numbers:
        average = sum(numbers) / len(numbers)
        max_number = max(numbers)
        print(f"Середнє арифметичне: {average}")
        print(f"Максимальний елемент: {max_number}")
    else:
        print("Ви не ввели жодного числа.")

if name == "__main__":
    main()

#5(1)
def calculate_total_resistance(resistance1, resistance2, connection_type):
    if connection_type.lower() == 'паралельне':
        total_resistance = (resistance1 * resistance2) / (resistance1 + resistance2)
    elif connection_type.lower() == 'серійне':
        total_resistance = resistance1 + resistance2
    else:
        total_resistance = None
        print("Помилка: невірно введений тип з'єднання")

    return total_resistance

resistor1 = 100  # опір першого резистора в Омах
resistor2 = 200  # опір другого резистора в Омах
connection = 'паралельне'  # тип з'єднання ('паралельне' або 'серійне')

total_resistance = calculate_total_resistance(resistor1, resistor2, connection)
if total_resistance is not None:
    print(f"Загальний опір кола: {total_resistance} Ом")
#6 (2)
def calculate_column_sum(matrix):
    column_sums = []
    for j in range(len(matrix[0])):
        column_sum = sum(matrix[i][j] for i in range(len(matrix)))
        column_sums.append(column_sum)
    return column_sums

def calculate_row_product(matrix):
    row_products = []
    for row in matrix:
        product = 1
        for num in row:
            product *= num
        row_products.append(product)
    return row_products

def main():
    matrix = [
        [1, 2, 3],
        [4, 5, 6],
        [7, 8, 9]
    ]

    column_sums = calculate_column_sum(matrix)
    row_products = calculate_row_product(matrix)

    print("Сума елементів стовбців:")
    for idx, column_sum in enumerate(column_sums):
        print(f"Стовбець {idx + 1}: {column_sum}")

    print("\nДобуток елементів рядків:")
    for idx, row_product in enumerate(row_products):
        print(f"Рядок {idx + 1}: {row_product}")
if name == "__main__":
    main()
#7 (12)
def remove_a_o(text):
    cleaned_text = ''.join(char for char in text if char.lower() not in ['a', 'o'])
    return cleaned_text

def main():
    input_text = input("Введіть текст: ")
    result_text = remove_a_o(input_text)
    print("Результат:", result_text)

if name == "__main__":
    main()
)
#8 (1)
def merge_sorted_arrays(arr1, arr2):
    merged_array = []
    i = j = 0
    
    while i < len(arr1) and j < len(arr2):
        if arr1[i] < arr2[j]:
            merged_array.append(arr1[i])
            i += 1
        else:
            merged_array.append(arr2[j])
            j += 1
    
    merged_array.extend(arr1[i:])
    merged_array.extend(arr2[j:])
    
    return merged_array

def main():
    array1 = ['a', 'c', 'e', 'g', 'i']
    array2 = ['b', 'd', 'f', 'h', 'j']

    merged_array = merge_sorted_arrays(array1, array2)

    print("Об'єднаний впорядкований масив:", merged_array)

if name == "__main__":
    main()
#9(1)
def main():
    cars = []

    n = int(input("кількість автомобілів: "))
    for i in range(1, n + 1):
        model = input(f"модель автомобіля {i}: ")
        year = int(input(f"рік випуску автомобіля {i}: "))
        price = float(input(f"ціну автомобіля {i} (в грн): "))
        color = input(f"колір автомобіля {i}: ")
        horsepower = float(input(f"потужність двигуна автомобіля {i} (у кінських силах): "))

        cars.append({
            'model': model,
            'year': year,
            'price': price,
            'color': color,
            'horsepower': horsepower
        })

    print("Автомобілі, які задовольняють умови:")
    for car in cars:
        if car['color'].lower() == 'червоний' and car['year'] > 2002 and car['price'] < 50000:
            print(f"Модель: {car['model']}, Рік: {car['year']}, Ціна: {car['price']} грн, Колір: {car['color']}, Потужність: {car['horsepower']} к.с.")

if name == "__main__":
    main()
