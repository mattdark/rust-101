![](img/rust-logo.png)
<!-- .element: style="margin-top: -5%;" -->
## Rust 101

#### [Mario Garcia](https://mariog.xyz) · [@mariogmd](https://twitter.com/mariogmd)

---

## What is Rust?

----

### A systems programming language focus on:

<br>

<span class="fragment">safety</span><span class="fragment">, speed</span><span class="fragment">, and concurrency.</span>

<!-- .element: class="fragment" -->

----

## Characteristics

- Compiled language
- Support for multiple OSs and hardware architectures<!-- .element: class="fragment" -->
- Integration with other languages<!-- .element: class="fragment" -->

---

## Installation

### Linux or Mac:

```
  $ curl https://sh.rustup.rs -sSf | sh
```

----

### Other OSs

Download from https://rustup.rs/

---

## Tools

---

## rustup

----

###  rustup is an installer for the systems programming language Rust 

----

### Versions of Rust

- Stable (1.31.1)
- Beta<!-- .element: class="fragment" -->
- Nightly<!-- .element: class="fragment" -->

----

### Install

```
  $ rustup install nightly
```

----

### Update

```
  $ rustup update
```

----

### Set default

```
  $ rustup default nightly
```

----

### Set default for a project

```
rustup override set nightly
```

---

## rustc

----

### main.rs

```
  fn main() {
      println!("Hello, world!");
  }
```

----

### Running

```
  $ rustc main.rs
  $ ./main
  Hello, world!
```

---

![](img/cargo-logo.png)

## Cargo

----

### Cargo is Rust’s build system and package manager.

---

## New project with Cargo

```
  $ cargo new hello_world
```

----

```
  ~/hello_world$ ls -a
  Cargo.toml src .git .gitignore
```

---

## Cargo.toml

```
  [package]
  name = "hello_world" # the name of the package
  version = "0.1.0"    # the current version
  authors = ["mattdark"] # author

  [dependencies]
```

---

## src/main.rs

```
  fn main() {
      println!("Hello, world!");
  }
```

---

## Build & Run

```
  $ cargo build #Optional
  $ cargo run
```

---

## Rust Sintax

---

## Print text

```
  println!("string {} literal", expressions);
```

----

```
  fn main() {
      println!("Hello, {}!", "world");
  }
```

----

## Comments

```
  // This is a comment
```

---

## variables

```
  let name = expression;
```

----

## Example

```
  fn main () {
      let a = 7;
      let b = 8;
      println!("The sum is: {}", a+b);
  }
```

---

## Constants

```
  const NAME: type = expression;
```

----

## Example

```
  fn main() {
      const A: i32 = 7;
      const B: i32 = 8;
      print!("The sum is: {}", A + B);
  }
```

---

## Mutability

----

```
  fn main() {
      let x = 5;
      println!("The value of x is: {}", x);
      x = 6;
      println!("The value of x is: {}", x);
  }
```

----

```
  let mut nombre = expression;
```

----

```
  fn main() {
      let mut x = 5;
      println!("The value of x is: {}", x);
      x = 6;
      println!("The value of x is: {}", x);
  }
```

---

## Primitive Types

---

## Numeric Types

- i8, i16, i32, i64
- u8, u16, u32, u64<!-- .element: class="fragment" -->
- isize, usize<!-- .element: class="fragment" -->
- f32, f64<!-- .element: class="fragment" -->

----

```
  let x = 42; // x has type i32
  let y = 1.0; // y has type f64
```

---

## Numeric operations

```
  fn main() {
      // addition
      let sum = 5 + 10;
      // subtraction
      let difference = 95.5 - 4.3;
      // multiplication
      let product = 4 * 30;
      // division
      let quotient = 56.7 / 32.2;
      // remainder
      let remainder = 43 % 5;
  }
```

---

## Char

```
  let x: char = 'x';
```

---

## Boolean

```
  let x = true;
  let y: bool = true;
```

---

## Decision making

```
  if condicion {
      expressions;
  }
  else {
      expressions;
  }
```

----

## Example

### if ... else

```
  fn main() {
      let a = 8;
      let b = 12;
      if a > b {
          println!("{} > {}", a, b);
      }
      else {
          println!("{} > {}", b, a);
      }
  }
```

----

### else if

```
  fn main() {
      let number = 6;

      if number % 4 == 0 {
          println!("number is divisible by 4");
      } else if number % 3 == 0 {
          println!("number is divisible by 3");
      } else if number % 2 == 0 {
          println!("number is divisible by 2");
      } else {
          println!("number is not divisible by 4, 3, or 2");
      }
  }
```

---

### Tuples

```
  let tup: (i32, f64, u8) = (500, 6.4, 1);
```

---

## Arrays

```
  let a = [1, 2, 3]; // a: [i32; 3]
  let mut m = [1, 2, 3]; // m: [i32; 3]
```

---

## Loops

----

### loop

```
  loop {
      expressions;
  }
```

----

```
  fn main() {
      loop {
          println!("again!");
      }
  }
```

----

### for

```
  for i in x..n {
      expressions;
  }
```

----

```
  fn main () {
      let a = [1, 2, 3, 4, 5];
      for i in 0..5 {
          println!("{}", a[i]);
      }
  }
```

----

```
  fn main() {
      let a = [1, 2, 3, 4, 5];
      for i in a.iter() {
          println!("{}", i);
      }
  }
```

----

```
  fn main() {
      let a = [1, 2, 3, 4, 5];
      for n in (0..5).rev() {
          println!("{}", a[n]);
      }
  }
```

----

### while

```
  while condition {
      expressions;
  }
```

----

```
  fn main () {
      let a = [1, 2, 3, 4, 5];
      let mut i = 0;
      while i < 5 {
          println!("{}", a[i]);
          i = i +1;
      }
  }
```

---

## functions

```
  fn name(arg: Type) -> ReturnType {
      statements;
  }
```

---

## Example

```
  fn main () {
      let a = 9;
      let b = 15;
      sum(a, b);
  }
  fn sum(a: i32, b: i32) {
      let c = a + b;
      println("The sum of {} + {} is: {}", a, b, c;
  }
```

----

```
  fn five() -> i32 {
      5
  }

  fn main() {
      let x = five();
      println!("The value of x is: {}", x);
  }
```

---

## Learn More

_[rust-lang.org](https//rust-lang.org)_

___

[@mariogmd](https://twitter.com/mariogmd)

[fb.com/iscmariog](https://fb.com/iscmariog)

mattdark@mozilla-mexico.org
