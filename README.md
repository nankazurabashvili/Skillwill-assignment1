# Skillwill-assignment1
Romanian calculator 
print('+. ADD')
print('-. Subtract')
print('Type Exit to calculate')
num = input("Enter Number: ")
def romanToInteger(num):
    d = {'I': 1, 'V': 5, 'X': 10, 'L': 50, 'C': 100, 'D': 500, 'M': 1000}
    ans = 0
    for i in range(len(num)):
        if i + 1 != len(num) and d[num[i]] < d[num[i + 1]]:
            ans = ans - d[num[i]]
        else:
            ans = ans + d[num[i]]
    return ans
num = romanToInteger(num)
op = "Operation"
while op != 'Exit':
    op = input("Operation: ")
    if op == "+":
        number = input("Enter Number: ")
        number = romanToInteger(number)
        int(number)
        num=int(num)+int(number)
    else:
        """number = input("Enter Number: ")
        number = romanToInteger(number)
        int(number)
        num = int(num) - int(number)"""

def to_Roman(num):
    val = [
        1000, 900, 500, 400,
        100, 90, 50, 40,
        10, 9, 5, 4,
        1
        ]
    syb = [
        "M", "CM", "D", "CD",
        "C", "XC", "L", "XL",
        "X", "IX", "V", "IV",
        "I"
        ]
    roman_num = ''
    i = 0
    while num > 0:
        for _ in range(num // val[i]):
            roman_num += syb[i]
            num -= val[i]
        i += 1
    return roman_num
num=to_Roman(num)
print("The Answer is " + str(num))
