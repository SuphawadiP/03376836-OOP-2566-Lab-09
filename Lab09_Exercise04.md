# Lab 9 Exercise 4

## Override overridden Method
![alt text](./Pictures/image02.png)
1.สร้าง console application project

```cmd
dotnet new console --name Lab09_Ex04
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
    public void Print()
    {
       System.Console.WriteLine("Hello from SecondDerivedClass");
    }
}
```

3.Build project โดยการใช้คำสั่ง

```cmd
dotnet build  Lab09_Ex04
```

ถ้ามีที่ผิดพลาดในโปรแกรม ให้แก้ไขให้ถูกต้อง

4.บันทึกผลที่ได้จากการรันคำสั่งในข้อ 3
<img width="800" alt="Screenshot 2024-03-29 124710" src="https://github.com/SuphawadiP/03376836-OOP-2566-Lab-09/assets/144196049/97bba815-33f9-4224-9d79-7cb2fa0664ef">

#### สามารถ Build ได้เเละมีการเเจ้งwarning แต่ ไม่ได้ใช้คีย์เวิร์ด override เพื่อระบุว่าเมทอดนั้นกำลังทับเมทอดในคลาสแม่ หรือ BaseClass
5.Run project โดยการใช้คำสั่ง

```cmd
dotnet run --project Lab09_Ex04
```

6.บันทึกผลที่ได้จากการรันคำสั่งในข้อ 5
<img width="797" alt="Screenshot 2024-03-29 124748" src="https://github.com/SuphawadiP/03376836-OOP-2566-Lab-09/assets/144196049/088061fd-7f91-450c-aad8-c43176047a8d">

#### สามารถ Run ได้ ปกติ
7.อธิบายสิ่งที่พบในการทดลอง
##### โปรแกรมจะแสดงผล
#### Hello from SecondDerivedClass
#### Hello from DerivedClass
