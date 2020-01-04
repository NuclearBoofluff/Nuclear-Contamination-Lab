import time

def user_input():
    while True:
        x = int(input("1:Too Low, 2:Too High, 3:Just Right\n"))
        if x == 1 or x == 2 or x == 3:
            return x

def change_guess(UI, low, high, number):
    if UI == 2:
        high = number
    else:
        low = number
    return low, high

def initialize_number():
    while True:
        user_num = int(input("Enter a number between 0 and 100: "))
        if user_num > 0 or user_num <100:
            print("This is your number, please remember it", end = "")
            break

def nap_time():
    x = 0
    while x < 5:
        time.sleep(.8)
        print(".", end = "")
        x += 1

def tester():
    count = 0
    low, high = 0, 100
    fail_safe = 0
    while True:
        if fail_safe == 1:
            return count, fail_safe
        if high - low < 1:
            fail_safe += 1
        count += 1
        number = (low + high) / 2
        time.sleep(1)
        print("\nIs " + str(int(number)) + " your number?")
        inputs = user_input()
        if inputs == 3:
            return count, fail_safe
        else:
            low, high = change_guess(inputs, low, high, number)


def main():
    initialize_number()
    nap_time()
    print("\n\nThis is the dumb AI speaking now. I will try to guess your number.")
    time.sleep(2)
    count, fail_safe = tester()
    if count == 1 and fail_safe == 0:
        print("\nCool, I guessed it in 1 try!")
    elif fail_safe == 0:
        print("\nCool, I guessed it in " + str(count) + " tries!")
    else:
        print("\nSorry I wasn't able to get your number :(")

if __name__ == '__main__':
    main()
