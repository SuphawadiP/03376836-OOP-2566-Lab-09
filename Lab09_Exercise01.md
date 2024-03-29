# Lab 9 Exercise 1

## Polymorphism (virtual-override methods)

1.สร้าง console application project

```cmd
dotnet new console --name Lab09_Ex01
```

2.เปลี่ยน code ให้เป็นดังต่อไปนี้

```cs
DerivedClass dcRef = new DerivedClass();
BaseClass bcRef = new BaseClass();

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
dotnet build  Lab09_Ex01
```

ถ้ามีที่ผิดพลาดในโปรแกรม ให้แก้ไขให้ถูกต้อง

4.บันทึกผลที่ได้จากการรันคำสั่งในข้อ 3
<img width="797" alt="Screenshot 2024-03-29 123325" src="https://github.com/SuphawadiP/03376836-OOP-2566-Lab-09/assets/144196049/71f0168f-49c1-49dc-9d82-8877b755e593">

#### สามารถ Build ได้ เพราะ virtual: ใช้บอกว่าเมทอดสามารถถูกโอเวอร์ไรด์ได้ในคลาสที่สืบทอด คือ Info override: ใช้ในคลาสที่สืบทอดเพื่อโอเวอร์ไรด์เมทอดที่ถูกประกาศเป็น virtual ในคลาสฐาน
5.Run project โดยการใช้คำสั่ง

```cmd
dotnet run --project Lab09_Ex01
```

6.บันทึกผลที่ได้จากการรันคำสั่งในข้อ 5
<img width="796" alt="Screenshot 2024-03-29 123453" src="https://github.com/SuphawadiP/03376836-OOP-2566-Lab-09/assets/144196049/05e98ae4-7749-48be-914a-5f5f6ecd3d9b">

#### สามารถ Run ได้ เพราะ Info ถูกประกาศเป็น virtual สามารถถูก override ได้ในคลาสที่สืบทอด
7.อธิบายสิ่งที่พบในการทดลอง
#### โปรแกรมจะแสดงผล
#### This is DerivedClass
#### This is BaseClass
