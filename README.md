# Powershell Cheat Sheet
Powershell Cheat Sheet

## Değişken Tanımlama


```powershell
# Integer
$sergen = 4

# Float
$sergen = 4.01

# String
$sergen = "sergen string"
$sergen = 'sergen string'

# Array
$sergen = @(1,2,3,4,5)
$sergen = @('sergen','can')

# Hash Table
$sergen=@{
        'sergen'=1
        'can'=2
}

$sergen = @{'sergen'=1}

#Boolean
Dogru = $true
Yanlis = $false

# Byte array
$sergen = [byte[]]@(1,2,3,4,5)

```
# KULLANIM ÖRNEKLERİ
```powershell
# String
PS C:\WINDOWS\system32> $sergen = "sergen string"

PS C:\WINDOWS\system32> $sergen[1]
e

# Array
PS C:\WINDOWS\system32> $sergen=@(1,2,3,4,5)

PS C:\WINDOWS\system32> $sergen[3]
4

# Hash Table

PS C:\WINDOWS\system32> $sergen=@{'sergen'='can'}

PS C:\WINDOWS\system32> $sergen['sergen']
can



```
## Aritmatik Operatörler
```powershell
# TOPLAMA
PS C:\WINDOWS\system32> 1+1
2

# CIKARMA
PS C:\WINDOWS\system32> 1-1
0

# BOLME
PS C:\WINDOWS\system32> 2/2
1

#CARPMA 
PS C:\WINDOWS\system32> 2*2
4
```
## Karşılaştırma Operatörleri ve IF-ELSE yapısı
```powershell
#IF-ELSE YAPISI
if(10 -eq 10){

        Write-Host 'birinci ikinciye esit'

}
elseif(10 -gt 10){
        Write-Host 'birinci ikinciden buyuk'
}
else{
        Write-Host 'ikiside değil'
}


# -eq  => Birinci değerin ikinciye eşit olup olmadığını kontrol eder eşit ise True döner
PS C:\WINDOWS\system32> $sergen='can'

PS C:\WINDOWS\system32> if($sergen -eq 'can'){Write-Host "esit"} else{Write-Host "esit degil"} 
esit

# -ne  => Birinci değerin ikinciye eşit olup olmadığını kontrol eder eşit değil ise True döner
PS C:\WINDOWS\system32> $sergen='can'

PS C:\WINDOWS\system32> if($sergen -ne 'can'){Write-Host "esit degil"} else{Write-Host "esit"} 
esit

# -gt  => Birinci değerin ikinciden büyük olup olmadığını kontrol eder büyük ise True döner
PS C:\WINDOWS\system32> $sergen=1;$can=2

PS C:\WINDOWS\system32> if($sergen -gt $can){Write-Host "birinci buyuk"} else{Write-Host "ikinci buyuk"} 
ikinci buyuk
 
# -lt  => Birinci değerin ikinciden küçük olup olmadığını kontrol eder  küçük ise True döner
PS C:\WINDOWS\system32> $sergen=1;$can=2

PS C:\WINDOWS\system32> if($sergen -lt $can){Write-Host "birinci kucuk"} else{Write-Host "ikinci kucuk"} 
birinci kucuk
     
# -le  => Birinci değerin ikinciden küçük veya eşit olup olmadığını kontrol eder  küçük veya eşit ise True döner

PS C:\WINDOWS\system32> $sergen=5

PS C:\WINDOWS\system32> if($sergen -le 5){Write-Host "kucuk veya esit"} else{Write-Host "buyuk"} 
kucuk veya esit
  
# -ge  => Birinci değerin ikinciden büyük veya eşit olup olmadığını kontrol eder  büyük veya eşit ise True döner
PS C:\WINDOWS\system32> $sergen=5

PS C:\WINDOWS\system32> if($sergen -ge 5){Write-Host "buyuk veya esit"} else{Write-Host "kucuk"} 
buyuk veya esit

  
# -in => Birinci değerin ikinci dizi içinde bulunup bulunmadığını kontrol eder bulunuyorsa True döner
PS C:\WINDOWS\system32> $sergen=@(1,2,3,4,5)

PS C:\WINDOWS\system32> if(1 -in $sergen){Write-Host 'Ikinci birinciyi iceriyor'} else{Write-Host "icermiyor"} 
Ikinci birinciyi iceriyor

# -contains => Birinci dizinin ikinci değeri barındırıp barındırmadığını kontrol eder barındırıyorsa True döner
PS C:\WINDOWS\system32> $sergen=@(1,2,3,4,5)

PS C:\WINDOWS\system32> if($sergen -contains 1){Write-Host 'Birinci ikinciyi iceriyor'} else{Write-Host "icermiyor"} 
Birinci ikinciyi iceriyor


# -match => birinci dize ile dizenin aynı olup olmadigini kontrol eder bulunuyorsa True doner
PS C:\WINDOWS\system32> $sergen='sergen'

PS C:\WINDOWS\system32> if($sergen -match 'sergen'){Write-Host 'Birinci dize ile ikinci dize ayni'} else{Write-Host "ayni degil"} 
Birinci dize ile ikinci dize ayni


# -like => ozel karakterler kullanarak dize icerisinde eslestirme yapar
PS C:\WINDOWS\system32> $sergen='sergen'

PS C:\WINDOWS\system32> if($sergen -like '*se*'){Write-Host 'Ikinci dize birinci icerisinde var'} else{Write-Host "yok"} 
Ikinci dize birinci icerisinde var


# -is => Bir değerin tipini kontrol etmek için kullanılır tipi doğruysa True döner
PS C:\WINDOWS\system32> $sergen='sergen'

PS C:\WINDOWS\system32> if($sergen -is [string]){Write-Host 'Bu bir String'} else{Write-Host "String degil"} 
Bu bir String


# -isnot => Bir değerin tipini kontrol etmek için kullanılır tipi başka ise True döner
PS C:\WINDOWS\system32> $sergen='sergen'

PS C:\WINDOWS\system32> if($sergen -isnot [string]){Write-Host 'String degil'} else{Write-Host "String"} 
String

```
## Mantıksal Operatörler
```powershell

# -and  => Iki veya daha cok kosulun ayni anda gerceklesmesini kontrol eder
PS C:\WINDOWS\system32> $sergen='merhaba'

PS C:\WINDOWS\system32> if($sergen -eq 'naber' -and 1 -eq 1){Write-Host 'merhaba dunya'} else{Write-Host 'olmadi'}
olmadi

# -or  => Herhangi bir kosulun gerceklesmesini kontrol eder
PS C:\WINDOWS\system32> $sergen='merhaba'

PS C:\WINDOWS\system32> if($sergen -eq 'naber' -or 1 -eq 1){Write-Host 'merhaba dunya'}
merhaba dunya


# -not => Kosulun tersini alir
PS C:\WINDOWS\system32> $sergen='merhaba'

PS C:\WINDOWS\system32> if(-not $sergen -eq 'merhaba'){Write-Host 'merhaba dunya'} else{Write-Host 'olmadi'}
olmadi

```
## Döngüler

```powershell
# FOR
PS C:\WINDOWS\system32> for($i=0;$i -lt 3;$i++){Write-Host 'Bu'$i}
Bu 0
Bu 1
Bu 2

# WHILE
PS C:\WINDOWS\system32> $i=0

PS C:\WINDOWS\system32> while($i -lt 3){Write-Host 'Bu'$i;$i++}
Bu 0
Bu 1
Bu 2

# DO-WHILE
PS C:\WINDOWS\system32> $i=0

PS C:\WINDOWS\system32> do{Write-Host 'Bu'$i;$i++} while($i -lt 3)
Bu 0
Bu 1
Bu 2

# FOREACH
PS C:\WINDOWS\system32> $sergen=@(1,2,3,4,5)

PS C:\WINDOWS\system32> foreach($yeni in $sergen){Write-Host 'Bu'$yeni}
Bu 1
Bu 2
Bu 3
Bu 4
Bu 5
```
## Switch-Case yapısı
```powershell

#SWITCH kullanimi
$arac=Read-Host 'Bir Arac Secin:'
switch($arac){
    "Ucak"{
    
        Write-Host 'Bu Ucak'
    }

    "Araba"{
    
        Write-Host 'Bu Araba'
    }
}

#CASLISTIRILMIS KOD
PS C:\WINDOWS\system32> $arac=Read-Host 'Bir Arac Secin:'

switch($arac){

    "Ucak"{
    
        Write-Host 'Bu Ucak'
    }


    "Araba"{
    
        Write-Host 'Bu Araba'
    

    }

}

Bir Arac Secin:: Araba
Bu Araba


```
## Fonksiyonlar
```powershell

function Sergen([int]$param1,[int]$param2){


        $SergenSonuc = $param1-$param2



        return Write-Host $SergenSonuc #return ile değer döndürme
}

Sergen -param1 6 -param2 1 # Fonksiyona parametreleri gönderme
______________________________________________________________________
function Sergen{

        param([int]$param1,[int]$param2) #Parametreleri ve tiplerini tanımlama

        $SergenSonuc = $param1-$param2



        return Write-Host $SergenSonuc #return ile değer döndürme
}

Sergen -param1 6 -param2 1 # Fonksiyona parametreleri gönderme

_______________________________________________________________________

function isimFunc{

    param([string]$isim)
   

    return $isim
}

$yazdir=isimFunc -isim 'Sergen'

Write-Host $yazdir # döndürülen değer bir değiskene atanılarka kullanıldı

```

## Tip Dönüşümü
```powershell
#POWERSHELL'de tip dönüşümleri [] ile yapılır.

# STRING DONUSTURME
______________________________

PS C:\WINDOWS\system32> $sergen=1

PS C:\WINDOWS\system32> $sergen.GetType()

IsPublic IsSerial Name                                     BaseType                           
-------- -------- ----                                     --------                           
True     True     Int32                                    System.ValueType                   



PS C:\WINDOWS\system32> $newSergen=[string]$sergen

PS C:\WINDOWS\system32> $newSergen.GetType()

IsPublic IsSerial Name                                     BaseType                           
-------- -------- ----                                     --------                           
True     True     String                                   System.Object                      


#INT DONUSTURME
______________________________

PS C:\WINDOWS\system32> $SergenDeger=1.0

PS C:\WINDOWS\system32> $SergenDeger.GetType()

IsPublic IsSerial Name                                     BaseType                           
-------- -------- ----                                     --------                           
True     True     Double                                   System.ValueType                   



PS C:\WINDOWS\system32> $SergenINT=[int]$SergenDeger

PS C:\WINDOWS\system32> $SergenINT.GetType()

IsPublic IsSerial Name                                     BaseType                           
-------- -------- ----                                     --------                           
True     True     Int32


# DOUBLE DONUSTURME
______________________________

PS C:\WINDOWS\system32> $SergenINT=[Double]$SergenDeger

PS C:\WINDOWS\system32> $SergenINT.GetType()

IsPublic IsSerial Name                                     BaseType                           
-------- -------- ----                                     --------                           
True     True     Double                                   System.ValueType   


# BOOLEAN DONUSTURME

PS C:\WINDOWS\system32> $SergenINT=[bool]$SergenDeger

PS C:\WINDOWS\system32> $SergenINT.GetType()

IsPublic IsSerial Name                                     BaseType                           
-------- -------- ----                                     --------                           
True     True     Boolean                                  System.ValueType 


# DATETIME DONUSTURME
_________________________________
PS C:\WINDOWS\system32> $SergenDeger='1991-01-01'

PS C:\WINDOWS\system32> $SergenDeger.GetType()

IsPublic IsSerial Name                                     BaseType                           
-------- -------- ----                                     --------                           
True     True     String                                   System.Object                      



PS C:\WINDOWS\system32> $SergenDateTime=[DateTime]$SergenDeger

PS C:\WINDOWS\system32> $SergenDateTime.GetType()

IsPublic IsSerial Name                                     BaseType                           
-------- -------- ----                                     --------                           
True     True     DateTime                                 System.ValueType



# Regex Donusturme
_________________________________

PS C:\WINDOWS\system32> $SergenDeger='\b\d{1}'

PS C:\WINDOWS\system32> $SergenRegex=[regex]$SergenDeger

PS C:\WINDOWS\system32> $SergenRegex.GetType()

IsPublic IsSerial Name                                     BaseType                           
-------- -------- ----                                     --------                           
True     True     Regex                                    System.Object        


# Byte Donusturme

PS C:\WINDOWS\system32> $SergenDeger=64

PS C:\WINDOWS\system32> $SergenByte=[byte]$SergenDeger

PS C:\WINDOWS\system32> $SergenByte.GetType()

IsPublic IsSerial Name                                     BaseType                                
-------- -------- ----                                     --------                                
True     True     Byte                                     System.ValueType      


# Array Donusturme
_________________________________

PS C:\WINDOWS\system32> $SergenDeger='merhaba','sergen'

PS C:\WINDOWS\system32> $SergenArray=[array]$SergenDeger


# Hash Table Donusturme
_________________________________
        
PS C:\WINDOWS\system32> $SergenDeger=@{'Isim'='Sergen'}

PS C:\WINDOWS\system32> $SergenHashTable=[hashtable]$SergenDeger

PS C:\WINDOWS\system32> $SergenHashTable.GetType()

IsPublic IsSerial Name                                     BaseType                                
-------- -------- ----                                     --------                                
True     True     Hashtable                                System.Object 


# Decimal Cevirme
_________________________________
PS C:\WINDOWS\system32> $SergenDeger=1

PS C:\WINDOWS\system32> $SergenDecimal=[decimal]$SergenDeger

PS C:\WINDOWS\system32> $SergenDecimal.GetType()

IsPublic IsSerial Name                                     BaseType                                
-------- -------- ----                                     --------                                
True     True     Decimal                                  System.ValueType    



# PSCUSTUMOBJECT OLUSTURMA(CEVIRME)!!!
_________________________________

# PScustumobject ile bir sinifin altında bulunan degiskenleri nasil o siniftan obje tureterek cagirabiliyorsak, bir hashtable'i bir sinif gibi kullanip bir nesne türetebilir ve icindeki key degerlerini kullanabiliriz.

PS C:\WINDOWS\system32> $SergenDeger=@{'Isim'='Sergen'}

PS C:\WINDOWS\system32> $SergenCustomObject =[PScustomobject]$SergenDeger

PS C:\WINDOWS\system32> $SergenCustomObject.GetType()

IsPublic IsSerial Name                                     BaseType                                
-------- -------- ----                                     --------                                
True     False    PSCustomObject                           System.Object                           



PS C:\WINDOWS\system32> $SergenCustomObject.Isim
Sergen



```
## Class yapısı - OOP

```powershell

PS C:\WINDOWS\system32>

#Sınıf tanımlanması
class SergenSinif{
    [string]$isim  
    [string]$soyisim

# sınıf ile aynı isimde Constructor tanımlanmalı, bu constructora yeni nesne oluşturulurken belirtilen parametreler verilmeli
    SergenSinif([string]$isim,[string]$soyisim){ 
    
        $this.isim=$isim
        $this.soyisim=$soyisim
    }
#Sınıf içinde bir method tanımlanması
    [void]yazdir(){
    
        Write-Host 'Merhaba' $this.isim
        
    }

}
# Bir sınıftan yeni obje üretilmesi
$YeniObje=[SergenSinif]::new("sergen","can")
$YeniObje.yazdir()

Merhaba sergen



__________________________________________________

#CMDLET ile Obje olusturma



PS C:\WINDOWS\system32> class SergenSinif{
    [string]$isim
    [string]$soyisim

    SergenSinif([string]$isim,[string]$soyisim){
    
        $this.isim=$isim
        $this.soyisim=$soyisim
    }

    [void]yazdir(){
    
        Write-Host 'Merhaba' $this.isim
        
    }

}


$YeniObje=New-Object SergenSinif('sergen','can') # New-Object cmdlet ile obje olusturma.
$YeniObje.yazdir()
Merhaba sergen



```
## Powershell Try Catch Finally yapısı
```powershell
TAMAMLANACAK!!!!!
```

## Powershell Ortam Değişkenleri
Kullanışlı bazı ortam değişkenleri
```powershell
# Bilgisayar adını verir
PS C:\WINDOWS\system32> $env:COMPUTERNAME  

# Aktif olarak kullanılan kullanıcıyı verir
PS C:\WINDOWS\system32> $env:USERNAME

# Common Files yolunu verir
PS C:\WINDOWS\system32> $env:CommonProgramFiles
C:\Program Files\Common Files

# Domain veya Workgroup ismini verir
PS C:\WINDOWS\system32> $env:USERDOMAIN

# Varsayılan kullanıcının dosya yolunu verir
PS C:\WINDOWS\system32> $env:HOMEPATH

# Varsayılan kullanıcının AppData klasörünün yolunu verir
PS C:\WINDOWS\system32> $env:APPDATA

# Program Files dosyas yolunu verir
PS C:\WINDOWS\system32> $env:ProgramFiles
C:\Program Files

# Linux üzerindeki $PATH ile aynı işlemi yapar. Aranacak olan program veya dosyaların hangi dizinlerde aranacağını belirtir.
PS C:\WINDOWS\system32> $env:Path

# Varsayılan kullanıcı için local klasörünün yolunu belirtir
PS C:\WINDOWS\system32> $env:LOCALAPPDATA

# Varsayılan kullanıcı için temp klasörünun dosya yolunu belirtir
PS C:\WINDOWS\system32> $env:TEMP

# Cmd.exe yolunu belirtir
PS C:\WINDOWS\system32> $env:ComSpec
C:\WINDOWS\system32\cmd.exe

# Windows klasörünün dosya yolunu belirtir.
PS C:\WINDOWS\system32> $env:windir
C:\WINDOWS

# İşletim sistemini belirtir.
PS C:\WINDOWS\system32> $env:OS
Windows_NT

# Ana diski belirtir.
PS C:\WINDOWS\system32> $env:HOMEDRIVE
C:

# DriverData klasörünün yolunu belirtir.
PS C:\WINDOWS\system32> $env:DriverData
C:\Windows\System32\Drivers\DriverData

# Varsayılan kullanıcı için OneDrive klasörünün yolunu belirtir.
PS C:\WINDOWS\system32> $env:OneDrive

# Bulunulan dosya yolunu verir.
PS C:\WINDOWS\system32> $PWD

Path               
----               
C:\WINDOWS\system32

#ORNEK KULLANIM
PS C:\WINDOWS\system32> Get-Content $env:USERPROFILE\Desktop\ORNEK.txt
Merhaba Sergen

```
## Powershell Bazı Önemli Kullanımlar
```powershell
$_.
TAMAMLANACAK!!!!!
___________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________
# Where-Object cmdletini SQL dilindeki WHERE sorgusu ile aynı işi yapar. Get-Service ile servisler listelenir ve "|" işareti ile Where-Object 'e gönderilir. Burada Name değeri wscsvc olan yakalanır ve Write-Host 'a verilir. Aslında CMDLET kullanarak bir if yapısı oluşturulur.
PS C:\WINDOWS\system32> Get-Service | Where-Object Name -Match wscsvc | Write-Host
wscsvc
___________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________
```
## Powershell Bazı Önemli kullanımlar 
```powershell
# powershell başlangıç parametreleri
powershell -c -enc veya -encodedcommand  # Base64 encoded komut çalıştırma
powershell -w 1 veya -windowstyle hidden
powershell -nop veya noprofile # No profile olarak başlatır
powershell -ep bypass # execution policy bypass eder
Start-Process -NoNewWindow
powershell -NoLogo
powershell -noninteractive




ÖNEMLİ CMDLET
Set(Get-Add-Remove)-MpPreference  #Zararlı yazılım koruma tercihleri ile ilgili işler
Set-ItemProperty # Register kayıt değiştirme
Set-PSSessionConfiguration # Bir powershell session ayarlarını değiştirir
Get-PSSession # Powershell sessionları listeler
New-PSSession # Yeni Powershell session oluşturma
Get-FileHash # Algoritmaya göre dosya hashini getirir
Get-MpPrefrence # Güvenlik seçeneklerini listeler
Get-NetIPAddress # Arayüzleri ve IP adreslerini listeler
Get-SmbShare # SMB paylaşılan dosyalar
Set-LocalUser # Kullanıcı şifresini değiştirmek için kullanulabilir
New-LocalUser # Kullanıcı oluşturmak için kullanılır.
Add-LocalGroupMember # Gruba kullanıcı ekler
Get-Hotfix # Yüklü olan güncellemelerin listesini getirir
Get-WmiObject # Wmi class yapısı kullanarak diğer yapılar hakkında bilgi toplamaya ve incelemeye yarar
Get-WindowsUpdateLog #Windows Update loglarını getirir
Get-Process # Processleri listeler
Get-ScheduledTask # Scheduled taskleri listeler
New-ScheduledTask(action-trigger-settings) # Yeni Scheduled task oluşturur.
Register-SchuduledTask # Oluşturulan taski kayıt eder
Get-NetAdapter # Ağ arayüzlerini listeler
Get-Service # Servisleri listeler
Get-NetFirewallRule # Güvenlik duvarı kurallarını listeler
Get-LocalUser # Local kullanıcıları listeler
Get-LocalGroup # Local grupları listeler
Get-ComputerInfo # Cihaz hakkında bilgi toplamak için kullanılır
Get-Clipboard #Pano içeriğini almak için kullanılır
Get-LocalGroupMember # Yerel bir gruptaki üyeleri listelemek için kullanılır
Get-ItemProperty # Kayıt defteri için Query oluşturmamıza yarar
New-Item #yeni bir register kaydı veya dosya oluşturmamıza yarar
Get-ChildItem # alt dosya ve dizinleri listeler
Get-Content # cat komutu ile aynı
Get-Eventlog # event logları getirir
New-Object # bir class'dan nesne oluşturabiliriz
Import-Module # Module yüklemek için kullanılır, bir modul yüklediğimiz zaman bunun içerisindeki özel CMDLETleri kullanabiliriz (ÖRNEK Powersploit)
Invoke-WebRequest(iwr) # Internetten dosya indirmemize (istek yapmamıza yardımcı olur)
Invoke-Expression(iex) # Bir stringi komut olarak çalıştırmaya yarar
Get-WinEvent #Olay günlüğü verilerini almak için kullanılır
ConvertTo-* ve ConvertFrom-* # Bir şeyi başka bir yapıya çevirmeye yarar
Move-Item # Dosya taşıma
Copy-Item # Dosya kopyalama
Remove-Item # Dosya kaldırma
Stop-Service # Servis durdurur
Start-Service # Servis başlatır
Start-Process # Bir işlem başlatır
Stop-Process # Bir işlemi durdurur
Select-Object # Linux Select ile aynı bir objeyi filtrelememizi sağlar
___________________________________________________________________________________________________________

WMI ORNEK > Get-WmiObject -Class Win32_PnPEntity | Select-Object Name # Bu yapı cihaz üzerinde takılı sanal ve gerçek şeylerin isimlerini gösterir.
___________________________________________________________________________________________________________

Set-MpPreference Kullanımları
TAMAMLANACAK!!!!!


```

## Powershell Obfusaction Teknikleri
```powershell
# String birleştirme
PS C:\WINDOWS\system32>  ('s'+'er'+'gen')
sergen
_______________________________________________________________________________________________________
# Format String Kullanımı
PS C:\WINDOWS\system32> '{1}{0}' -f 'can','sergen'
sergencan
_______________________________________________________________________________________________________
# Backtick kullanımı 
PS C:\WINDOWS\system32> "TC`p`C`liEnt"
TCpCliEnt
_______________________________________________________________________________________________________
# Bir fonksiyonu string olarak bir değişkene atama ve değişkeni fonksiyon olarak kullanma
PS C:\WINDOWS\system32> $merhabastr="merhaba"

PS C:\WINDOWS\system32> $merhabastr.GetType()

IsPublic IsSerial Name                                     BaseType                           
-------- -------- ----                                     --------                           
True     True     String                                   System.Object                      


PS C:\WINDOWS\system32> $New='GetType'

PS C:\WINDOWS\system32> $merhabastr.$NEW()

IsPublic IsSerial Name                                     BaseType                           
-------- -------- ----                                     --------                           
True     True     String                                   System.Object        
_______________________________________________________________________________________________________

# CMDLET değişken atama
PS C:\WINDOWS\system32> $new="Get-LocalGroup"

PS C:\WINDOWS\system32> iex($new)

Name                                       Description                                        
----                                       -----------                                        
__vmware__                                 VMware User Group                                  
Administrators                             Yöneticilerin bilgisayar/etki alanına tam ve sın...
Backup Operators                           Yedek İşletmenler, yalnızca dosya yedeklemek ya ...
Cihaz Sahipleri                            Bu grubun üyeleri sistem genelindeki ayarları de...
_______________________________________________________________________________________________________





```
