print("Basic Matrix Operation using Python") 
m1 = [] 
m = [] 
m2 = [] 
res = [[0, 0, 0, 0, 0], [0, 0, 0, 0, 0], [0, 0, 0, 0, 0], [0, 0, 0, 0, 0], [0, 0, 0, 0, 0]] 
print("Welcome all in assignment no:03 from Group A") 
print("For Matrix operation we require some input from you Please.") 
row1 = int(input("Enter no of rows in first matrix: ")) 
col1 = int(input("Enter no of cols in first matrix: ")) 
row2 = int(input("Enter no of rows in second matrix: ")) 
col2 = int(input("Enter no of cols in second matrix: "))
def main():
    print("1. Accept two matrices from user:")
    print("2. Show the matrices values: ")
    print("3. Addition of Two Matrices:")
    print("4. Subtraction of Two Matrices: ")
    print("5. Multiplication of Two Matrices: ")
    print("6. Transpose of Matrix")
    print("7. Exit")
    ch = int(input("Enter your choice:"))
    if ch == 1:
        print("please enter the values for First Matrix:") 
        accept(m1, row1, col1)
        print("please enter the values for Second Matrix:")
        accept (m2, row2, col2)
        main()
    elif ch == 2:
        print("The Value of First matrix is as follows: ")
        show(m1, row1, col1)
        print("The Value of Second matrix is as follows: ")
        show(m2, row2, col2)
        main()
    elif ch == 3:
        print("The addition of two matrices are as follows..")
        if ((row1 == row2) and (col1 == col2)):
            add_mat(m1, m2, row1, col1)
        show(res, row1, col1)
        print("Sorry!!! Addition is not possible...")
        main()
    elif ch == 4:
        print("The subtraction of two matrices are as follows..")
        if ((row1 == row2) and (col1 == col2)):
            sub_mat(m1, m2, row1, col1)
            show(res, row1, col1)
        else:
            print("Sorry!!! Subtraction is not possible...")
        main()
    elif ch == 5:
        print("The Multiflication is as follow...")
        if ((row1 == row2) and (col1 == col2)):
            mul(m1, m2, row1, col1)
            show(res, row1, col1)
        else:
            print("Sorry!!! Multiplication is not possible...")
        main()
    elif ch == 6:
        print("The Multiflication is as follow...")
        tran(m1,row1,col1)
        show(m1,row1,col1)
        main()
    elif ch == 7:
          exit
            
    else:
        print("enter valid choice")
def accept(m, row, col):
    for i in range(row):
        c = []
        for j in range(col):
            no = int(input("Enter the value of matrix[" + str(i) + "][" + str(j) + "]:: "))
            c.append(no)
        print("--------")
        m.append(c)
def show(m, row, col):
    for i in range(row):
        for j in range(col):
            print(m[i][j], end=" ")
    print()
def add_mat(ml, m2, row, col):
    for i in range(row):
        for j in range(col):
            res[i][j] = m1[i][j] + m2[i][j]
def sub_mat(ml, m2, row, col):
    for i in range(row):
        for j in range(col):
            res[i][j] = m1[i][j] - m2[i][j]            
main()
def mul(m1,m2,row,col):
    for i in range (row):
        for j in range (col):
            for k in range(len(m1)):
                res[i][j]+=m1[i][k]*m2[k][j]
def tran(m1,row,col):
    for i in range (row):
        for j in range (col):
            res[i][j]=m1[j][i]