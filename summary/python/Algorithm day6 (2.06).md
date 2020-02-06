# Algorithm day6 (2.06)

\# 백준  2635

\# n1 = 100

\#   lis = []

\#   lis.append(n1)

\# for n2 in range(1, 100):

\#   r = n1 - n2

\#   lis.append(n2)

\#   if r > 0:

\#     n1 = n2

\#     n2 = r

\#     while r > 0:

\#       r = n1 - n2

\#       lis.append(r)

\#       n1 = n2

\#       n2 = r

\# print(lis)

\# 못품



\# 백준 2439

\# T = int(input())

\# for i in range(T):

\#   for j in range(T):

\#     if i + j + 1 < T:

\#       print(' ', end = '')

\#     else:

\#       print('*', end = '')

\#   print('')



\# 백준 2440

\# T = int(input())

\# for i in range(T):

\#   for j in range(T):

\#     if i + j < T:

\#       print('*', end = '')

\#     else:

\#       break

\#   if i + 1 == T:

\#     break

\#   else:

\#     print('')



\# 백준 2441

\# T = int(input())

\# for i in range(T):

\#   for j in range(T):

\#     if i > j:

\#       print(' ', end = '')

\#     else:

\#       print('*', end = '')

\#   print('')



\# 백준 2442

\# 절대값으로 풀기 실패

\# T = int(input())

\# for i in range(T):

\#   for j in range(T*2-1):

\#     if (i + j) - T + 1 == 0:

\#       print('*', end = '')

\#     else:

\#       print(' ', end = '')

\#   print('')



\# T = int(input())

\# for i in range(T):

\#   for j in range(2*T-1):

\#     if j+1-i > T:

\#       break

\#     elif T-i-1 <= j <= T+i-1:

\#       print('*', end = '')

\#     else:

\#       print(' ', end = '')

\#   print('')



\# 백준 2443

\# T = 5

\# for i in range(2*T-1):

\#   for j in range(T):

\# 패스



\# 백준 1427

\# T = input()

\# lis = []

\# try:

\#   for idx, i in enumerate(T):

\#     lis.append(T[idx])

\#     for j in lis:

\#       if T[idx] > T[j] :

\#         lis.insert(0, i)

\#       elif T[idx] < T[j]:

\#         lis.append(i)

\# except KeyboardInterrupt:

\#   print(lis)

\# T = input()

\# num = []

\# for i in T:

\#   num.append(i)

\# num = reversed(sorted(num))

\# result = ''

\# for i in num:

\#   result += str(i)

\# print(result)



\# 백준 2741

\# T = int(input())

\# for i in range(T):

\#   print(i+1)



\# 백준 2742

\# T = int(input())

\# for i in range(T, 0, -1):

\#   print(i)



\# 백준 10872

\# T = int(input())

\# result = 1

\# for i in range(1, T+1):

\#   result *= i

\# print(result)



\# 백준 10871

\# a = list(map(int, input().split()))

\# b = list(map(int, input().split()))

\# r = []

\# for i in b:

\#   if i < a[1]:

\#     print(i,end=' ')



\# 백준 11720

\# a = int(input())

\# b = input()

\# r = 0

\# for i in b:

\#   r += int(i)

\# print(r)



\# 백준 