# highpeak_assignment
assignment given 
in_file =open("sample_input.txt","r")
#open output file to write output
out_file = open("output.txt","w+")
goods={}
out_list=[]
#reading input file 
for f in in_file:
    toRead_index_price=f.index(":")
    print(f[toRead_index_price+1:].strip())
    print(f[:toRead_index_price])
    goods[f[:toRead_index_price]]=f[toRead_index_price+1:].strip()
print(goods) 
single_prices=list(goods.values())


single_prices=[int(i)for i in single_prices]
#sorted list in decsending order to get prices to be distributed in order
single_prices.sort(reverse=True)
print(single_prices)
#taking inputs
num=int(input("Enter number of employees: "))
len_considered=(len(single_prices)-num)

print(leng_considered)

#finding minimum difference between highest and lowest
for i in range(len_considered):
    maxprice=single_prices[i]
    minprice=single_prices[num+i]
    if i == 0:
        diff=maxprice-minprice
        idx_choosen=i
    elif (maxprice-minprice)<diff:
        diff=maxprice-minprice
        idx_choosen=i

choosen_prices=single_prices[idx_choosen:num+idx_choosen]
#differnce between high and low price
diff=max(choosen_prices)-min(choosen_prices)
print("diff",diff)

cnt=0
for key,value in goodies.items():
    single_prices[cnt]
    print(value)
    if int(value)in choosen_prices and cnt<num:
        str1=key+": "+value
        #preparing  list for output
        out_list.append(str1)
        cnt+=1
        print(str1)
        
out_file.write("The goodies selected for distribution: ")

out_file.write("\n")

for i in out_list:
    out_file.write(i)
    out_file.write("\n")
out_file.write("And the difference between the chosen goodie with highest price and the lowest price is "+str(diff))

in_file.close()
out_file.close()        
