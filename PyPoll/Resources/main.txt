import csv

print("Election Result")
print("-------------------------")

votes = 0
list = {}
most_count =0
Winner = ""
with open("election_data.csv", 'r') as csvfile:
    csvheader = csv.reader(csvfile, delimiter = ',')
    csvheader_next = next(csvheader)

    for row in csvheader:
        
        
        candidate = row[2]
    
        if candidate in list:
            list[candidate] = list[candidate] + 1
        else:
            list[candidate] =1
        votes = votes + 1
    print("Total Votes: " + str(votes))
print("-------------------------")   
for key, value in list.items():
    number = float(value)/float(votes)   
    percentage = "{:.0%}".format(number)
    print(f"{key} : {percentage} ({value})")
        #print(votes)
    if value > most_count:
        Winner = key
        most_count = value
print("-------------------------")           
print("Winner: "+ str(Winner))
print("-------------------------")
    #print(list)
    #print("Total Votes" + str(votes))
    