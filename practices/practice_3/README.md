# Стратегия

Стратегия – поведенческий шаблон, призванный для обеспечения взаимозаменяемости разных алгоритмов или вариаций алгоритма с одинаковыми интерфейсами. Стратегии – и есть эти варианты. В зависимости от условий (контекст) код выбирает подходящий алгоритм. 

Мы создаем общий интерфейс стратегий BaseStrategy – как абстрактный класс ABC. Далее в каждой стратегии реализуем этот интерфейс.

Создаем интерфейс:

```
class BaseStrategy(ABC):
    @abstractmethod
    def do_work(self, x, y):
        pass
```

Создаем классы:

```
class Adder(BaseStrategy):
    def do_work(self, x, y):
        return x + y
```

```
class Multiplicator(BaseStrategy):
    def do_work(self, x, y):
        return x * y
```

```
class Calculator:
    def set_strategy(self, strategy: BaseStrategy):
        self.strategy = strategy
    def calculate(self, x, y):
        print('Result is', self.strategy.do_work(x, y))
```

## Диаграмма



# Шаблонный метод
