# go-lingual v1.0.0

Ini adalah module bahasa pemrograman go sederhana untuk mengkonfigurasikan tampilan 
pesan ke dalam multi bahasa.

### instalasi
`go get github.com/michaelwp/linggo` atau
`go get github.com/michaelwp/linggo@v1.0.0`

### contoh penggunaan
A. Buat Json file untuk menampung bahasa yang digunakan
- id.json (bahasa Indonesia)
```json 
    {
      "hello world": "halo dunia"
    }
```
- en.json (bahasa Inggris)
```json 
    {
      "hello world": "hello world"
    }
```
- fr.json (bahasa Prancis)
```json 
    {
      "hello world": "Bonjour le monde"
    }
```
- en.json (bahasa China)
```json 
    {
      "hello world": "你好，世界"
    }
```
B. import file ke dalam golang file
- main.go
```go 
    package main
    
    import (
        "github.com/michaelwp/linggo"  // import linggo package
        "log"
    )
    
    func main(){
        // contoh translate ke dalam bahasa China
        msg, err := linggo.Tr("ch", "hello world")
        // handle error (disarankan untuk menghandle error dengan cara yang lebih baik)
        if err != nil {
            log.Fatal(err)
        }
        // menampilkan hasil ke layar
        log.Println(msg)
    }
```
#### hasil
```text
    你好，世界
```


