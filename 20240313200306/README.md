# Go: path to executable

```
ex, err := os.Executable()
    if err != nil {
        panic(err)
    }
    exPath := filepath.Dir(ex) // get rid of the last part of the path
```
