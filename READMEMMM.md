# Залік

**Імʼя:** Маркіян Братейко  
**Група:** КН-32  

---

## Завдання 3

Створити клас `FactorialCalculator`, який:

- Приймає в конструкторі додатне число `n` (наприклад, `n = 5`)
- Має метод `calculate()`, який обчислює факторіал числа `n`
- Має property `factorial`, яка повертає обчислений факторіал

---

## User Prompt

Твоє завдання виконати **«Завдання 3»** у попередній комірці, дотримуючись наступних вимог:

- Створити клас `FactorialCalculator`
- Приймає в конструкторі додатне число `n` (наприклад, `n = 5`)
- Має метод `calculate()`, який обчислює факторіал числа `n`
- Має property `factorial`, яка повертає обчислений факторіал

---

## Реалізація

```python
class FactorialCalculator:
    def __init__(self, n: int):
        if n < 0:
            raise ValueError("n повинно бути додатним числом")
        self.n = n
        self._factorial = None

    def calculate(self):
        result = 1
        for i in range(1, self.n + 1):
            result *= i
        self._factorial = result
        return result

    @property
    def factorial(self):
        if self._factorial is None:
            raise ValueError("Спочатку виклич calculate()")
        return self._factorial
fc = FactorialCalculator(5)
fc.calculate()
print(fc.factorial)  # 120
