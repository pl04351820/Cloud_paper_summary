### Keyword in cpp

#### static
1. Variable. Malloc space and initilize it in global area (data segmentation)
2. Function. This funciton can be used only in this file.
3. Class attribute. All objects share this varible.
4. Class method. No inilization can access to this funciton.

#### this
Used in class to differentiate the attribute between different object
```
class Box
{
    public:
      int compare(Box box)
      {
         return this->Volume() > box.Volume();
      }
}
```

#### inline 
More like macro in cpp. use inline to reduce the cost of create funciton(maybe in stack). Inline function will do type check. Still cannot add iterate, loop or swtich operation.
Modern complier is not recommend to use inline of macro.

#### class and struct 
Access control. Struct is public and class is private. 

#### Explicit 
To avoid casting directly.
```
class Test1
{
public:
    Test1(int n)            //普通构造函数
    {
        num=n;
    }
private:
    int num;
};

class Test2
{
public:
    explicit Test2(int n)   //explicit(显式)构造函数
    {
        num=n;
    }
private:
    int num;
};

int main()
{
    Test1 t1=12;            //隐式调用其构造函数,成功
    Test2 t2=12;            //编译错误,不能隐式调用其构造函数
    Test2 t2(12);           //显式调用成功
    return 0;
}

```

#### Virtual function (Dynamic linking)
- Normal function cannot be virtual (non-sense)
- Static function (non-sense)
- Inline function (Inline is handled by compiler time(static link), not in same epoch)
- Constructor (Handle object without knowing the details of object)

Usually the virtual function can be used as virtual funciton. (The base class pointer use this to delete attribute.)

#### Smart Pointer 
Smart pointer is actully a class based on RAII. I understand smart pointer as a way of GC in c++ based on RAII.
Use this to manage the life cycle of object. If there is only new and no delete, dangling pointer generates errors. 

c98     auto_ptr
c++11   shared_ptr, weak_ptr, unique_ptr

Shared_ptr
    Popular in use. Use reference counting to locate the life cycle.

#### RTTI (runtime type information)
Get the information of class in runtime.
typeid operator can check the type of object.