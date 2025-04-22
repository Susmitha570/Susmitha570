def is_prime(n):
    if n < 2:
        return False
    for i in range(2, int(n**0.5) + 1):
        if n % i == 0:
            return False
    return True

def is_3d_prime(num):
    if not is_prime(num):
        return False
    
    num_digits = len(str(num))
    if not is_prime(num_digits):
        return False

    digit_sum = sum(int(d) for d in str(num))
    if not is_prime(digit_sum):
        return False

    return True
    
for i in range(10, 1000):
    if is_3d_prime(i):
        print(i)
