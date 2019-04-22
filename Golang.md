# Golang

## Random Snippets

1. Generics

Creating functions with generic/abstract parameters using `interface{}`
```go
func Introduce(entity interface{}) {
    fmt.Println("Hello, I am", entity) // no casting
    p := entity.(Person)
    fmt.Println("Hello, I am", p.Name, p.FamilyName) // casted
}
```
Using generic arrays. There is no need of `[]interface{}` in the function parameters.
```go
func IntroduceMany(many interface{}) {
	data := many.([]Person) // casting to an array of People
	for _, p := range data {
		fmt.Println("Hello, I am", p.Name, p.FamilyName)
	}
}
```

2. WIP Reflections
```go
// NOTE WIP
func InterfaceSlice(slice interface{}) []interface{} {
    s := reflect.ValueOf(slice)
    if s.Kind() != reflect.Slice {
        panic("InterfaceSlice() given a non-slice type")
    }
}
```