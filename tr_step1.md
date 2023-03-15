## Golang'da Test yazmak

İlk örnekte Golang kod tabanınızda, iki tamsayı alıp toplamını döndüren basit bir fonksiyonumuz mevcut. Bu fonksiyon için birim testleri yazmak istiyorsunuz ve böylece fonksiyonun doğru çalıştığından emin olmak istiyorsunuz.

Aynı dizindeki fonksiyonunuzla birlikte function_test.go adında yeni bir dosya oluşturabilir ve Golang test paketini kullanarak fonksiyonunuzu test eden bir test fonksiyonu yazabilirsiniz. Verilen örnekten yararlanabilirsiniz:
Go paketini yükleyelim. `apk add go`

Ardından yeni bir Go sayfası oluşturalım. `vim goroutine.go`

Yeni sayfa oluşturduktan sonra komut ekranına aşağıdaki kodu ekleyelim.

package main

import (
"testing"
)

func TestSum(t \*testing.T) {
result := sum(2, 3)
expected := 5
if result != expected {
t.Errorf("Beklenen %d ancak %d alındı.", expected, result)
}
}

Bu örnekte, sum (toplam) fonksiyonunu test ediyoruz ve iki girdi için doğru değeri döndürdüğünü doğruluyoruz.
