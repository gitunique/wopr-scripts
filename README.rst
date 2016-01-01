wopr is a neat application for generating visualisations in a terminal.
https://github.com/yaronn/wopr/blob/master/README.md

I wanted to generate coordinates to use on a world map that represents the location of various CERT capabilities around the world.
To do this, a list of ccTLDs per community is used to get the lat and long coordinates for the capital of that country, these are then rendered on the world map available in wopr.

A complete sample is included in cert-communities.xml

.. code-block:: guess 

	export COLOUR=green
	export FILE=input_file
	for cc in $(cat $FILE ); do grep ,$cc, country-capitals.csv; done | awk -F, '{print "<m lat=\""$3"\: lon=\""$4"\" color=\"$COLOUR\">"}'


