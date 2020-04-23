# Crosstabulation



# Let's create a quick data set
from StringIO import StringIO

data ="""\
Sample   Brands   Expensive
1        Gucci     Yes
2Prada Yes
3 Nike No
4 Puma No
5 Luis Vutton Yes"""
#Store as dframe

dframe = pd.read_table(StringIO(data),sep='\s+')
# Show
dframe

# Now we can create a cross-tabulation table, which is basically just a frequency table
pd.crosstab(dframe.Brands,dframe.Expensive,margins=True)

# And thats about it as far as it's general use.
# We'll use it in examples in the final projects!
 
