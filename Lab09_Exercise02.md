# Lab 9 Exercise 2

## virtual-override methods

1.สร้าง console application project

```cmd
dotnet new console --name Lab09_Ex02
```

2.เปลี่ยน code ให้เป็นดังต่อไปนี้

```cs
DerivedClass dcRef = new DerivedClass();
BaseClass bcRef =  (BaseClass) dcRef;

dcRef.Info();
bcRef.Info();

class BaseClass
{
    virtual public void Info()
    {
        System.Console.WriteLine("This is BaseClass");
    }
}

class DerivedClass : BaseClass
{
    override public void Info()
    {
        System.Console.WriteLine("This is DerivedClass");
    }
}
```

3.Build project โดยการใช้คำสั่ง

```cmd
dotnet build  Lab09_Ex02
```

ถ้ามีที่ผิดพลาดในโปรแกรม ให้แก้ไขให้ถูกต้อง

4.บันทึกผลที่ได้จากการรันคำสั่งในข้อ 3
<img width="798" alt="Screenshot 2024-03-29 123846" src="https://github.com/SuphawadiP/03376836-OOP-2566-Lab-09/assets/144196049/4f1620a9-c293-4704-b8cd-6bdbad0de989">

#### สามารถ Build ได้ เพราะ มีการสร้างคลาสที่สืบทอด จากคลาสอื่น ๆ และโอเวอร์ไรด์เมทอดในคลาสที่สืบทอดนั้น
5.Run project โดยการใช้คำสั่ง

```cmd
dotnet run --project Lab09_Ex02
```

6.บันทึกผลที่ได้จากการรันคำสั่งในข้อ 5
<img width="795" alt="Screenshot 2024-03-29 123920" src="https://github.com/SuphawadiP/03376836-OOP-2566-Lab-09/assets/144196049/b3595edd-73df-4681-bea2-f399ba69a6b5">

#### สามารถ Run ได้ เพราะ dcRef.Info() จะเรียกใช้เมทอด Info() จากคลาสที่สืบทอด (DerivedClass) และ bcRef.Info() จะเรียกใช้เมทอด Info() จากคลาสฐาน (BaseClass)
7.อธิบายสิ่งที่พบในการทดลอง
#### โปรแกรมจะแสดงผล
#### This is DerivedClass
#### This is DerivedClass
