# julian-day-converter
Shell scripts to convert a date in ISO format to a Julian Day Number
and back again

## Introduction

A [Julian Day Number](https://en.wikipedia.org/wiki/Julian_day#History)
is similar to a Unix timestamp, counting days instead of seconds,
and using January 1st of the year 4713 BC as starting point (or "epoch").

This is a useful format for computations on dates:
* adding a number of days to a date to get a new date
* subtracting dates to get the interval in days

## Algorithms

The conversions use the algorithms described on Wikipedia:

1. [Converting Julian or Gregorian calendar date to Julian Day Number]
   (https://en.wikipedia.org/wiki/Julian\_day#Converting\_Julian\_or\_Gregorian\_calendar\_date\_to\_Julian\_Day\_Number)
2. [Gregorian calendar from Julian day number]
   (https://en.wikipedia.org/wiki/Julian\_day#Gregorian\_calendar\_from\_Julian\_day\_number)

## Usage

The script `iso2julian.sh` converts an ISO date in format `yyyy-mm-dd`
to a Julian Day Number:

```sh
$ ./iso2julian.sh 2015-03-18
2457100
```

The script `julian2iso.sh` converts a Julian Day Number back to an ISO date
in format `yyyy-mm-dd`:

```sh
$ ./julian2iso.sh 2457100
2015-03-18
```

The date to convert can be provided as parameter; otherwise, it will be
read from standard input:

```sh
$ echo '2015-03-18' | ./iso2julian.sh
2457100

$ echo 2457100 | ./julian2iso.sh
2015-03-18
```

In both cases, the converted date is written to standard output.

## License

[CC0](https://creativecommons.org/publicdomain/zero/1.0/)
