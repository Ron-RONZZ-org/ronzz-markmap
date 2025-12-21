# TOML

## Overview

- Tom's Obvious Minimal Language
- Human-friendly config format
- Easy to read
- Maps to hash table

## Basic syntax

### Strings

```toml
# Basic strings
str1 = "Hello!"
str2 = "You can \"quote\" me."  # Escaping
str3 = "Name\tJose\u00E9\nLocation\tSF."  # Special chars
```

### Multi-line strings

```toml
# Multi-line basic string
str4 = """
Roses are red
Violets are blue"""

# Line-ending backslash
str5 = """\
    The quick brown fox \
    jumps over \
    the lazy dog.\
    """
```

### Numbers

```toml
# Hexadecimal with prefix 0x
hex1 = 0xDEADBEEF

# Octal with prefix 0o
oct1 = 0o755

# Binary with prefix 0b
bin1 = 0b11010110

# Float
float1 = 6.626e-34

# Separators for readability
float2 = 224_617.445_991_228
hex3 = 0xdead_beef

# Infinity
inf1 = +inf
inf2 = -inf

# Not a number
nan1 = nan
```

### Booleans

```toml
bool1 = true
bool2 = false
```

### Dates and times

```toml
# Offset date-time
odt1 = 1979-05-27T07:32:00Z
odt2 = 1979-05-27T00:32:00-07:00

# Local date-time
ldt1 = 1979-05-27T07:32:00

# Local date
ld1 = 1979-05-27

# Local time
lt1 = 07:32:00
```

## Arrays

```toml
# Simple arrays
integers = [1, 2, 3]
colors = ["red", "yellow", "green"]

# Nested arrays
nested = [[1, 2], [3, 4, 5]]

# Multi-line arrays
array = [
    "item1",
    "item2",
    "item3",
]
```

## Tables

### Basic tables

```toml
[table]
key = "value"
number = 42

[table.subtable]
nested = true
```

### Inline tables

```toml
name = { first = "Tom", last = "Preston-Werner" }
point = { x = 1, y = 2 }
```

### Array of tables

```toml
[[products]]
name = "Hammer"
sku = 738594937

[[products]]
name = "Nail"
sku = 284758393
```

## Keys

- Bare keys
  - `key = "value"`
  - Alphanumeric, dashes, underscores
- Quoted keys
  - `"key with spaces" = "value"`
  - Any Unicode character
- Dotted keys
  - `physical.color = "orange"`
  - Creates nested structure

## Comments

```toml
# Single line comments only
key = "value"  # End of line comments
```

## Best practices

- Use meaningful names
- Group related settings
- Comment complex values
- Use consistent style
- Prefer tables over deep nesting
- Order sections logically

## Common use cases

- Configuration files
- Package metadata
  - Cargo.toml (Rust)
  - pyproject.toml (Python)
- Application settings
- Build specifications
