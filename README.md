# Become an Expert!

If you are looking to become an expert, check out my books:

* [Exercise Python][0]
* [Master Data Analysis with Python][0]
* [Master Machine Learning with Python][0]

They are all extremely comprehensive and offer lots of exercises with detailed solutions.

[0]: https://www.dunderdata.com/store

# Mininally Sufficient Pandas Guidelines

This notebook contains a summary of all the guidelines in this tutorial along with a list of attributes and methods that provide nearly all of the functionality of Pandas.

Minimally sufficient Pandas
* is simple, explicit, straightforward, and boring
* has one obvious way to accomplish a task
* uses this obvious way every single time
* is easier to retain in memory
* is easier to read and debug by yourself an others
* uses less of the library by eliminating methods that provide no additional functionality
* avoids Pandas bugs because of less code
* doesn't rely on being tricky to impress friends
* makes it easier to use in production

* Selecting Subsets of Data
    * Select a single column of data with the brackets
    * Do not use dot notation
    * Be explicit and use `loc` and `iloc`
    * Never use `ix`
    * No need to use `at` or `iat`
* Handling the `SettingWithCopyWarning`
    * Know the three cases when it appears
        * Correct assignment with side effects
        * No assignment
        * Correct assignment without side effects
    * To handle the warning, you will be in one of two scenarios
        * You want to work with a new independent DataFrame - use the `copy` method
        * You want to work with original DataFrame. Assign data with a single indexer, `loc`. Avoid chained indexing.
* Method Duplication
    * Many methods are aliases or provide no extra functionality. Only use one
    * All operators have methods. Only use methods when necessary 
    * Always use Pandas methods and not builtin Python functions
* Say No to `apply`
    * `apply` is an automated for loop that passes each column or row to a user-defined function
    * Use `apply` as a method of last resort
    * Using `apply` with `axis='columns'` is one of the slowest operations in all of Pandas
* Standardizing `groupby`
    * Know the three components
        * Grouping columns
        * Aggregating columns
        * Aggregating functions
    * Use the syntax `df.groupby('grouping columns').agg({'aggregating column': 'aggregating function'})
* Handling a MultiIndex
    * A MultiIndex is difficult to make selections and further process
    * I suggest having a single level index
    * Rename the columns and reset the index after a groupby
* Say no to `apply` with `groupby`
    * Can be extremely slow to use `apply` with `groupby`
    * Call all methods independent of the group, outside of the custom function
* Similarity between groupby, pivot_table, crosstab
* Similarity between melt, pivot, stack, unstack

## Minimal set of DataFrame attributes and methods
Below is a short list of DataFrame attributes and methods that allows you maximum coverage of the library.

* T
* abs
* all
* any
* append
* asfreq
* astype
* clip
* columns
* copy
* corr
* count
* cov
* cummax
* cummin
* cumprod
* cumsum
* describe
* diff
* drop
* drop_duplicates
* dropna
* dtypes
* equals
* expanding
* fillna
* groupby
* head
* idxmax
* idxmin
* iloc
* index
* interpolate
* isin
* isna
* loc
* max
* mean
* median
* melt
* merge
* min
* mode
* nlargest
* notna
* nsmallest
* nunique
* pct_change
* pivot_table
* plot
* prod
* quantile
* rank
* rename
* replace
* resample
* reset_index
* rolling
* round
* sample
* select_dtypes
* shape
* shift
* sort_index
* sort_values
* std
* sum
* tail
* to_csv
* to_sql
* values
* var

[1]: http://www.globalbigdataconference.com/santa-clara/3rd-annual-global-artificial-intelligence-conference-108/speaker-details/theodore-petrou-73077.html
