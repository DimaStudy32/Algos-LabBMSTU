# Эмпирический анализ временной сложности алгоритмов

## Цель работы

Эмпирический анализ временной сложности алгоритмов.

## Работу выполнил
Цыганков Д.С
## Группа 
ИУ10-37

## Задания 
### Задание 1.2
```python
import random
import time
import matplotlib.pyplot as plt

def sum_elements(v: list):
    total = 0
    for num in v:
        total += num
    return total

student_number = 8 
N = 20 - student_number

items = range(1, 10**5 * N, 50000)
times = []

print(f"Задание 1.2 | Вариант {student_number} | Точек: {len(list(items))}")

for n in items:
    total_time = 0
    
    for _ in range(20):
        vector = [random.randint(1, 10) for _ in range(n)]
        
        start_time = time.perf_counter()
        result = sum_elements(vector)
        end_time = time.perf_counter()
        
        total_time += (end_time - start_time)
    
    avg_time = total_time / 20
    times.append(avg_time)
    print(f"n={n}: {avg_time:.6f} сек")

plt.plot(items, times, 'bo-')
plt.title('The execution time of the sum of list elements algorithm')
plt.xlabel('Number of elements')
plt.ylabel('Time, sec')
plt.grid(True)
plt.show()
```

![png](Img/Num1.2.Image.png)



