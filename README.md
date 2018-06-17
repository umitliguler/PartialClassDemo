# PartialClassDemo

C# programlarımızda bazı sınıf (class) lar çok fazla sayıda sınıf elemanına sahip olabilir. 
Özellikle büyük projelerde sınıfların karışık yapıda olmasını engellemek için sınıfı belirli parçalara bölmek daha mantıklı bir yol olacaktır. Böylece sınıfın ve projenin görünümü ve yönetimi daha kolay bir hal alacaktır. İşte bu yüzden büyük sınıflarımızı C# taki "partial" anahtar kelimesi yardımıyla parçalara bölebiliriz.
Bunu yapabilmek için parçaya ayırdığımız class ın başına "partial" eklememiz yeterli olacaktır.

**_Aşağıdaki örneğimizde bir adet sınıfımızı mantıklı olacak bir şekilde özellikleri(properties) bir parçada, metotları(methods) da ayrı bir parçada tutarak class ın karışık bir yapıda olması önlenmiş olur ve yönetimi kolaylaşır.
_**
```C#
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
 
namespace PartialClassKavrami
{
    public partial class Sinif
    {
        public string Ozellik1 { get; set; }
        public int Ozellik2 { get; set; }
        public double Ozellik3 { get; set; }
 
        
// dıger ozellikler eklenir...
 
    }
}
```

**_Burada "Sinif" adlı class ımız partial anahtar kelimesi ile bölümlenmiş ve class a ait değişkenler bu parçada tanımlanmışlardır._**

```C#
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
 
namespace PartialClassKavrami
{
    public partial class Sinif
    {
        public void Metot1()
        {
            
// Kodlar...
        }
 
        public void Metot2()
        {
            
// Kodlar...
        }
 
        
// sınıfa ait diğer metotlar eklenir...
    }
}
```
Burada ise yine aynı class a ait metotlar bu sefer farklı bir parçada tutularak özellikler ile birbirine karışması engellenmiş olur.

Partial class kavramı WindowsForms uygulamalarında da karşımıza çıkmaktadır. 
Formun designer bölümü bir parçada kodlama bölümü ise ayrı bir parçada tutularak programcıya kolaylık sağlanmıştır.
Her ne kadar sınıfımız parçaya ayrılmış gibi görünse de program çalıştırıldığında class ımız tek class gibi hareket edecek
ve parçaya ayrılmış olan kodlarımız derlenip program tarafından bir bütün olarak çalıştırılacaktır.
