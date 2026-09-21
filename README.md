# Library Management System

Books, users and borrowing transactions, with the catalogue persisted as JSON.
Java Lessons, task 5.

## What it covers

- An OOP model split into `models`, `enums`, `comparators` and `exceptions` packages.
- `Comparator` implementations that sort books and users by several fields.
- Checked exceptions of its own - `BookNotAvailableException`,
  `UserNotFoundException` - raised from the lending path rather than returning
  error codes.
- Reading and writing the catalogue as JSON with Jackson.

## Running it

Jackson is vendored under `lib/`, so no dependency manager is needed:

```bash
# Linux / macOS
javac -cp "lib/*" -d out $(find src -name "*.java")
java -cp "out:lib/*" Main

# Windows (PowerShell)
javac -cp "lib/*" -d out (Get-ChildItem -Recurse src -Filter *.java).FullName
java -cp "out;lib/*" Main
```

## Layout

- `src/models/` - `Book`, `User`, `Transaction`.
- `src/enums/` - genre, role and transaction type.
- `src/comparators/`, `src/exceptions/` - sorting, and the failure cases.
- `src/datas/` - the JSON store (`library`, `users`, `transactions`).
- `lib/` - Jackson 2.17.1 jars.
