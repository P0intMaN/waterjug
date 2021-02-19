
jug1 = int(input('Enter the jug1 value: '))              # capacity of jug1
jug2 = int(input("Enter the jug2 value: "))              # capacity of jug2
 
finalJug1 = int(input("Enter the final jug1 value: "))   # final jug1 values
finalJug2 = int(input("Enter the final jug2 value: "))   # final jug2 values
 
goalState = (finalJug1,finalJug2)                        # this is what we need
jugValues = (jug1,jug2)                                  # stores the capacity

openList   = []           # stores all the newly discovered possibilities.
closedList = []           # stores all the explored possibilites.

initialValue  = (0,0)
flag = 0
openList.append(initialValue)
while(len(openList)!=0 or goalState not in closedList):

    for x,y in openList:
        
        if x<jug1:                                 # completely filling jug1
            currentState = (jug1,y)
            if currentState == goalState:
                flag = 1
                closedList.append(currentState)
                break
            elif currentState not in closedList:
                openList.append(currentState)        
        
        if y<jug2:                                 # completely filling jug2
            currentState = (x,jug2)
            if currentState == goalState:
                closedList.append(currentState)
                flag = 1
                break
            elif currentState not in closedList:
                openList.append(currentState)                     
        
        if x>0:                                    # empty jug1
            currentState = (0,y)
            if currentState == goalState:
                closedList.append(currentState)
                flag = 1
                break
            elif currentState not in closedList:
                openList.append(currentState)                                    
        
        if y>0:                                    # empty jug2
            currentState = (x,0)
            if currentState == goalState:
                closedList.append(currentState)
                flag = 1
                break
            elif currentState not in closedList:
                openList.append(currentState)        
              

        if x<jug1 and y>0:                          # transfer from jug2 to jug1
            currentState = (min(jug1,(x+y)),max(0,(x+y)-jug1))
            if currentState == goalState:
                closedList.append(currentState)
                flag = 1
                break
            elif currentState not in closedList:
                openList.append(currentState)        

        if y<jug2 and x>0:                          # transfer from jug1 to jug2
            currentState = (max(0,(x+y)-jug1),min(jug2,(x+y)))
            if currentState == goalState:
                closedList.append(currentState)
                flag = 1
                break
            elif currentState not in closedList:
                openList.append(currentState)        

        done = openList.pop(0)
        closedList.append(done) 

    if flag:
        break



if flag:
    for i in closedList:
        print(i)
    
    print("solved")


if len(openList) == 0 and (goalState not in closedList):
    print("No solution possible")


# cap(4,3)   (1,3) ---> (4,0)   
#            (x,y)      (min(jug1,(x+y)), max(0,(x+y)-jug1))             
#            (3,3) ---> (4,2)   
