---
title: Python에서 super()의 역할과 super().__init__과 명시적 상속의 차이
date: 2023-09-28 20:00:00 +0900
categories:
  - python
tags:
  - Python
---
## `super()`가 무엇인가요?

`super()`는 Python에서 사용되는 내장 함수로, 부모 클래스의 메서드를 호출할 수 있도록 도와줍니다. 이 함수는 주로 상속을 통해 부모 클래스의 속성이나 메서드를 확장하거나 변경할 때 사용됩니다.

## `super().__init__`은 어떻게 동작하는가요?

`super().__init__()` 메서드는 자식 클래스가 생성될 때 부모 클래스의 생성자를 호출하게 됩니다. 이렇게 함으로써, 자식 클래스는 부모 클래스의 모든 속성과 메서드를 상속받을 수 있습니다.

예시:
```python
class Parent:
    def __init__(self, name):
        self.name = name

class Child(Parent):
    def __init__(self, name, age):
        super().__init__(name)
        self.age = age
```

여기서 `Child` 클래스의 인스턴스를 생성하면, `super().__init__(name)`이 호출되어 `Parent` 클래스의 `__init__` 메서드도 실행됩니다. 이로써 `Child` 인스턴스는 `name`과 `age`라는 두 가지 속성을 가지게 됩니다.

## 명시적 상속과 `super().__init__`의 차이는?

명시적 상속은 부모 클래스의 메서드를 직접 호출하는 방법입니다. 이 방법은 파이썬 2와 파이썬 3에서 동작이 다르며, 코드의 가독성과 유지 보수 측면에서 복잡할 수 있습니다.

예시:
```python
class Child(Parent):
    def __init__(self, name, age):
        Parent.__init__(self, name)
        self.age = age
```

`super().__init__`을 사용하면, 상속 체인을 자동으로 관리해주기 때문에 코드가 더 간결하고 가독성이 좋습니다. 또한 파이썬 2와 파이썬 3에서 동일하게 동작합니다.

## 정리

`super()`는 Python의 상속 메커니즘을 간편하게 만들어주는 훌륭한 도구입니다. `super().__init__`을 사용하면, 상속받은 부모 클래스의 생성자를 자동으로 호출해 줍니다. 이 방법은 명시적 상속 방법보다 코드가 깔끔하고 유지 보수하기 쉽습니다. 따라서 가능하면 `super()`를 사용하는 것이 좋습니다.