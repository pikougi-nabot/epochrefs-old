# Alternative Interfaces

Subsets of IMDb data are available for access to customers for personal and non-commercial use. You can hold local copies of this data, and it is subject to our terms and conditions. Please refer to the Non-Commercial Licensing and copyright/license and verify compliance.

## IMDb Dataset Details

Each date-based folder in the S3 bucket contains datasets in gzipped, tab-separated-values (TSV) format. The first line in each file contains headers that describe what is in each column. A ‘\N’ is used to denote that a particular field is missing or null for that title/name. The available datasets (S3 object key) are as follows:

* **title.basics.tsv.gz** – Contains the following information for titles:
  * tconst (string) - alphanumeric unique identifier of the title
  * titleType (string) – the type/format of the title (e.g. movie, short, tvseries, tvepisode, video, etc.)
  * primaryTitle (string) – the more popular title / the title used by the filmmakers on promotional materials at the point of release
  * originalTitle (string) - original title, in the original language
  * isAdult (boolean) - 0: non-adult title; 1: adult title
  * startYear (YYYY) – represents the release year of a title. In the case of TV Series, it is the series start year
  * endYear (YYYY) – TV Sereis end year. ‘\N’ for all other title types
  * runtimeMinutes – primary runtime of the title, in minutes
  * genres (string array) – includes up to three genres associated with the title
* **title.crew.tsv.gz** – Contains the director and writer information for all the titles in IMDb. Fields include:
  * tconst (string)
  * directors (array of nconsts) - director(s) of the given title
  * writers (array of nconsts) – writer(s) of the given title
* **title.episode.tsv.gz** – Contains the tv episode information. Fields include:
  * tconst (string) - alphanumeric identifier of episode
  * parentTconst (string) - alphanumeric identifier of the parent TV Series
  * seasonNumber (integer) – season number the episode belongs to
  * episodeNumber (integer) – episode number of the tconst in the TV series.
* **title.principals.tsv.gz** – Contains the principal cast for titles
  * tconst (string)
  * principalCast (array of nconsts) – title’s top-billed cast
* **title.ratings.tsv.gz** – Contains the IMDb rating and votes information for titles
  * tconst (string)
  * averageRating – weighted average of all the individual user ratings
  * numVotes - number of votes the title has received
* **name.basics.tsv.gz** – Contains the following information for names:
  * nconst (string) - alphanumeric unique identifier of the name/person
  * primaryName (string)– name by which the person is most often credited
  * birthYear – in YYYY format
  * deathYear – in YYYY format if applicable, else ‘\N’
  * primaryProfession (array of strings)– the top-3 professions of the person
  * knownForTitles (array of tconsts) – titles the person is known for
