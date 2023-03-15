## HTTP Sunucusu için Entegrasyon Testleri Yazma

Bu senaryoda, Golang'da yazılmış bir REST API sunan bir HTTP sunucunuz var ve API'nin doğru çalıştığını doğrulamak için entegrasyon testleri yazmak istiyorsunuz.

HTTP sunucunuz için entegrasyon testleri yazmak istenildiğinde Golang net/http/httptest paketini kullanabilirsiniz. Aşağıda örnek olarak verilen kodu terminal ekranında çalıştırarak test edebilirsiniz:

package main

import (
"net/http"
"net/http/httptest"
"testing"
)

func TestGetUser(t \*testing.T) {
req, err := http.NewRequest("GET", "/users/1", nil)
if err != nil {
t.Fatal(err)
}

    rr := httptest.NewRecorder()
    handler := http.HandlerFunc(GetUserHandler)

    handler.ServeHTTP(rr, req)

    if rr.Code != http.StatusOK {
        t.Errorf("Beklenen durum kodu %d ancak %d alındı.", http.StatusOK, rr.Code)
    }

    // Verify response body
    expected := `{"id":1,"name":"Vakkas Sahin"}`
    if rr.Body.String() != expected {
        t.Errorf("Beklenen yanıt %s ancak %s alındı.", expected, rr.Body.String())
    }

}

Bu örnekte, varsayımsal bir GetUser API uç noktasını test ediyoruz ve belirli bir girdi için doğru durum kodunu ve yanıt gövdesini döndürdüğünü doğrulamış oluyoruz.
