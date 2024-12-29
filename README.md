# rasteador

## Descripción

El script incluye las siguientes funciones:

### `add_expense(expenses, amount, category)`

Esta función agrega un gasto a la lista de gastos.

- **Parámetros:**
  - `expenses`: Lista de gastos.
  - `amount`: Monto del gasto.
  - `category`: Categoría del gasto.

```python
def add_expense(expenses, amount, category):
    expenses.append({'amount': amount, 'category': category})
```

### `print_expenses(expenses)`

Esta función imprime todos los gastos en la lista.

- **Parámetros:**
  - `expenses`: Lista de gastos.

```python
def print_expenses(expenses):
    for expense in expenses:
        print(f'Amount: {expense["amount"]}, Category: {expense["category"]}')
```

### `total_expenses(expenses)`

Esta función calcula el total de todos los gastos en la lista.

- **Parámetros:**
  - `expenses`: Lista de gastos.

- **Retorna:**
  - La suma total de los montos de los gastos.

```python
def total_expenses(expenses):
    return sum(map(lambda expense: expense['amount'], expenses))
```

### `filter_expenses_by_category(expenses, category)`

Esta función filtra los gastos por categoría.

- **Parámetros:**
  - `expenses`: Lista de gastos.
  - `category`: Categoría por la cual filtrar los gastos.

- **Retorna:**
  - Un filtro de gastos que pertenecen a la categoría especificada.

```python
def filter_expenses_by_category(expenses, category):
    return filter(lambda expense: expense['category'] == category, expenses)
```

### `main()`

Esta función principal proporciona una interfaz de usuario para interactuar con el rastreador de gastos. Permite al usuario agregar gastos, listar todos los gastos, mostrar el total de gastos y filtrar gastos por categoría.

```python
def main():
    expenses = []
    while True:
        print('\nExpense Tracker')
        print('1. Add an expense')
        print('2. List all expenses')
        print('3. Show total expenses')
        print('4. Filter expenses by category')
        print('5. Exit')

        choice = input('Enter your choice: ')

        if choice == '1':
            amount = float(input('Enter amount: '))
            category = input('Enter category: ')
            add_expense(expenses, amount, category)

        elif choice == '2':
            print('\nAll Expenses:')
            print_expenses(expenses)

        elif choice == '3':
            print('\nTotal Expenses: ', total_expenses(expenses))

        elif choice == '4':
            category = input('Enter category to filter: ')
            print(f'\nExpenses for {category}:')
            expenses_from_category = filter_expenses_by_category(expenses, category)
            print_expenses(expenses_from_category)

        elif choice == '5':
            print('Exiting the program.')
            break

main()
```
