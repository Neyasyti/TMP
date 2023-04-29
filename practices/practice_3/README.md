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

```
@startuml
class Strategy.Calculator {
~ Activity activity
+ void setActivity(Activity)
+ void executeActivity()
}
class Strategy.Adder {
+ void AddSmth()
}
interface Strategy.BaseStrategy {
+ void AddSmth()
+ void MultiplicateSmth()
}
class Strategy.Multiplicator {
+ void MultiplicateSmth()
}

Strategy.BaseStrategy <|.. Strategy.Adder
Strategy.BaseStrategy <|.. Strategy.Multiplicator

@enduml

```
![](https://github.com/Smipos/TMP/blob/main/practices/practice_3/strategy/strategy.jpg)

# Шаблонный метод
