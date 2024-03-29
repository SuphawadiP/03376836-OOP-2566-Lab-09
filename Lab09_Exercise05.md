# Lab 9 Exercise 5

## Override with `new` keyword
![alt text](./Pictures/image03.png)
1.สร้าง console application project

```cmd
dotnet new console --name Lab09_Ex05
```

2.เปลี่ยน code ให้เป็นดังต่อไปนี้

```cs
SecondDerivedClass sdRef  = new SecondDerivedClass();
BaseClass bcRef = (BaseClass) sdRef;

sdRef.Print();
bcRef.Print();

class BaseClass
{
    virtual public void Print()
    {
        System.Console.WriteLine("Hello from BaseClass");
    }
}
class DerivedClass : BaseClass
{
    override public void Print()
    {
       System.Console.WriteLine("Hello from DerivedClass");
    }
}
class SecondDerivedClass : DerivedClass
{
    new public void Print()
    {
       System.Console.WriteLine("Hello from SecondDerivedClass");
    }
}
```

3.Build project โดยการใช้คำสั่ง

```cmd
dotnet build  Lab09_Ex05
```

ถ้ามีที่ผิดพลาดในโปรแกรม ให้แก้ไขให้ถูกต้อง

4.บันทึกผลที่ได้จากการรันคำสั่งในข้อ 3
<img width="799" alt="Screenshot 2024-03-29 125044" src="https://github.com/SuphawadiP/03376836-OOP-2566-Lab-09/assets/144196049/9324d842-45cb-49ce-9851-dfd3bc286a42">

#### สามารถ Build ได้ เพราะ ใส่ keyword New เข้าไปทำให้สร้างเมทอดในคลาสลูกจะสร้างเมทอดใหม่ที่ไม่ได้ทับเมทอดในคลาสแม่
5.Run project โดยการใช้คำสั่ง

```cmd
dotnet run --project Lab09_Ex05
```

6.บันทึกผลที่ได้จากการรันคำสั่งในข้อ 5
<img width="798" alt="Screenshot 2024-03-29 125123" src="https://github.com/SuphawadiP/03376836-OOP-2566-Lab-09/assets/144196049/ce2c8b39-a3ea-4584-b1fd-aa5ab62c2144">

#### สามารถ Run ได้ปกติ
7.อธิบายสิ่งที่พบในการทดลอง
#### โปรแแกรมจะแสดงผล
#### Hello from SecondDerivedClass
#### Hello from DerivedClass
