# homework
#coding:gbk
"""
第一个小项目：Rock-paper-scissors-lizard-Spock
作者：段至柔
日期：2020年4月12日
"""

import random





def name_to_number(name):    #定义函数，将游戏对象对应不同的数
    if name=="石头":      #利用if,elif,else将游戏对象对应在不同的数上，利用return返还结果
	    return 0
    elif name=="史波克":
        return 1
    elif name=="纸":
        return 2
    elif name=="蜥蜴":
        return 3
    elif name=="剪刀":
        return 4
    else:
        print("Error: No Correct Name")




def number_to_name(number):  #定义函数，将整数 (0, 1, 2, 3, or 4)对应到游戏的不同对象
	if number==0:         #利用if,elif,else将不同的数对应在游戏对象上，利用return返还结果
		return "石头"
	elif number==1:
		return "史波克"
	elif number==2:
		return "纸"
	elif number==3:
		return "蜥蜴"
	elif number==4:
		return "剪刀"
	else:
		print("Error: No Correct number")
	


def rpsls(player_choice):    #定义函数，用户玩家任意给出一个选择，根据RPSLS游戏规则，在屏幕上输出对应的结果
    print()
    print("您的选择为：",player_choice)
    player_choice_number=name_to_number(player_choice)  #调用name_to_number()函数将用户的游戏选择对象转换为相应的整数，存入变量player_choice_number
    comp_number=random.randrange(0,5)
    comp_choice=number_to_name(comp_number)    # 利用random.randrange()自动产生0-4之间的随机整数，作为计算机随机选择的游戏对象，存入变量comp_number
    print("计算机的选择为：",comp_choice)
    if player_choice_number-comp_number in [-4,-3,1,2]:  #根据 player_choice_number与comp_numbe之间的差判断输赢，利用列表赋予差不同的数据，此时为玩家赢的情况
        print("您赢了!")
    elif player_choice_number-comp_number in [-2,-1,3,4]:  #此为玩家输的情况
        print("机器赢了")
    elif player_choice_number-comp_number==0:  #此为平局的情况
        print("您和计算机出的一样呢")
    else:
        print("Error: No Correct Name")
		
    



print("欢迎使用RPSLS游戏")
print("----------------")
print("请输入您的选择:")
choice_name=input()
print("----------------")
rpsls(choice_name)    # 对程序进行测试


