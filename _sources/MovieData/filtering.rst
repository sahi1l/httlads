Filtering the data
------------------

Let’s start by only looking at films that cost over a million dollars to
make.

Create a variable called ``budget_df`` that contains all columns for the
movies whose budget was over a million dollars.

.. code:: ipython3

    budget_df = []
    budget_df.shape


.. fillintheblank:: mov_expensive_movies

   How many movies have a budget over 1 million dollars?

   - :7208: Is the correct answer
     :7405: Budget should be over (not including) 1 million dollars
     :x: catchall feedback


With this more manageable list of 7000+ movies, I’d like to have a way
to look up the budget of a particular movie.

Create a Series object called ``budget_lookup`` such that you are able
to use a call to ``budget_lookup['Dead Presidents']`` to find the budget
of that movie.

.. code:: ipython3

    budget_lookup = []
    budget_lookup['Dead Presidents']


.. fillintheblank:: mov_dead_presidents_budget

   What was the budget for Dead Presidents?

   - :10000000: Is the correct answer
     :x: catchall feedback


I have figured out that the first (alphabetically) movie whose title
starts with an ‘A’ is ‘A Bag of Hammers’ and the last movie that starts
with a ‘B’ is ‘Byzantium’.

.. code:: ipython3

    budget_lookup[budget_lookup.index.str.startswith('A')].sort_index()[[0]]




.. parsed-literal::

    title
    A Bag of Hammers    2000000
    dtype: int64



.. code:: ipython3

    budget_lookup[budget_lookup.index.str.startswith('B')].sort_index()[[-1]]




.. parsed-literal::

    title
    Byzantium    10000000
    dtype: int64



Use that knowledge to create a series that contains budget informations
for all the movies that start with an ‘A’ or a ‘B’.

HINT: No need to use startswith like I did above, just use the movie
titles to do a slice.

.. code:: ipython3

    budget_lookup_as_and_bs = []
    budget_lookup_as_and_bs.shape


.. fillintheblank:: mov_a_b_movies

   How many movies with a budget of over a million dollars and whose title
   starts with an ‘A’ or a ‘B’ are there?

   - :933: Is the correct answer
     :x: catchall feedback

