# magic-1089
The magic of 1089. Take a three-digit number, the digits of which are in descending order. Subtract its reversed number. Then to the sum add its reversed sum. The result is always 1089.

import random
is_on = True
counted = 0
impossible = {}
while is_on:
    counted += 1
    print(f"Counted - {counted}")
    print(f"Impossible - {impossible}")
    random_number_one = random.randint(3, 9)
    random_number_two = random.randint(1, 8)
    while random_number_two >= random_number_one:
        random_number_two = random.randint(1, 8)
    random_number_three = random.randint(0, 7)
    while random_number_three >= random_number_two:
        random_number_three = random.randint(0, 7)
    common_order = [str(random_number_one), str(random_number_two), str(random_number_three)]
    common_number = int("".join(common_order))
    reversed_order = [str(random_number_three), str(random_number_two), str(random_number_one)]
    reversed_number = int("".join(reversed_order))
    common_number_sum = common_number - reversed_number
    print(f"{common_number} - {reversed_number} = {common_number_sum}")
    sum_numbers_list = [i for i in str(common_number_sum)]
    reversed_number_sum_order = [str(sum_numbers_list[2]), str(sum_numbers_list[1]), str(sum_numbers_list[0])]
    reversed_number_sum = int("".join(reversed_number_sum_order))
    reversed_sum = common_number_sum + reversed_number_sum
    print(f"{common_number_sum} + {reversed_number_sum} = {reversed_sum}")
    if reversed_sum != 1089:
        impossible[common_order] = "impossible"





