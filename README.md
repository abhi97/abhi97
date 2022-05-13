#obtain state of all 7 nets of given combinational circuit  

#input on logic gate XNOR(U0) at net number 1
i1 = int(input('Enter 1st input: '))

#input on logic gate XNOR(U1) at net number 3
i3 = int(input('Enter 3rd number: '))

#input on logic gate XNOR(U0) at net number 4
i4 = int(input('Enter 4th input: '))

#printing input i1 at net 1
print("The state of i1 is",i1)
   
#defining output logic of NOT gate(U0) having input i1
def U0(i1):
    return ~i1+2

i2 = U0(i1)     #assigning  NOT gate output (i2) logic with i1 input

#printing intermediate output i2 at net 2
print("the state of i2 is", U0(i1))

#printing input i3 at net 3
print("The state of i3 is",i3) 

#printing input i4 at net 4
print("The state of i4 is",i4) 

#defining output logic of XNOR gate(U1) having input i1
def U1(i2,i3):
	if(i2== i3):
		return 1
	else:
		return 0   
i5= U1(i2,i3)      #assigning  XNOR gate intermediate output(i5) logic with i2,i3 input

#printing intermediate output i5 at net 5
print("The state of i5 is",U1(i2,i3))

#defining output logic of NOR gate(U2) having input i2,i4,i5
def U2(i2,i4,i5):
	if i2 == 0 and i4 == 0 and i5 == 0:
	    return 1
	else:
		return 0

#printing primary output o6 at net 6
print("the state of o6 is",U2(i2,i4,i5))   

#defining output logic of NAND gate(U3) having input i4,i5
def U3(i4,i5):
	if i4 == 1 and i5 == 1:
		return 0
	else:
		return 1 
		
#printing primary output o7 at net 7		
print("the state of o7 is",U3(i4,i5))
