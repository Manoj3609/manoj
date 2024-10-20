def shellSort(arr):
    n = len(arr)
    gap = n // 2
    while gap > 0:
        for i in range(gap, n):
            temp = arr[i]
            j = i
            while j >= gap and arr[j - gap] > temp:
                arr[j] = arr[j - gap]
                j -= gap
            arr[j] = temp
        gap = gap // 2
    return arr


def insertion_sort(arr):
    for i in range(1, len(arr)):
        key = arr[i]
        j = i - 1
        while j >= 0 and key < arr[j]:
            arr[j + 1] = arr[j]
            j -= 1
        arr[j + 1] = key
    return arr


def top_five(arr):
    print("Top five scores are : ")
    cnt = len(arr)
    if cnt < 5:
        start, stop = cnt - 1, -1
    else:
        start, stop = cnt - 1, cnt - 6
    for i in range(start, stop, -1):
        print("\t{0:2f}".format(arr[i]), end=" ")


arr = []
Num = int(input("Enter the number of students: "))
for i in range(Num):
    per = float(input("Enter the mark of student " + str(i + 1) + ":"))
    arr.append(per)


def main():
    print("1. shellsort")
    print("2. insertionsort")
    print("3. display top five marks")
    print("4. exit")
    choice = int(input("Enter choice for sort: "))
    if choice == 1:
        insertion_sort(arr)
        print("Sorted Array:")
        m = []
        for i in range(len(arr)):
            m.append(arr)
        print(m)
    elif choice == 2:
        shellSort(arr)
        print("Sorted Array is:")
        n = []
        for i in range(len(arr)):
            n.append(arr)
        print(n)
    elif choice == 3:
        top_five(arr)
    elif choice == 4:
        exit()
    else:
        print("Enter valid input : ")


main()
