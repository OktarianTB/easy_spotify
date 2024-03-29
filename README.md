# Spotify-Wrapper
Easy-Spotify is a python Wrapper for the Spotify Web API. It was conceived with ease of use in mind. It allows you to retrieve data from Spotify such as track or artist information, images, related artists, top tracks, and more.

## Documentation
Install the package as usual.

~~~bash
pip install easy-spotify
~~~

To be able to access Spotify Web API you need to provide easy-spotify with your <code>client_id</code> and <code>client_secret</code> which you can obtain [here](https://developer.spotify.com/dashboard/).

~~~python
from easy_spotify import Spotify

spotify = Spotify(MY_CLIENT_ID, MY_CLIENT_SECRET)
~~~

##### Get Artist or Track ID
Search for an artist or track in Spotify's catalogue and get back the top results.
~~~python
my_artist_id = spotify.get_artist_id("Adele", only_id=False)

my_track_id = spotify.get_track_id("Starboy")
multiple_tracks_id = spotify.get_multiple_track_id(["Starboy"], ["Hello"], ["Cake By The Ocean"])
~~~

##### Artist related methods
~~~python
artist_info_name = spotify.get_artist_info_from_name("Adele")
artist_info_id = spotify.get_artist_info_from_id("ARTIST_ID")

my_albums_name = spotify.get_albums_from_name("Adele")
my_albums_id = spotify.get_albums_from_id("ARTIST_ID")

top_tracks_name = spotify.get_artist_top_tracks_from_name("Adele", just_id_and_name=False)
top_tracks_id = spotify.get_artist_top_tracks_from_id("ARTIST_ID", just_id_and_name=True)

related_artists = spotify.get_related_artists("ARTIST_ID")
~~~

##### Track related methods
~~~python
track_features = spotify.get_track_audio_features("TRACK_ID")
multiple_track_features = spotify.get_multiple_tracks_audio_features(["TRACK_ID", "TRACK_ID", "TRACK_ID"])

track_info = spotify.get_track_info("TRACK_ID")
multiple_track_info = spotify.get_multiple_tracks_info(["TRACK_ID", "TRACK_ID", "TRACK_ID"])
~~~

