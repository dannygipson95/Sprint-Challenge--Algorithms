#### Please add your answers to the ***Analysis of  Algorithms*** exercises here.

## Exercise I

a) This could be O(n) because it changes constantly with the size of n


b) This may be O(n^2) because there are two loops


c) I feel like this one may be O(n) because it has very few steps other than the recursive call

## Exercise II

I could start at the middle floor and drop the egg. Then check to see if the number of eggs has decremented by one. If so find the middle floor between the ground and that floor and repeat, and vice versa for not being broken. until I am left with two floors, and if the egg is broken return the "middle" or lower option, if not return the floor above. I believe the runtime on this would be logarithmic so O(log(n))

def eggFunction(n, low = 1):
    tempEggs = numEggs[:]

    middleFloor = (low+n)//2

    dropEgg(middleFloor)

    if numEggs < tempEggs:
        n = middleFloor
        return eggFunction(n, low = low)
    elif numEggs == tempEggs and n > 2:
        return eggFunction(n, middleFloor)
    elif numEggs == tempEggs and n == 2:
        return n
    else:
        return low



