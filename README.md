def PrimeList(N):
    if N <= 2:
        return ""
    sieve = [True] * N
    sieve[0] = sieve[1] = False
    for i in range(2, int(N**0.5) + 1):
        if sieve[i]:
            sieve[i*i:N:i] = [False] * len(sieve[i*i:N:i])
    primes = [str(i) for i, is_p in enumerate(sieve) if is_p]
    return ' '.join(primes)
