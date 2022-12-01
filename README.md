# add_del_sort

#using python sets and lambada to combine a list with a source then remove a list from it and then sort it length wise and  reverse alphabetically
<code>
def add_del_sort (original: list, add: list, delete: list) -> list :
    #cast original list to set
    s_original = set(original)
    #using try except to catch possible KeyError if items in delete does not exist in the original list 
    try:
        for i in add:
            s_original.add(i)
        for i in delete:
            s_original.remove(i)
    except KeyError:
        print("Some values in delete can not be found in the original list even after addition.")
    
    finally:
        #casting back to list and sorting it using lambda 
        s = list(s_original)
        s = sorted(s, key= lambda x : (len(x),x[0]), reverse =1)
    
    return s

print(add_del_sort(original,add,delete))

</code>
