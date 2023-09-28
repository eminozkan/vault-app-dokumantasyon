# 1- Secrets Nedir?

- Secrets(Hassas veriler), çeşitli siber güvenlik önlemleriyle korunması gereken ve ayrıcalıklı erişim izni tanımlanmadıkça yetkisiz kişilerin ve üçüncü parti bileşenlerin erişemeyeceği sınıflandırılmış veriler olarak tanımlanabilir. 

- Bizim konumuzda ise API Token, Database Credentials, Username& Password ve TLS Sertifikaları gibi bileşenlerden bahsediyor olacağız.

- Secrets ismini verdiğimiz bilgilerin nerelerde olduğunu bilmeden, dağınık şekilde çeşitli yerlerde bulunabilmesi Secret Sprawl problemini oluşturur.

# 2 - Secret Sprawl Problemi Nedir?

- Secrets bilgilerinin kaynak kodu, config dosyası, versiyon kontrol sistemleri(Github,Gitlab) içerisinde bulunabilmesi bir sorundur.
    1. İlk olarak bu bilgilerin tam olarak nerede olduğu hakkında bir bilgiye sahip olamayız.
    2. İkinci olarak, bu bilgiler üzerinde bir kontrol sahibi değiliz ve Wiki, Github gibi kaynaklar bu bilgileri saklamaya elverişli bir platform değildir.
    3. Üçüncü olarak ise, bu bilgilerin dışarıya sızdığında ne yapacağımız hakkında bilgimiz yoktur. Örneğin internette database'imiz ile ilgili bir bilgiye rastladığımızda; bu bilgiyi nereden sızdırdığımızı bilemeyiz.

## Çözüm :

Bu sorunu çözmek için aklımıza gelen ilk çözüm yöntemi ise bu bilgileri merkezileştirip şifreli şekilde tek bir noktada barıdırmaktır. Ancak bu durumda da Secrets dediğimiz bilgilere kimlerin eriştiğini, bu bilgiye sahip olanların kullanıp kullanmadığını bilemeyiz.

Tüm bu sorunların çözümü için [HashiCorp](https://www.hashicorp.com/) tarafından geliştirilmiş olan [Vault](https://www.vaultproject.io/) uygulamasını kullanabiliriz.