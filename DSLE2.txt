def In(element,list1):
    flag=0
    for i in range(len(list1)):
        if (element==list1[i]):
            flag=1
    if flag == 1:
        return True
    else:
        return False
def first_appe(string,substring):
    flag=0
    for i in range (len(substring)):
        if In(substring[i],string):
            flag=flag+1
        if flag==len(substring):
            for i in range(len(string)):
                if substring[0]==string[i]:
                    return i
    return 0
def rev(string):
    revstr=""
    for i in range(len(string)):
        revstr=string[i]+revstr
    return revstr
def str_count(str1,char):
    count=0
    for i in range(len(str1)):
        if char==str1[i]:
            count=count+1
    return count
def max_len(splitL):
    global new_str2
    len1=0
    new_str1=""
    for i in range(len(splitL)):
        if len1<(len(splitL[i])):
            len1=(len(splitL[i]))
            new_str2=new_str1+splitL[i]
    return len1
def is_palindrome(str):
    for i in range(0,int(len(str))%2):
        if str[i] != str[len(str)-i-1]:
            return False
    return True
flag =1
while flag==1:
    flag=1
    print("\n\n-----Menu----\n")
    print("1.Check Palindrome string.")
    print("2.Check Max length world in string.")
    print("3.Check count of specific character.")
    print("4.Check appearemce of substring.")
    print("5.Exit")
    choice=int(input("Enter Choice (1 to 5):"))
    if choice==1:
        str1=input("Enter A string to check is it palindrome or Not:")
        if (is_palindrome(str1)):
                 print("Entered String is palindrome")
        else:
                 print("Entered string is not palindrome")
    elif choice==2:
        str2=input("Enter a sentence to check maximum length of world: ")
        new=str2.split()
        print("Max length: ",max_len(new), "world: ",new_str2)
    elif choice==3:
        str3=input("Enter string to check count of specific character:")
        ch=input("Enter Character:")
        print("Entered character count is: ",str_count(str3,ch))
    elif choice==4:
        str4 = input("Enter string to check first appearance of substring: ")
        sub_string=input("Enter Substring: ")
        print(sub_string," is at index",first_appe(str4,sub_string))
        
    elif choice==5:
        flag=0
        print("Thank You")
    else:
        print("You Enter Wrong Choice")
        print("you want to continue yes or no.")
        ans=input()
        if ans==yes:
            flag=1
        else:
            flag=0
            print("Thank You")
        