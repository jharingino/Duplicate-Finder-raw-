# Duplicate-Finder-raw-
Manual creation of two tables, determine the number of repetition of elements in those two tables
'''
Created by Engr. Joshua Hans C. Aringino
Developed: OCT. 2019
version 1 
this is a sample of counting duplicate elements from 2 different tables
'''

# this will check all the appearances of element 'x' in tb_all list
def o_count(x):
	count = tb_all.count(x)
	return count	# return the number of appearances


tb_one = [] 	# first table
tb_two = [] 	# second table
tb_newlist = [] # for new output list

while True:
	try:
		# insert objects for TABLE 1
		tbo_range = int(input('enter the num. of items for tb_one: '))
		while len(tb_one) <= tbo_range-1:
			ui = input('enter the object here: ')
			tb_one.append(ui)
		print(tb_one)	
		
		# insert objects for TABLE 2
		tbt_range = int(input('enter the num. of items for tb_two: '))
		while len(tb_two) <= tbt_range-1:
			ui = input('enter the object here: ')
			tb_two.append(ui)
		print(tb_two)
		
		# input all tables to one list
		tb_all = list(tb_one + tb_two)
		
		# analyze tables and produce output
		print('Analyzing duplicate objects. please wait.....')
		print('Output:')
		
		
		# insert all elements of 'tb_one' into 'tb_newlist' list
    # subject for revision 
		for i in tb_one:
			tb_newlist.append(i)    # this will only add each element in tb_one, but not analyze if the same number is exisitng e.g. [13,13,5]
     # revision end
			
		# check each elements of tb_two if it exist in tb_newlist.
		# this is used to prevent duplicate element from being recounted and displayed again
		for o in tb_two:
			if o not in tb_newlist:
				tb_newlist.append(o)
		
		# get each elements in tb_newlist and call o_count function
		for p in tb_newlist:		
			print(p, '=', o_count(p))
		print('\n')
		
		# clear list tables
		tb_one.clear()
		tb_two.clear()
		
	except(ValueError,TypeError,SyntaxError):
		print('Alert an Error occured!')

user_input = input('press any key to stop')
