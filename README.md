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
