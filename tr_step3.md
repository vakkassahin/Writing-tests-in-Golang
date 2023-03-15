## Bir işlev (benchmark) için Performans Testi yazma

Bu senaryoda, Golang kod tabanınızda işlemci yoğun bir görevi yerine getiren bir işleviniz var. Bu işlevin performansını ölçmek için performans testleri yazmak istiyorsunuz.

Golang test paketinin performans testi özelliğini kullanarak, işleviniz için performans testleri yazabilirsiniz. İşte bir örnek:

package main

import (
"testing"
)

func BenchmarkFunction(b \*testing.B) {
for i := 0; i < b.N; i++ {
// İşlevinizi burada calıstırın
}
}

Bu örnekte, BenchmarkFunction test işlevini kullanarak, işlevimizi birden çok kez çalıştırıyor ve performansını testing.B nesnesini kullanarak ölçüyoruz.
