# Language Detector

Using latest ML technology, we can detect the languages used in of any incoming request. We will then assign a weight to each of the languages, based on the percentages and meanings of the words (nouns and adj. are more important then propositions)

We will then use these weights to score the models in the network, based on their performances on the respective languages. The weighted store will be combined with geo-proximity to determine the final model score.
