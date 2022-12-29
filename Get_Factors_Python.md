Fuction that connects to [FactorDB](http://factordb.com/) and returns a list of factors that were found
````python3
def get_factor_list_from_factordb(n):
    factor_list=[]
    #Establishing a connection with factordb
    Rq= requests.get("http://factordb.com/api", params={"query": str(n)}).json()
    #Extracting factors from the response
    for i in range(len(Rq['factors'])):
        factor_list.append(int(Rq['factors'][i][0]))
    #Return factors list
    return factor_list
    
````
