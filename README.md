# dpt-shell

[![](https://img.shields.io/github/license/luoyesiqiu/dpt-shell)](https://github.com/luoyesiqiu/dpt-shell/blob/main/LICENSE) [![](https://img.shields.io/github/downloads/luoyesiqiu/dpt-shell/total?color=blue)](https://github.com/luoyesiqiu/dpt-shell/releases/latest) [![](https://img.shields.io/github/issues-raw/luoyesiqiu/dpt-shell?color=red)](https://github.com/luoyesiqiu/dpt-shell/issues) ![](https://img.shields.io/badge/Android-5.0%2B-brightgreen)

English | [简体中文](./README.zh-CN.md) 

dpt-shell, Android Dex metot uygulamalarını boşaltıp çalışma zamanında yeniden oluşturan bir Android Dex koruma kabuğudur.

## Kullanım

### Hızlı kullanım

[Sürümler](https://github.com/luoyesiqiu/dpt-shell/releases/latest) adresine gidin, `executable.zip` dosyasını indirin ve açın, terminalde aşağıdaki komut satırlarını çalıştırın:

```shell
java -jar dpt.jar -f /path/to/android-package-file
```

### Manuel derlemeler
```shell
git clone --recursive https://github.com/luoyesiqiu/dpt-shell
cd dpt-shell
./gradlew assemble
cd executable
java -jar dpt.jar -f /path/to/android-package-file
```

### Komut satırı seçenekleri

```text
usage: java -jar dpt.jar [option] -f <package_file>
 -c,--protect-config <arg>   Protect config file.
                             
    --debug                 Paketi hata ayıklanabilir hale getirin.
    --disable-acf            Uygulama bileşeni fabrikasını devre dışı bırakın (sadece hata ayıklama için kullanın).
    --disable-anti-debug     Çalışma zamanı hata ayıklama önleme özelliğini devre dışı bırakın.
    --disable-crc-detect     Çalışma zamanında libc .text CRC tespitini devre dışı bırakın.
                             
    --disable-frida-detect   Çalışma zamanında Frida algılamasını devre dışı bırakın.
                             
    --dump-code              DEX kodunun içeriğini çıkarın ve .json dosyalarına kaydedin.
.json dosyalarına kaydedin.
 -e,--exclude-abi <arg>     Belirli ABI'leri hariç tutun (virgülle ayrılmış, örneğin:
x86,x86_64).
                            Desteklenen ABI'ler:
                             - arm       (armeabi-v7a)
                             - arm64     (arm64-v8a)
                             - x86
                             - x86_64
 -f,--package-file <arg>     Android paket dosyalarını (*.apk, *.aab) korumak gerekiyor.
 -K,--keep-classes           Bazı sınıfları paket içinde tutmak,
uygulamanın başlatma hızını belirli bir ölçüde iyileştirebilir,
ancak bazı uygulama paketleri bunu desteklemez.
    --noisy-log              Gürültülü günlüğü açın.
 -o,--output <arg>           Korunan paketin çıktı dizini.
 -r,--rules-file <arg>       Korunmayacak sınıf adları için kurallar dosyası.
 -S,--smaller                Uygulamanın performansından biraz ödün vererek,
daha küçük bir uygulama boyutu elde edin.
 -v,--version                Programın sürüm numarasını göster.
 -vs,--verify-sign           Çalışma zamanı uygulama imza doğrulamasını etkinleştirin.

Sertifikanın SHA-256 değeri,
imzalama anahtar deposundan otomatik olarak hesaplanır.
 -x,--no-sign               Paketi imzalamayın.
```

## Uyarı

Bu projede çok fazla test bulunmamaktadır, üretim ortamında kullanırken dikkatli olun. Aksi takdirde, tüm sonuçlardan siz sorumlu olursunuz.

## Bağımlılıklar veya kullanım, proje kodunu takip eder.

- [dx](https://android.googlesource.com/platform/dalvik/+/refs/heads/master/dx/)
- [Dobby](https://github.com/jmpews/Dobby)
- ~~[libzip-android](https://github.com/julienr/libzip-android)~~
- [ManifestEditor](https://github.com/WindySha/ManifestEditor)
- ~~[Xpatch](https://github.com/WindySha/Xpatch)~~
- [bhook](https://github.com/bytedance/bhook)
- [zipalign-java](https://github.com/Iyxan23/zipalign-java)
- [minizip-ng](https://github.com/zlib-ng/minizip-ng)
- [JSON-java](https://github.com/stleary/JSON-java)
- [zip4j](https://github.com/srikanth-lingala/zip4j)
- [commons-cli](https://github.com/apache/commons-cli)
- [dexmaker](https://android.googlesource.com/platform/external/dexmaker)
- [Obfuscate](https://github.com/adamyaxley/Obfuscate)
