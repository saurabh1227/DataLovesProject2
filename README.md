# DataLovesProject2
TicTocToe-Python Project
1.	import os    
2.	import time    
3.	    
4.	board = [' ',' ',' ',' ',' ',' ',' ',' ',' ',' ']    
5.	player = 1    
6.	   
7.	########win Flags##########    
8.	Win = 1    
9.	Draw = -1    
10.	Running = 0    
11.	Stop = 1    
12.	###########################    
13.	Game = Running    
14.	Mark = 'X'    
15.	   
16.	#This Function Draws Game Board    
17.	def DrawBoard():    
18.	    print(" %c | %c | %c " % (board[1],board[2],board[3]))    
19.	    print("___|___|___")    
20.	    print(" %c | %c | %c " % (board[4],board[5],board[6]))    
21.	    print("___|___|___")    
22.	    print(" %c | %c | %c " % (board[7],board[8],board[9]))    
23.	    print("   |   |   ")    
24.	   
25.	#This Function Checks position is empty or not    
26.	def CheckPosition(x):    
27.	    if(board[x] == ' '):    
28.	        return True    
29.	    else:    
30.	        return False    
31.	   
32.	#This Function Checks player has won or not    
33.	def CheckWin():    
34.	    global Game    
35.	    #Horizontal winning condition    
36.	    if(board[1] == board[2] and board[2] == board[3] and board[1] != ' '):    
37.	        Game = Win    
38.	    elif(board[4] == board[5] and board[5] == board[6] and board[4] != ' '):    
39.	        Game = Win    
40.	    elif(board[7] == board[8] and board[8] == board[9] and board[7] != ' '):    
41.	        Game = Win    
42.	    #Vertical Winning Condition    
43.	    elif(board[1] == board[4] and board[4] == board[7] and board[1] != ' '):    
44.	        Game = Win    
45.	    elif(board[2] == board[5] and board[5] == board[8] and board[2] != ' '):    
46.	        Game = Win    
47.	    elif(board[3] == board[6] and board[6] == board[9] and board[3] != ' '):    
48.	        Game=Win    
49.	    #Diagonal Winning Condition    
50.	    elif(board[1] == board[5] and board[5] == board[9] and board[5] != ' '):    
51.	        Game = Win    
52.	    elif(board[3] == board[5] and board[5] == board[7] and board[5] != ' '):    
53.	        Game=Win    
54.	    #Match Tie or Draw Condition    
55.	    elif(board[1]!=' ' and board[2]!=' ' and board[3]!=' ' and board[4]!=' ' and board[5]!=' ' and board[6]!=' ' and board[7]!=' ' and board[8]!=' ' and board[9]!=' '):    
56.	        Game=Draw    
57.	    else:            
58.	        Game=Running    
59.	    
60.	print("Tic-Tac-Toe Game Designed By Sourabh Singh")    
61.	print("Player 1 [X] --- Player 2 [O]\n")    
62.	print()    
63.	print()    
64.	print("Please Wait...")    
65.	time.sleep(3)    
66.	while(Game == Running):    
67.	    os.system('cls')    
68.	    DrawBoard()    
69.	    if(player % 2 != 0):    
70.	        print("Player 1's chance")    
71.	        Mark = 'X'    
72.	    else:    
73.	        print("Player 2's chance")    
74.	        Mark = 'O'    
75.	    choice = int(input("Enter the position between [1-9] where you want to mark : "))    
76.	    if(CheckPosition(choice)):    
77.	        board[choice] = Mark    
78.	        player+=1    
79.	        CheckWin()    
80.	    
81.	os.system('cls')    
82.	DrawBoard()    
83.	if(Game==Draw):    
84.	    print("Game Draw")    
85.	elif(Game==Win):    
86.	    player-=1    
87.	    if(player%2!=0):    
88.	        print("Player 1 Won")    
89.	    else:    
90.	        print("Player 2 Won")    
