---
title: 'Dependency Injection'
date: 2025-01-31
permalink: /posts/2025/01/blog-dependency-injection/
tags:
  - Software Engineering
  - Coding
  - C++
  - Python
  - Design Principles
---

# Dependency Injection

Types of Dependency injections:
- Dependency Injection with Inheritance/Polymorphism (run time)
- Dependency Injection with Template (complile time)
- 



## Dependency Injection with Template

It is a technique where dependencies are injected into a class through template parameters, allowing for compile-time configuration and customization. Instead of relying on abstract classes or interfaces and runtime polymorphism, template-based DI resolves dependencies statically. [Google AI]

### Examples
This can be analogous to color shade of different box. Assume we need to create a box class, but it can have different color. 
We can use color as a dependency and include it in the box class as template. 
In future, we can create our own custom color class, but do not have change the box class since it takes color as a template parameter.

Some examples are below:
Example # 1: From Google AI result
```

template <typename Dependency>
class Client {
public:
  Client(Dependency& dependency) : dep(dependency) {}

  void doSomething() {
    dep.execute();
  }
private:
    Dependency& dep;
};

class ConcreteDependency1 {
public:
    void execute() {
        // Implementation 1
    }
};

class ConcreteDependency2 {
public:
    void execute() {
        // Implementation 2
    }
};

int main() {
    ConcreteDependency1 dep1;
    Client<ConcreteDependency1> client1(dep1);
    client1.doSomething();

    ConcreteDependency2 dep2;
    Client<ConcreteDependency2> client2(dep2);
    client2.doSomething();
}


```

From this example, we can determine that we need to make those components as type parameter that have more probability of future extensions and being different genres.

**Pros and Cons**: Template-based dependency injection offers advantages like compile-time safety and potential performance gains by avoiding virtual function calls. However, it can increase code complexity and compile times, and might not be suitable for scenarios requiring runtime dependency switching.