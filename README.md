# How To Build and Run

* Unzip twitter.zip
* Run "java -cp ./twitter.jar:code-challenge.jar -Dfactory=com.twitter.ChirpServiceFactoryImpl com.twitter.challenge.tester.Main"

# Design Constraints

* Making use of a persistent storage for storing mappings between tiny hash and its corresponding expanded url. 
* Making use of a persistent storage for storing mappings between a long id and its corresponding chirp instance.
* Making use of a cache instance to store the mapping between tiny hash to its corresponding expanded url, so that we can avoid fetch expanded url, given a tiny url in an efficient manner without needing persistent storage lookup.
* Making use of a cache instance to store the mapping between chirp id to its corresponding chirp instance, so that we can avoid fetch chirp instance, given a long id in an efficient manner without needing persistent storage lookup.
* Make use of cache for tiny hash and chirp id lookup, if not available, lookup in persistent storage and then store it into cache. This way, only the most used mappings at any point in time, would reside on the cache and thus helping avoid persistent storage lookups. 

