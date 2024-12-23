![image](https://github.com/Independent-Society-of-Knowledge/Kompute/assets/76442288/3c1c723a-6ba8-407d-9dfa-407ffbf9bf87)

# Kompute README

## Overview

**Kompute** is the core computational engine of the Kotlin-For-Science ecosystem. It provides the fundamental numerical primitives and interfaces with high-performance C/C++ libraries to perform scientific computations efficiently. By leveraging Kotlin's expressive syntax, functional programming features, and native interoperability, Kompute enables a high-performance and type-safe environment for scientific research and computations.

Kompute is modular and lightweight, offering optimized, type-safe, and immutable constructs for array handling, computations, and more. It is designed to seamlessly integrate with domain-specific libraries built on top of it, such as `LinAlgebra`, `DifferentialSolvers`, `OptiK`, and others, forming a robust scientific computation ecosystem.

## Key Features

- **Efficient Computational Engine**: Kompute provides a high-performance backend that handles numerical operations efficiently using precompiled C/C++ bindings (e.g., BLAS, LAPACK, FFTW).
- **Immutable and Type-Safe**: Data structures and operations are designed to be immutable and type-safe, providing predictability and minimizing errors.
- **Interoperability with C/C++**: Kompute integrates seamlessly with high-performance C/C++ libraries, making it possible to execute heavy computations without sacrificing performance.
- **Modular Architecture**: Kompute serves as the foundation for a modular ecosystem, allowing users to build specialized tools for their specific needs (e.g., linear algebra, optimization, differential equations) without unnecessary dependencies.
- **Multi-threaded Support**: Kompute supports multi-threading for concurrent computations, optimizing performance across multiple CPU cores.

## Installation

### Requirements

- Kotlin 1.8+ 
- JDK 11+
- C/C++ compilers for native bindings
- `gradle` for building

### Gradle Dependency

To use Kompute in your Kotlin project, add the following to your `build.gradle.kts` file:

```kotlin
dependencies {
    implementation("com.iskportal:kompute:1.0.0")
}
```

Replace `1.0.0` with the latest version of Kompute.

## Usage

Kompute provides basic functionalities such as array creation, element-wise operations, matrix operations, and more. Below is a simple example of how to perform basic array operations using Kompute:

### Example: Creating and manipulating arrays

```kotlin
import com.kotlinforscience.kompute.*

fun main() {
    // Create a 1D array
    val array1 = KomputeArray(10)
    array1.fill { it.toDouble() }

    // Create another array and add it element-wise to array1
    val array2 = KomputeArray(10)
    array2.fill { it * 2.0 }

    // Perform element-wise addition
    val result = array1 + array2

    println("Result: $result")
}
```

### Example: Matrix Operations

```kotlin
import com.kotlinforscience.kompute.*

fun main() {
    // Create a 3x3 matrix
    val matrix1 = KomputeMatrix(3, 3)
    matrix1.fill { row, col -> row.toDouble() + col.toDouble() }

    // Create another matrix
    val matrix2 = KomputeMatrix(3, 3)
    matrix2.fill { row, col -> (row + 1).toDouble() * (col + 1).toDouble() }

    // Perform matrix multiplication
    val result = matrix1 * matrix2

    println("Matrix multiplication result: $result")
}
```

Kompute provides operators and functions for various mathematical operations on arrays and matrices, including addition, multiplication, transposition, and more.

## Performance and Optimization

Kompute automatically uses precompiled C/C++ libraries for optimized mathematical operations. By linking to widely-used libraries such as BLAS and LAPACK, Kompute ensures that computations are fast and scalable. You do not need to worry about manually configuring these bindings, as Kompute handles it internally.

### Memory Management

Kompute uses Kotlin's native memory management features and integrates with optimized C/C++ memory allocations, ensuring efficient memory usage during computations.

## Documentation

- **API Documentation**: The full API documentation is available on [Kotlin-For-Science Docs](https://kotlinforscience.com/docs).
- **Tutorials and Guides**: Step-by-step tutorials are available for getting started with Kompute, as well as advanced use cases. Visit the [Kotlin-For-Science Tutorials](https://kotlinforscience.com/tutorials) to explore further.
- **Example Projects**: Example projects using Kompute are available in the `examples` directory in the repository. These examples showcase a variety of use cases from basic array operations to complex numerical simulations.

## Contributing

We welcome contributions to Kompute! If you're interested in improving the engine, optimizing performance, or adding new features, feel free to submit a pull request. Before contributing, please make sure to:

1. Fork the repository and clone it to your local machine.
2. Run the tests to ensure that everything works as expected.
3. Add or modify code with a focus on modularity and performance.
4. Follow the project's coding guidelines and write clear, concise documentation.

If you encounter any issues or have suggestions, feel free to open an issue on the [GitHub Issues Page](https://github.com/KotlinForScience/Kompute/issues).

## License

Kompute is released under the [Apache License 2.0](https://www.apache.org/licenses/LICENSE-2.0).

## Acknowledgments

Kompute relies on several powerful C/C++ libraries for its numerical computations, including:

- BLAS (Basic Linear Algebra Subprograms)
- LAPACK (Linear Algebra PACKage)
- FFTW (Fast Fourier Transform in the West)

We thank the maintainers of these libraries for their contributions to the scientific computing community.

---

For more information and to explore the Kotlin-For-Science ecosystem, visit [KotlinForScience.com](https://kotlin.iskportal.com).
