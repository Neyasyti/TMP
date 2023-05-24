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
