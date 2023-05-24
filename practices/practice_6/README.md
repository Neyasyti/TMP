# Инверсия управления

your_name.py
```
config = {}

def your_name():
    output_function = config["OUTPUT_FUNCTION"]
    output_function("Your name, ")
```

your_name_people.py
```
people = []


def your_name_people():
    for person in people:
        print(f"Hello, {person}.")
```

main.py
```
import your_name

your_name.config["OUTPUT_FUNCTION"] = print

if __name__ == "__main__":
    your_name.your_name()
```

serzh.py
```
import your_name_people

your_name_people.people.append("Serzh")
```

## Диаграмма

```
@startuml Inversion_Of_Control
class YourName.your_name {
- config []
+ def your_name()
}
class YourName.your_name_people {
+ def your_name_people()
}
class YourName.main {
- config []
+ def your_name()
}
class YourName.serzh {
+ people.append()
}


YourName.your_name <|.. YourName.main
YourName.your_name_people <|.. YourName.main
YourName.serzh <|.. YourName.your_name
@enduml
```

![инверсия контроля](https://github.com/Smipos/TMP/blob/main/practices/practice_6/screens/Inversion_Of_Control.png)


# Заместитель (Proxy)

```
from abc import ABCMeta, abstractmethod
class ISubject(metaclass=ABCMeta):
    "An interface implemented by both the Proxy and Real Subject"
    @staticmethod
    @abstractmethod
    def request():
        "A method to implement"
class RealSubject(ISubject):
    "The actual real object that the proxy is representing"
    def __init__(self):
        self.enormous_data = [1, 2, 3]
    def request(self):
        return self.enormous_data
class Proxy(ISubject):
    def __init__(self):
        self.enormous_data = []
        self.real_subject = RealSubject()
    def request(self):
        if self.enormous_data == []:
            print("pulling data from RealSubject")
            self.enormous_data = self.real_subject.request()
            return self.enormous_data
        print("pulling data from Proxy cache")
        return self.enormous_data
    
SUBJECT = Proxy()

print(id(SUBJECT))
print(SUBJECT.request())
print(SUBJECT.request())
```

## Диаграмма
![Proxy](https://github.com/Smipos/TMP/blob/main/practices/practice_6/screens/proxy.png)
