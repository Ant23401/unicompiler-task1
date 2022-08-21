# unicompiler-task1
import random
from warnings import catch_warnings
print("Please Select A or B \n")
correctInput = True
while(correctInput):
    print("A> 1 - 10\n")
    print("B> 1 - 100\n")
    n = input()
    
# Input given is proper
    if(n == "A" or n=="a" or n=="B" or n =="b"):
        correctInput = False
        if(n == "A" or "a"):
            secNum = random.randint(1, 10)
        elif(n == "B" or "b"):
            secNum = random.randint(1, 100)
        guessed = False
        if(n == "B" or n=="b"):
            print("\nGUESS A NUMBER BETWEEN 1 to 100")
            i = 20
            score = 20
            while(score != 0):
                if(score >= 0):
                    print("Chances left " + str(score) + " \n")
                    print("GUESS THE NUMBER \n")
                    n = int(input())

                    if(n > secNum):
                        range1 = secNum - i
                        if(range1 < 0):
                            range1 = 0
                        range2 = secNum + i
                        print("\nNumber greater than Secret number")
                        print("number is  between " + str(range1) +
                            " and " + str(range2) + "\n")
                        score -= 1
                    elif(n < secNum):
                        range1 = secNum - i
                        range2 = secNum+i
                        if(range2 > 100):
                            range2 = 100
                        if(range1 < 0):
                            range1 = 0

                        print("\nNumber smaller than Secret number")
                        print("Number is  between " + str(range1) +
                            " and " + str(range2)+"\n")
                        score -= 1
                    if(n == secNum):
                        print("Secret number " + str(secNum) +
                            " guessed successfully")
                        chances = False
                        print("score :" + str(score))
                        guessed = True
                        break
                    i -= 1
                    
            if(guessed == False):
                print("YOU COULDN'T GUESS THE NUMBER : " + str(secNum))

        elif(n == "A" or n=="a"):
            print("\nGUESS A NUMBER BETWEEN 1 to 10 ")
            i = 5
            score = 5
            while(score != 0):
                if(score >= 0):
                    print("Chances left " + str(score) + " \n")
                    print("GUESS THE NUMBER \n")
                    n = int(input())

                    if(n > secNum):
                        range1 = secNum - i
                        if(range1 < 0):
                            range1 = 0
                        range2 = secNum+i
                        if(range2>10):
                            range2 = 10
                        print("\nNumber greater than Secret number ")
                        print("number is  between " + str(range1) +
                            " and " + str(range2) + "\n")
                        score -= 1
                    elif(n < secNum):
                        range1 = secNum - i
                        range2 = secNum+i
                        if(range2 > 10):
                            range2 = 10
                        if(range1 < 0):
                            range1 = 0

                        print("\nNumber smaller than Secret number")
                        print("number is  between " + str(range1) +
                            " and " + str(range2)+"\n")
                        score -= 1
                    if(n == secNum):
                        print("Secret number " + str(secNum) +
                            " guessed successfully")
                        chances = False
                        print("score :" + str(score))
                        guessed = True
                        break
                    i -= 1

            if(guessed == False):
                print("YOU COULDN'T GUESS THE NUMBER : " + str(secNum))

# Input given is not proper
    else:
        print("Wrong input. PLEASE ENTER EITHER A OR B")
