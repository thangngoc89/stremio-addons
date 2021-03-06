### Stream Response

**One of the following must be passed** to point to the stream itself

* ``url`` - direct URL to a video stream - http, https, rtmp protocols supported
* ``externalUrl`` - URL to the video, which should be opened in a browser (webpage), e.g. link to Netflix
* ``yt_id`` - youtube video ID, plays using the built-in YouTube player
* ``infoHash`` and/or ``fileIdx`` - info hash of a torrent file, and mapIdx is the index of the video file within the torrent; **if fileIdx is not specified, the largest file in the torrent will be selected**
* ``mapIdx`` - alias to ``fileIdx``, specifies index of file in case of BitTorrent

**Additional properties to provide information / behaviour flags**

``name`` - _optional_ - name of the stream, e.g. "Netflix"; the add-on name will be used if not specified

``title`` - _optional_ - title of the stream; usually used for stream quality

``availability`` - _optional_ - 0-3 integer representing stream availability, in the context of P2P streams - 0 not available, 1 barely available, 2 OK, 3 highly available

``tag`` - _optional_ - array, optional tags of the stream; use ``"480p"``, ``"720p"``, ``"1080p"``/``"hd"`` or ``"2160p"`` to specify quality

``isFree`` - _optional_ - set this to ``true`` if the stream si free of charge

``isSubscription`` - _optional_ - set this to ``true`` if this stream requires a subscription (e.g. Netflix)

``isPeered`` - _optional_ - set this to ``true`` if this stream is peered locally and therefore delivered with a high speed; useful for areas with slow internet connections, such as India

``subtitles`` - _optional_ - [``Subtitles Objects``](/docs/api/subtitles/subtitles.object.md) representing subtitles for this stream

``live`` - _optional_ - boolean, specify if this is a live stream; this will be auto-detected if you're using HLS

``repeat`` - _optional_ - boolean, true if you want stremio to do ``stream.find`` again with the same arguments when the video ends, and play the result

``geos`` - _optional_ - use if the stream is geo-restricted - array of ISO 3166-1 alpha-2 country codes **in lowercase** in which the stream is accessible

``widgetSidebar`` - _optional_ - URL to a page that will be shown in the Player sidebar instead of usual contents; the page will be rendered in a restricted web view, appending "?item_hash=" at the end with Item Hash

``widgetPlayer`` - _optional_ - URL to a page that will replace the sit on top of the entire Player; the page will be rendered in a restricted web view, appending "?item_hash=" at the end with Item Hash; useful for things like YouTube/Vimeo embeds, as well as showing additional information/functionality when player is paused

``widgetPlayerStates`` - _optional_ - array of the states in which the ``widgetPlayer`` is shown; default is ``["buffering", "loading"]``, which means it will be shown during loading
  
 Possible states are:
  
  * ``buffering`` - while the video is buffering
  * ``loading`` - white the video is initially loading
  * ``paused`` - while the video is paused
  * ``postplay`` - after the video has finished playing
  * ``error`` - upon player error
  * ``device`` - when casting to a device
  * ``replaceplayer`` - entirely replaces the default player with the widget

``meta`` - _optional_ - object, used to specify ``{ season: X, episode: Y }`` in case you're using a [``Stream Object``](/documentation/protocol.md#stream-object) for ``videos`` for a series
