# Go: File / Directory exists

# File 

```
import (
    "log"
    "os"
)

func main() {
    fileinfo, err := os.Stat("temp.txt")
    if os.IsNotExist(err) {
        log.Fatal("File does not exist.")
    }
    log.Println(fileinfo)
}
```

# Directory

```
import (
    "log"
    "os"
)

func main() {
    folderInfo, err := os.Stat("temp")
    if os.IsNotExist(err) {
        log.Fatal("Folder does not exist.")
    }
    log.Println(folderInfo)
}
```
