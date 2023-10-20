# • Write a get_prim method in python/perl/bash/pseudo.

Sure, I can provide you with examples of a `get_prim` method in Python, Perl, Bash, and pseudocode.

**Python:**

```python
def is_prime(n):
    if n <= 1:
        return False
    elif n <= 3:
        return True
    elif n % 2 == 0 or n % 3 == 0:
        return False
    i = 5
    while i * i <= n:
        if n % i == 0 or n % (i + 2) == 0:
            return False
        i += 6
    return True

def get_prim(n):
    primes = []
    for num in range(2, n + 1):
        if is_prime(num):
            primes.append(num)
    return primes

print(get_prim(20))

```

**Perl:**

```perl
sub is_prime {
    my $n = shift;
    return 0 if $n <= 1;
    return 1 if $n <= 3;
    return 0 if ($n % 2 == 0) || ($n % 3 == 0);
    my $i = 5;
    while ($i * $i <= $n) {
        return 0 if ($n % $i == 0) || ($n % ($i + 2) == 0);
        $i += 6;
    }
    return 1;
}

sub get_prim {
    my $n = shift;
    my @primes;
    for my $num (2 .. $n) {
        push @primes, $num if is_prime($num);
    }
    return @primes;
}

my @result = get_prim(20);
print join(", ", @result), "\\n";

```

**Bash:**

```bash
#!/bin/bash

is_prime() {
    n=$1
    if [ $n -le 1 ]; then
        return 1
    elif [ $n -le 3 ]; then
        return 0
    elif [ $((n % 2)) -eq 0 ] || [ $((n % 3)) -eq 0 ]; then
        return 1
    fi
    i=5
    while [ $((i * i)) -le $n ]; do
        if [ $((n % i)) -eq 0 ] || [ $((n % (i + 2))) -eq 0 ]; then
            return 1
        fi
        i=$((i + 6))
    done
    return 0
}

get_prim() {
    n=$1
    primes=""
    for ((num = 2; num <= n; num++)); do
        if is_prime "$num"; then
            primes="$primes $num"
        fi
    done
    echo "$primes"
}

result=$(get_prim 20)
echo "$result"

```

**Pseudocode:**

```
function is_prime(n):
    if n <= 1:
        return False
    else if n <= 3:
        return True
    else if n % 2 == 0 or n % 3 == 0:
        return False
    i = 5
    while i * i <= n:
        if n % i == 0 or n % (i + 2) == 0:
            return False
        i += 6
    return True

function get_prim(n):
    primes = []
    for num in range(2, n + 1):
        if is_prime(num):
            primes.append(num)
    return primes

```

You can use these code examples in their respective languages to find prime numbers up to a given limit (`n`).