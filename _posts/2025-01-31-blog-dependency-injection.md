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



## Template Base Method

This can be analogous to color shade of different box. Assume we need to create a box class, but it can have different color. 
We can use color as a dependency and include it in the box class as template. 
In future, we can create our own custom color class, but do not have change the box class since it takes color as a template parameter.

Some examples are below:
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