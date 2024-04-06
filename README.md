409446514
1.
i = 1
while i <= 9:
  j = 1
  while j <= 9:
    result = i*j
    print("%d*%d=%-3d" % (i, j, result), end=" ")
    j += 1
  print()
  i += 1
  
2.
def matrix(m1, m2):
    if len(m1[0]) != len(m2):
        print("無法進行矩陣乘法。第一個矩陣的列數必須等於第二個矩陣的行數。")
        return None

    result = [[0 for _ in range(len(m2[0]))] for _ in range(len(m1))]

    for i in range(len(m1)):
        for j in range(len(m2[0])):
            for k in range(len(m2)):
                result[i][j] += m1[i][k] * m2[k][j]

    return result

def input_matrix(r, c):
    matrix = []
    print("請逐行輸入元素：")
    for i in range(r):
        row = []
        for j in range(c):
            element = float(input(f"輸入位置 ({i+1},{j+1}) 的元素: "))
            row.append(element)
        matrix.append(row)
    return matrix

def print_matrix(m):
    for row in m:
        print(row)

def main():
    print("矩陣乘法程式")

    r1 = int(input("請輸入第一個矩陣的行數: "))
    c1 = int(input("請輸入第一個矩陣的列數: "))

    print("請輸入第一個矩陣的元素:")
    m1 = input_matrix(r1, c1)

    r2 = int(input("請輸入第二個矩陣的行數: "))
    c2 = int(input("請輸入第二個矩陣的列數: "))

    print("請輸入第二個矩陣的元素:")
    m2 = input_matrix(r2, c2)

    result = matrix(m1, m2)

    if result:
        print("\n矩陣乘法結果:")
        print_matrix(result)

if __name__ == "__main__":
    main()

3.

import random

def quicksort(array):
    if len(array) <= 1:
        return array
    a = array[len(array) // 2]
    l = [x for x in array if x < a]
    m = [x for x in array if x == a]
    r = [x for x in array if x > a]
    return quicksort(l) + m + quicksort(r)

random_numbers = [random.randint(1, 100) for _ in range(15)]

sorted_numbers = quicksort(random_numbers)
print("Sorted Numbers:",sorted_numbers)

