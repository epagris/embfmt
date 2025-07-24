# EmbFmt

A lightweight formatted printer (`printf()`) implementation for embedded systems with CMake support.

## Formatting codes

The library supports the following type designators:

| Designator      | Type           | Description                                                  |
| --------------- | -------------- | ------------------------------------------------------------ |
| `%c`            | `char`         | Character                                                    |
| `%s`            | `char *`       | Null-terminated string                                       |
| `%d`, `%i`      | `int`          | Signed decimal integer                                       |
| `%u`            | `unsigned int` | Unsigned decimal integer                                     |
| `%x`, `%p`/`%X` | `unsigned int` | Unsigned hexadecimal integer with lowercase/UPPERcase digits |
| `%f`/`%k`       | `double`       | Floating point with rounding/truncation                      |
| `%e`            | `double`       | Floating point using scientific notation                     |
| `%%`            | -              | '%' character                                                |

## Length modifier

By default, 32-bit integers are assumed (e.g.: `%u` - `uint32_t`), the `l` modifier always extends integer fields to 64 bits (e.g. `%lu` - `uint64_t`).

## Precision modifier

The library supports the precision modifiers, e.g. `%.4f` - four digits in the fractional part. The least significant digit is either determined by rounding (`%.3f`: 1.2345 -> 1.235), or by truncation (`%.3k`: 1.2345 -> 1.234).

## Leading digits

The library provides support for specifying the number and the type of leading character for numerical fields. The filling characters can be either `0` or spaces. (e.g. `%05u`: 12 -> 00012, `% 5u`: 12 -> ␣␣␣12)

The length of a field can be also passed as a parameter with the `*` modifier.

# License

The EmbFmt library has been released under the MIT License. Developer and main contributor: [Epagris](https://github.com/epagris)
