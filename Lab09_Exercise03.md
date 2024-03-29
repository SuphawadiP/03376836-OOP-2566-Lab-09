# Lab 9 Exercise 3

## Override overridden Method
![alt text](./Pictures/image01.png)

1.สร้าง console application project

```cmd
dotnet new console --name Lab09_Ex03
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
    override public void Print()
    {
       System.Console.WriteLine("Hello from SecondDerivedClass");
    }
}
```

3.Build project โดยการใช้คำสั่ง

```cmd
dotnet build  Lab09_Ex03
```

ถ้ามีที่ผิดพลาดในโปรแกรม ให้แก้ไขให้ถูกต้อง

4.บันทึกผลที่ได้จากการรันคำสั่งในข้อ 3
<img width="792" alt="Screenshot 2024-03-29 124347" src="https://github.com/SuphawadiP/03376836-OOP-2566-Lab-09/assets/144196049/096b5f9c-eb72-44c2-8dbf-c322f9d8f566">

#### สามารถ Build ได้ เพราะ สร้างคลาส BaseClass, DerivedClass และ SecondDerivedClass ซึ่งมีการสืบทอดกันเป็นลำดับ โดย DerivedClass สืบทอดมาจาก BaseClass และ SecondDerivedClass สืบทอดมาจาก DerivedClass
5.Run project โดยการใช้คำสั่ง

```cmd
dotnet run --project Lab09_Ex03
```

6.บันทึกผลที่ได้จากการรันคำสั่งในข้อ 5
<img width="800" alt="Screenshot 2024-03-29 124420" src="https://github.com/SuphawadiP/03376836-OOP-2566-Lab-09/assets/144196049/c8a7785a-e9da-4599-95d0-a57a1236eebc">

#### สามารถ Run ได้ เพราะ เรียกเมทอด Print() เรียกบนอ็อบเจกต์ของคลาส SecondDerivedClass ซึ่่ง ผลลัพธ์จากเมทอดที่ถูกโอเวอร์ไรด์ในคลาส SecondDerivedClass
7.อธิบายสิ่งที่พบในการทดลอง
#### โปรแกรมจะแสดงผล
#### Hello from SecondDerivedClass
#### Hello from SecondDerivedClass
