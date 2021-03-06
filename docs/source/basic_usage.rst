Usage
=====

KeplerMapper adopts the scikit-learn API as much as possible, so it should feel very familiar to anyone who has used these libraries.
  
Python code
~~~~~~~~~~~

.. code:: python

    # Import the class
    import kmapper as km

    # Some sample data
    from sklearn import datasets
    data, labels = datasets.make_circles(n_samples=5000, noise=0.03, factor=0.3)

    # Initialize
    mapper = km.KeplerMapper(verbose=1)

    # Fit to and transform the data
    projected_data = mapper.fit_transform(data, projection=[0,1]) # X-Y axis

    # Create dictionary called 'graph' with nodes, edges and meta-information
    graph = mapper.map(projected_data, data, nr_cubes=10)

    # Visualize it
    mapper.visualize(graph, path_html="make_circles_keplermapper_output.html",
                     title="make_circles(n_samples=5000, noise=0.03, factor=0.3)")

Console output
~~~~~~~~~~~~~~

::

    ..Projecting data using: [0, 1]

    ..Scaling with: MinMaxScaler(copy=True, feature_range=(0, 1))

    Mapping on data shaped (5000L, 2L) using dimensions

    Creating 100 hypercubes.

    created 86 edges and 57 nodes in 0:00:03.614000.

    Wrote d3.js graph to 'make_circles_keplermapper_output.html'

Visualization output
~~~~~~~~~~~~~~~~~~~~

.. figure:: http://i.imgur.com/i3cqQVr.png
   :alt: Click for large

   Visualization

Click here for an `interactive
version <http://mlwave.github.io/tda/make_circles_keplermapper_output2.html>`__.
Click here for an older `interactive
version <http://mlwave.github.io/tda/make_circles_keplermapper_output.html>`__.
