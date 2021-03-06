### Meta Element

The response is an array of Metadata objects. 

#### Metadata object

``id`` - **required** - universal identifier, formed like "DOMAIN_id:ID", for example "yt_id:UCrDkAvwZum-UTjHmzDI2iIw".

``type`` - **required** - type of the content; e.g. `movie`, `series`, `channel`, `tv` (see [Content Types](content.types.md))

``name`` - **required** - name of the content

``genre`` - **required**  - genre/categories of the content; array of strings, e.g. ``["Thriller", "Horror"]``

``poster`` - **required** - URL to png of poster; accepted aspect ratios: 1:0.675 (IMDb poster type) or 1:1 (square) ; you can use any resolution, as long as the file size is below 100kb; below 50kb is recommended

``posterShape`` - _optional_ - can be `square` (1:1 aspect) or `regular` (1:0.675) or `landscape` (1:1.77). If you don't pass this, `regular` is assumed

``background`` - _optional_ - the background shown on the stremio detail page ; heavily encouraged if you want your content to look good; URL to PNG, max file size 500kb

``description`` - _optional_ - a few sentances describing your content

``year`` - _optional_ - string - year the content came out ; if it's ``series`` or ``channel``, use a start and end years split by a tide - e.g. ``"2000-2014"``. If it's still running, use a format like ``"2000-"``

``director``, ``cast`` - _optional_  - directors and cast, both arrays of names

``imdbRating`` -  _optional_ - IMDb rating, a number from 0 to 10 ; use if applicable

``dvdRelease`` - _optional_ - DVD release date

``released`` - _optional_ - initial release date; for movies, this is the cinema debut

``inTheaters`` - _optional_ - used only for ``movie`` type, boolean whether this movie is still in theaters or not; if not provided, it will be decided based on ``released`` date

``episodes`` - _optional_ - used for ``series``, array of Episode objects

``videos`` - _optional_ - used for ``channel``, array of Video objects

``uploads`` - _optional_ - used for ``channel``, array of Video objects; same as ``videos`` but **obsolete**

``certification`` - _optional_ - [MPAA rating](http://www.mpaa.org/film-ratings/) - can be "G", "PG", "PG-13", "R", "NC-17"

``runtime`` - _optional_ - human-readable expected runtime - e.g. "120m"

``language`` - _optional_ - spoken language

``country`` - _optional_ - official country of origin

``awards`` - _optional_ - human-readable string that describes all the significant awards

``website`` - _optional_ - URL to official website

``isPeered`` - _optional_ - set this property if you know whether that item can be streamed with peering by the same add-on which is serving the meta

#### Episode object

``number`` - **required** - number of the episode

``season`` - **required** - season number of the episode

``name`` - **required** - name of the episode

``firstAired`` - **required** - Date, air date of the episode

``trailer`` - _optional_ - YouTube ID of the trailer video for the episode

``overview`` - _optional_ - episode overview/summary

#### Video object

``title`` - **required** - title of the video

``publishedAt`` - **required** - Date, publish date of the video

``thumbnail`` - **required** - URL to png of the video thumbnail, in the video's aspect ratio, max file size 5kb

``id`` - _optional_ - YouTube ID of the video

_As an alternative to using a YouTube ID, **you can inherit the [``Stream Object``](/docs/api/stream/stream.response.md)** to point the video to a HTTP URL, BitTorrent, YouTube or any other stremio-supported transport protocol._
