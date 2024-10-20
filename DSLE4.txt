def bubble_sort(arr):
    n = len(arr)
    for i in range(n-1):
        for j in range(0, n-i-1):
            if arr[j] > arr[j+1]:
                arr[j],arr[j+1]=arr[j+1], arr[j]
    return arr

def selection_sort(arr):
    n = len(arr)
    for i in range(n-1):
        location = i
        for j in range(i+1, n):
            if arr[location] < arr[j]:
                location = j
            temp=arr[location]
            arr[location]=arr[j]
            arr[j]=temp
    return arr
def display_top_scores(arr, n=5):
    print("Top 5 scores:")
    for i in range(n):
        print(f"{i+1}. {arr[-i-1]}")


percentages=[]
for i in range(5):
    percentage=int(input("enter percentage of students"))
    i+=1
    percentages.append(percentage)
        
flag=1
while flag:
    ch=int(input("enter a no from 1 to 3:"))
    if(ch==1):
        print("before sorting",percentages)
        print("after sorting:",bubble_sort(percentages))
    else:
        print("thank you for using my program")
        flag=0
    ch=int(input("enter a no from 1 to 3:"))
    if(ch==2):
        print("before sorting",percentages)
        print("after sorting:",selection_sort(percentages))
    else:
        print("thank you for using my program")
        flag=0
    ch=int(input("enter a no from 1 to 3:"))
    if(ch==3):
        print(display_top_scores(percentages, n=5))
    else:
        flag=0