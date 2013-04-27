import sys

#检查是否存在非法字符
def checkChr(s):
    chrList = ['(',')','+','-','*','/','0','1','2','3','4','5','6','7','8','9']
    if s in chrList:
        return True
    else:
        return False
#计算结果
def jisuan(n1,n2,o):
    if o=='+':
        return n1+n2
    elif o=='-':
        return n1-n2
    elif o=='*':
        return n1*n2
    elif o=='/':
        return n1/n2
#计算过程
def com(flag):
    if not stack_flag:
        loop = 0
    elif flag==0:
        loop = 1
    else:
        loop = len(stack_flag)
    i = 0
    while i < loop:
        if stack_flag[-1]=='(':
            break
        opnt = stack_num.pop()
        opno = stack_num.pop()
        op = stack_flag.pop()
        result = jisuan(opno,opnt,op)
        stack_num.append(result)
        i = i + 1        

exp = input('please input expressions:')
#符号栈
stack_flag = []
stack_num = []
operate = {'+':1,'-':1,'*':3,'/':3}
tmp = str()
numList = ['0','1','2','3','4','5','6','7','8','9']
length = 0
#分析输入字符串
for chr in exp:
    length = length + 1
    if not checkChr(chr):
        print('please check input')
        break
    if chr in numList:
        tmp = tmp + chr
        if length == len(exp):
            stack_num.append(int(tmp))
            com(1)
    else:
        if tmp!='':
            stack_num.append(int(tmp))
            tmp = ''
        if chr == '(':
            stack_flag.append(chr)
        elif chr ==')':
            com(1)
            po =stack_flag.pop()
            if po!='(':
                print('error exp!')
                break
        elif chr=='+' or chr=='-' or chr=='*' or chr=='/':
            if stack_flag:
                stack_top = stack_flag[-1]
            else:
                stack_top = ''
            if stack_top!='' and stack_top!='(' and len(stack_num)>=2 and not operate[chr]>operate[stack_top]:
               if operate[chr]==operate[stack_top]:
                   com(0)
               else:
                   com(1)
            
            stack_flag.append(chr) 
    pass
if stack_flag:
    com(1)
print(stack_num)
print(stack_flag)








