# Wikipedia Analysis in Apache Spark

Use Apache Spark to analyze Wikipedia data.

For example, [this notebook](/notebooks/1a_gis_analysis_of_wikipedia_with_spark_h3_and_deckgl.ipynb) parses the Wikipedia dump for [mediawiki coord templates](https://en.wikipedia.org/wiki/Template:Coord) to produce maps like the one shown below, visualizing all `{{coord...}`'s in the English Wikipedia :

![Map of all coordinate templates in Wikipedia](assets/all_wikipedia_coords.png "Map of all coordinate templates in Wikipedia")

Notebooks in this repository were tested using the Jupyter `all-spark-notebook` launched with the script below.

```
docker run --dns=8.8.8.8 \
           --rm -p 0.0.0.0:8888:8888 \
           -p 0.0.0.0:4040:4040 \
           -e JUPYTER_ENABLE_LAB=yes \
           -v `pwd`:/home/jovyan/work \
           jupyter/all-spark-notebook \
           start-notebook.sh --NotebookApp.token=$reasonable_password
```

Your milage may vary getting the deck.gl and/or kepler.gl cells to render correctly on Google Colab or Databricks notebooks.
