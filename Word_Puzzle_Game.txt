import random

def word_choose():
    word=["Father","Parents","Numbers","Dry","Different","Green","Aeroplane","Mother","Happy","Game","Teacher","Alphabet","Welcome","Hello","Sorry"]
    pick=random.choice(word)     #Makes different choices every time
    return pick.upper()

def jumble_word(word):
    random_word = random.sample(word, len(word))
    jumbled = ''.join(random_word)
    return jumbled
        
def play():
    score=0       #variable for counting score
    turn=5        #Playing time
    while turn>0:
        print("Arrange the letters to form a valid word:")
        pick_word = word_choose()       #calling word_choose() function
        pickwordlist=[pick_word.upper(),pick_word.lower(),pick_word.capitalize()]   # for UpperCase, LowerCase, Capitalize the picked word and store in a list 
        jumble = jumble_word(pick_word)   #calling jumble_word() function to jumble words
        print(jumble)
        answer = input()

        if answer in pickwordlist:        # answer is in the list or not
            score+=1       #increment by 1 if answer is right
            print("\nCorrect\n")
        else:
            print("\nWrong\n")
            score-=1           # decrement by 1 if answer is wrong

        turn-=1
        
    print("Net Score is",score)


play()
