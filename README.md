# Spotify Recommender

A music recommendation system

## Steps to Run

1. Download the audio dataset from [AudioSet](https://research.google.com/audioset/download.html). Scroll down to the section where it says "Manually download" and get the compressed `tar.gz` file. Double click to uncompress in your project repository. These are youtube videos that have been encoded using the [MAX-Audio-Embedding-Generator](https://github.com/IBM/MAX-Audio-Embedding-Generator). 

2. Run all cells in `Spotify recommender.ipynb` notebook. The result:
	-  Ensure we are only extracting music audio
	-  Cut audio to be 10 seconds
	-  Store in a list of JSON (a usable format)

3. Run all cells in `Annoy.ipynb` which uses a nearest neighbor algorithm [ANNOY](https://github.com/spotify/annoy) to take an input audio sample and return a list of recommendations within our dataset.


## Embedding Generation

You don't need the following steps for this project. But adding context to what happens behind the scenes. This is required if you want to generate the embeddings yourself from raw wav files.

1. Execute these steps under [Run Locally](https://github.com/IBM/MAX-Audio-Embedding-Generator#run-locally) to build the docker app and have it running on port 5000.

2. Once step 1 is complete, you should be able to type `http://localhost:5000` and have it load the UI. Play around by uploading a wav file and seeing the corresponding embedding generated at the output.

3. Go to `demo.ipynb` - this notebook has code to convert a wav file to it's embeddings. It makes a call to the Audio Embedding service.

## Fun Next Steps

We could containerize this application. Some Ideas:
- Create a UI that requests an Upload of a WAV file and potential start and end timestamps (10 seconds)

## Resources

[1] AudioSet Download: https://research.google.com/audioset/download.html

[2] MAX Audio Embedding Generator: https://github.com/IBM/MAX-Audio-Embedding-Generator

[3] Annoy slidedeck: https://www.slideshare.net/erikbern/approximate-nearest-neighbor-methods-and-vector-models-nyc-ml-meetup

[4] Annoy explained in more detail: https://www.youtube.com/watch?v=QkCCyLW0ehU
