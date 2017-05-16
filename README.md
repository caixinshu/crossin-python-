# crossin-python-
# coding=utf-8
from random import randint

while True:
    c = input('1:开始游戏;2:退出\n')

    if c ==1:
        num = randint(1,99)
        print '猜数字:'
        n = 5
        while n>0:
            n = n-1 #限制次数
            numb=input("输入数字：")
            if numb> num:
                print '大了'
            elif numb<num:
                print '小了'
            else:
                print '猜对了'
                break
    elif c == 2:
        print '退出游戏'
        break


f=open('cj.txt','r')
zong=[]  
sum =0
for line in f.readlines():
    line = line.split()
    for i in line[1:10]:
        sum = sum + int(i)
    line.append(sum)
    line.append(round(sum/9.0,1))
    zong.append(line)
    sum = 0

zong.sort(key= lambda x:x[-2])
zong = zong[::-1]
print zong
pj=[]
for i in range(1,12):
    sum = 0.0
    for j in range(len(zong)):
        sum = sum + int(zong[j][i])
    pj.append(round(sum/len(zong),1))
print pj
