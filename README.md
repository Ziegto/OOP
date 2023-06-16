# OOP

__Kódy__: <br/>
**Deklarace čistě abstraktní třídy A s konstruktorem, destruktorem a dvěma dalšími metodami:**
```
class A {
public:
    A() {}  // Konstruktor
    virtual ~A() {}  // Virtuální destruktor
    virtual void method1() = 0;  // Čistě virtuální metoda
    virtual void method2() = 0;  // Čistě virtuální metoda
};
```

**Deklarace konkrétního potomka B:**
```
class B : public A {
public:
    B() {}  // Konstruktor třídy B
    ~B() {}  // Destruktor třídy B
    void method1() override {
        // Implementace metody M1 pro třídu B
    }
    void method2() override {
        // Implementace metody M2 pro třídu B
    }
};
```

**Deklarace třídy A s datovými položkami, destruktorem a alespoň třemi konstruktory:**
```
class A {
private:
    int data1;
    float data2;
public:
    A() {}  // Implicitní konstruktor
    A(int d1) : data1(d1) {}  // Konstruktor s jedním parametrem
    A(int d1, float d2) : data1(d1), data2(d2) {}  // Konstruktor s dvěma parametry
    ~A() {}  // Destruktor
};
```

**Deklarace třídy A s jednou datovou položkou a dvěma metodami, která je v roli objektu a nelze vytvořit její instanci z vnějšku:**
```
class A {
private:
    int data;
    A() {}  // Soukromý konstruktor
public:
    static A& getInstance() {
        static A instance;
        return instance;
    }
    void method1() {
        // Implementace metody
    }
    void method2() {
        // Implementace metody
    }
};
```

**Deklarace a definice třídy MATH, která se chová jako objekt a nelze vytvořit její instance, obsahuje funkce na nalezení minima a maxima ze dvou čísel:**
```
class MATH {
private:
    MATH() {}  // Soukromý konstruktor
public:
    static int min(int a, int b) {
        return (a < b) ? a : b;
    }
    static int max(int a, int b) {
        return (a > b) ? a : b;
    }
};
```

**Deklarace obecné třídy s alespoň jednou generickou datovou položkou a jednou metodou s obecným datovým parametrem:**
```
template<typename T>
class S {
private:
    T data;
public:
    S(T value) : data(value) {}
    void method(T param) {
        // Implementace metody s generickým parametrem
    }
};
```
