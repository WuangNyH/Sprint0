# Java – Formatting Rules (chuẩn Google/Oracle)

- **Indent**: 4 spaces (không dùng tab).
- **Braces**: mở cùng dòng, đóng xuống dòng (K&R):

  ```java
  if (ok) {
      run();
  } else {
      rollback();
  }
  ```

- **Khoảng trắng**:

  - Sau dấu `,` và quanh toán tử: `a + b`, `map.put(k, v);`
  - Không có khoảng trắng trước `;` hay trước dấu `)`; có **1 space** trước `{`.
  - Không space giữa tên method và `(`: `doWork(arg)` (❌ `doWork (arg)`).

- **Dòng trống**:

  - 1 dòng giữa các **field group**, **constructor**, **method**.
  - 1 dòng sau block import.

- **Imports**:

  - Không dùng `*`.

- **Chaining / Wrapping**:

  - Khi xuống dòng, **ngắt trước dấu chấm**:

    ```java
    var x = builder
        .setName(name)
        .setAge(age)
        .build();
    ```

- **Annotation**:

  ```java
  @RequestMapping(
      method = GET,
      value = "/employees"
  )
  ```

- **Lambda**: có khoảng trắng quanh `->`, block nhiều dòng phải có `{}`:

  ```java
  list.stream().map(x -> x * 2).forEach(System.out::println);
  ```

# Vue.js – Formatting Rules (Vue 3 + Prettier + ESLint)

- **Indent**: 2 spaces.
- **Self-closing**: thẻ không nội dung tự đóng: `<img />`, `<MyButton />`.
