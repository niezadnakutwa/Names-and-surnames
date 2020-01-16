# Names-and-surnames
Program that reads file with names and surnames, than creates separate files for names and surnames
namesandsurnames = []
with open("namesandsurnames.txt", "r") as file:
    for line in file:
        namesandsurnames.append(tuple(line.replace("\n", "").split()))

    
with open("names.txt", "w") as file:
    for item in namesandsurnames:
        file.write(item[0] + "\n")

with open("surnames.txt", "w") as file:
    for item in namesandsurnames:
        try:
            file.write(item[1] + "\n")
        except IndexError:
            file.write("\n")
