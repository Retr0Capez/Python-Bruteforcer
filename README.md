# Python-Bruteforcer
#I made this password cracker for my Mandeville Junior High Science Fair Project in 2016.
#By James Land
  #Copyright (C) 2016 James Land

    #This program is free software: you can redistribute it and/or modify
    #it under the terms of the GNU General Public License as published by
    #the Free Software Foundation, either version 3 of the License, or
    #any later version.

    #This program is distributed in the hope that it will be useful,
    #but WITHOUT ANY WARRANTY; without even the implied warranty of
    #MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
    #GNU General Public License for more details.

    #You should have received a copy of the GNU General Public License
    #along with this program.  If not, see <http://www.gnu.org/licenses/>.
import itertools
import time


Alphabet = ("abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ1234567890-_.")


Password = input("What is your password?\n")


start = time.time()


counter = 1


CharLength = 1


for CharLength in range(25):

    
    passwords = (itertools.product(Alphabet, repeat = CharLength))

    
    print("\n \n")

    
    print("currently working on passwords with ", CharLength, " chars")
    print("We are currently at ", (counter / (time.time() - start)), "attempts per seconds")
    print("It has been ", time.time() - start, " seconds!")
    print("We have tried ", counter, " possible passwords!")

    
    for i in passwords:

        
        counter += 1
        
        
        i = str(i)

        
        i = i.replace("[", "")
        i = i.replace("]", "")
        i = i.replace("'", "")
        i = i.replace(" ", "")
        i = i.replace(",", "")
        i = i.replace("(", "")
        i = i.replace(")", "")

        
        if i == Password:

            
            end = time.time()

            
            timetaken = end - start

            
            print("Found it in ", timetaken, " seconds and ", counter, "attempts")

            
            print("That is ", counter / timetaken, " attempts per second!")

            
            print(i)

        
            input("Press enter when you have finished")

        
            exit()


