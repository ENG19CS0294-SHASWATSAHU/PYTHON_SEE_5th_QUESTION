# PYTHON_SEE_5th_QUESTION
Program is given in debug_exam.py and Instructions are given in ReadMe file.
# Fork the repository and commit the changes.
# Answers should be given for all three questions here.
def uniqueUpdate(data1, data2):
    # Initially empty dictionary
    dupKeys = {}

    # Examine every (k, v2) pair in data2
    for k, v2 in data2.items():
        # Search for a key-value pair
        # with key = k in data1
        # (no such pair found yet)
        kFound = False

        for [k1, v1] in data1:
            if k1 == k:
                # Found pair with key = k
                kFound = True

                if v1 != v2:
                	# Remove (k, v1) from data1
                	data1.add(k,[v1,v2]) # Add (k, [v1, v2]) to dictionary
                	dupKeys[k] = [v1,v2]
  
        # After the loop, check if
        # k was not found
        if not kFound:
            # Add (k, v2) to data1
            data1.append([k, v2])

    # After processing all (k, v2) in
    # data2, return the dictionary
    return dupKeys
## DO NOT MODIFY BELOW THIS LINE! ##
#This part of the code reads input in
#the following format:Page 4 of 5
#Line 1: A positive integer n1
#representing the number of key value
#pairs in data1
#Lines 2 to n1+1: Two integers k v
#per line representing the key and
#value (these n1 key value pairs are
#added to data1)
#Line n1+2: A positive integer n2
#representing the number of key value
#pairs in data2
#Lines n1+3 to n1+n2+2: Two integers
#k and v per line representing the
#key and value (these n2 key value
#pairs are added to data2)
#This also prints the output in the
#following format after calling the
#uniqueUpdate function:
#data1
#data2 (should remain the same)
#dup (the dictionary returned)

import sys
if _name_ == '_main_':
    data1 = {}
    n1 = int(input())
    for _ in range(n1):
        k, v = map(int, input().split())
        if k in data1:
            sys.exit("Illegal: data1")
        data1[k] = v
    data2 = []
    n2 = int(input())
    for _ in range(n2):
        k, v = map(int, input().split())
        for [k2, v2] in data2:
            if k2 == k:
                sys.exit("Illegal: data2")
        data2.append([k, v])
dup = uniqueUpdate(data1, data2)
print(data1)
print(data2)
print(dup)
