# Decorator

## @property:
In Python, ***@property*** is a built-in decorator that provides a way to manage class attributes. It allows methods to be accessed like attributes, enabling control over attribute access, modification, and deletion. It is commonly used to implement getters, setters, and deleters for class attributes.

```
class MyClass:
    def __init__(self, value):
        self._value = value
    
    @property
    def value(self):
        """Getter method for the value attribute."""
        return self._value
    
    @value.setter
    def value(self, new_value):
        """Setter method for the value attribute."""
        if new_value >= 0:
            self._value = new_value
        else:
            raise ValueError("Value must be non-negative")
    
    @value.deleter
    def value(self):
        """Deleter method for the value attribute."""
        del self._value

# Example Usage
obj = MyClass(10)
print(obj.value)  # Accessing value using the getter
obj.value = 20  # Setting value using the setter
print(obj.value)
del obj.value  # Deleting value using the deleter

```
In this example, ***@property*** is used to define a getter, setter, and deleter for the value attribute. The getter method is defined with the ***@property*** decorator, while the setter and deleter methods are defined using the @value.setter and @value.deleter decorators, respectively. This allows the value attribute to be accessed, modified, and deleted like a regular attribute, while still providing control over these operations.