# Expression System (KES)

Kompute uses a set of classes, dataclasses, interfaces and types to enhance writing mathematical object in Kotlin. 

```kotlin
sealed interface Expression {
    fun internalEvaluation(): Expression
    fun toKotlinPrimitiveTypes(): T
} 
```