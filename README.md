# pythonoopnote

Object-Oriented Programming in Python, or OOP for short, is a programming paradigm that combines data and operations in programming. This refers to an approach that helps make programs more modular, organizable and reusable.

# Python OOP Notes

Bu depo, Python'da Nesne Yönelimli Programlama (OOP) üzerine notları içermektedir. OOP, nesneleri ve sınıfları kullanarak kodu yapılandıran bir programlama paradigmadır. İşte temel kavramların özeti:

## Sınıflar ve Nesneler

- **Sınıf:** Belirli bir türdeki tüm nesneler için ortak olan özellikleri (nitelikler) ve davranışları (metodlar) tanımlayan bir şablondur.
  
  ```python
  class Araba:
      def __init__(self, marka, model):
          self.marka = marka
          self.model = model

# Nesne: Bir sınıfın örneğidir. Belirli bir sınıftan türetilen bir nesne, o sınıfın özelliklerini ve metodlarını içerir.

araba1 = Araba("Toyota", "Corolla")

# Nitelikler ve Metodlar

Nitelikler: Veriyi saklayan değişkenlerdir. Her nesnenin kendi nitelik kümesi vardır.
print(araba1.marka)  # Çıktı: Toyota

Metodlar: Nesneler üzerinde çalışan fonksiyonlardır. Nesnelerin davranışlarını tanımlarlar.

class Kedi:
    def miyavla(self):
        return "Miyav!"

benim_kedim = Kedi()
print(benim_kedim.miyavla())  # Çıktı: Miyav!

# Kalıtım
Bir sınıfın (alt sınıf/çocuk) başka bir sınıftan (üst sınıf/ebeveyn) özellikleri ve metodları miras almasını sağlar.

class ElektrikliAraba(Araba):
    def __init__(self, marka, model, pil_kapasitesi):
        super().__init__(marka, model)
        self.pil_kapasitesi = pil_kapasitesi

# Polimorfizm
Farklı sınıfların aynı metodunu farklı şekillerde uygulamasına olanak tanır.

class Kus:
    def ses_cikar(self):
        pass

class Karga(Kus):
    def ses_cikar(self):
        return "Çağrışım"

class Serce(Kus):
    def ses_cikar(self):
        return "Cıvıldama"

kus1 = Karga()
kus2 = Serce()

print(kus1.ses_cikar())  # Çıktı: Çağrışım
print(kus2.ses_cikar())  # Çıktı: Cıvıldama

# Kapsülleme
Veriyi (nitelikler) ve veri üzerinde çalışan metodları bir araya getirerek tek bir birimi (sınıf) oluşturur.

class BankaHesabi:
    def __init__(self):
        self.bakiye = 0

    def para_yatir(self, miktar):
        self.bakiye += miktar

    def para_cek(self, miktar):
        if miktar <= self.bakiye:
            self.bakiye -= miktar
        else:
            print("Yetersiz bakiye.")

