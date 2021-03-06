---
swagger: "2.0"
x-collection-name: Spotify
x-complete: 0
info:
  title: Spotify Update User Playlist Track
  description: '[Reorder or replace a Playlist''s Tracks](https://developer.spotify.com/web-api/reorder-playlists-tracks/)'
  version: v1
host: api.spotify.com
basePath: /v1
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /albums/{id}/tracks:
    get:
      summary: Get Album Tracks
      description: '[Get an Album''s Tracks](https://developer.spotify.com/web-api/get-albums-tracks/)'
      operationId: get-an-albums-trackshttpsdeveloperspotifycomwebapigetalbumstracks
      x-api-path-slug: albumsidtracks-get
      parameters:
      - in: path
        name: id
        description: The Spotify ID for the album
      - in: query
        name: limit
        description: The maximum number of items to return
      - in: query
        name: market
        description: The market (an ISO 3166-1 alpha-2 country code)
      - in: query
        name: offset
        description: The index of the first item to return
      responses:
        200:
          description: OK
      tags:
      - Music
      - Album
      - Tracks
  /artists/{id}/top-tracks:
    get:
      summary: Get Artist Top Tracks
      description: '[Get an Artist''s Top Tracks](https://developer.spotify.com/web-api/get-artists-top-tracks/)'
      operationId: get-an-artists-top-trackshttpsdeveloperspotifycomwebapigetartiststoptracks
      x-api-path-slug: artistsidtoptracks-get
      parameters:
      - in: query
        name: country
        description: The country (an ISO 3166-1 alpha-2 country code)
      - in: path
        name: id
        description: The Spotify ID for the artist
      responses:
        200:
          description: OK
      tags:
      - Music
      - Artists
      - Tracks
  /me/tracks:
    delete:
      summary: Delete My Tracks
      description: '[Remove Tracks for Current User](https://developer.spotify.com/web-api/remove-tracks-user/)'
      operationId: remove-tracks-for-current-userhttpsdeveloperspotifycomwebapiremovetracksuser
      x-api-path-slug: metracks-delete
      parameters:
      - in: header
        name: Accept
        description: It is used to set specified media type
      - in: query
        name: ids
        description: A comma-separated list of IDs
      responses:
        200:
          description: OK
      tags:
      - Music
      - Me
      - Tracks
    get:
      summary: Get My Tracks
      description: '[Get Current User''s Saved Tracks](https://developer.spotify.com/web-api/get-users-saved-tracks/)'
      operationId: get-current-users-saved-trackshttpsdeveloperspotifycomwebapigetuserssavedtracks
      x-api-path-slug: metracks-get
      parameters:
      - in: header
        name: Accept
        description: It is used to set specified media type
      - in: query
        name: limit
        description: The maximum number of items to return
      - in: query
        name: market
        description: The market (an ISO 3166-1 alpha-2 country code)
      - in: query
        name: offset
        description: The index of the first item to return
      responses:
        200:
          description: OK
      tags:
      - Music
      - Me
      - Tracks
    put:
      summary: Update My Tracks
      description: '[Save Tracks for Current User](https://developer.spotify.com/web-api/save-tracks-user/)'
      operationId: save-tracks-for-current-userhttpsdeveloperspotifycomwebapisavetracksuser
      x-api-path-slug: metracks-put
      parameters:
      - in: header
        name: Accept
        description: It is used to set specified media type
      - in: query
        name: ids
        description: A comma-separated list of IDs
      responses:
        200:
          description: OK
      tags:
      - Music
      - Me
      - Tracks
  /me/tracks/contains:
    get:
      summary: Get My Track Contains
      description: '[Check Current User''s Saved Tracks](https://developer.spotify.com/web-api/check-users-saved-tracks/)'
      operationId: check-current-users-saved-trackshttpsdeveloperspotifycomwebapicheckuserssavedtracks
      x-api-path-slug: metrackscontains-get
      parameters:
      - in: query
        name: ids
        description: A comma-separated list of IDs
      responses:
        200:
          description: OK
      tags:
      - Music
      - Me
      - Tracks
  /tracks:
    get:
      summary: Get Tracks
      description: '[Get Several Tracks](https://developer.spotify.com/web-api/get-several-tracks/)'
      operationId: get-several-trackshttpsdeveloperspotifycomwebapigetseveraltracks
      x-api-path-slug: tracks-get
      parameters:
      - in: query
        name: ids
        description: A comma-separated list of IDs
      - in: query
        name: market
        description: The market (an ISO 3166-1 alpha-2 country code)
      responses:
        200:
          description: OK
      tags:
      - Music
      - Tracks
  /tracks/{id}:
    get:
      summary: Get Track
      description: '[Get a Track](https://developer.spotify.com/web-api/get-track/)'
      operationId: get-a-trackhttpsdeveloperspotifycomwebapigettrack
      x-api-path-slug: tracksid-get
      parameters:
      - in: path
        name: id
      - in: query
        name: market
        description: The market (an ISO 3166-1 alpha-2 country code)
      responses:
        200:
          description: OK
      tags:
      - Music
      - Tracks
  /users/{user_id}/playlists/{playlist_id}/tracks:
    delete:
      summary: Delete User Playlist Tracks
      description: '[Remove Tracks from a Playlist](https://developer.spotify.com/web-api/remove-tracks-playlist/)'
      operationId: remove-tracks-from-a-playlisthttpsdeveloperspotifycomwebapiremovetracksplaylist
      x-api-path-slug: usersuser-idplaylistsplaylist-idtracks-delete
      parameters:
      - in: header
        name: Accept
        description: It is used to set specified media type
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: playlist_id
        description: The Spotify playlist ID
      - in: path
        name: user_id
        description: The users Spotify user ID
      responses:
        200:
          description: OK
      tags:
      - Music
      - User
      - Playlists
      - Tracks
    get:
      summary: Get User Playlist Tracks
      description: '[Get a Playlist''s Tracks](https://developer.spotify.com/web-api/get-playlists-tracks/)'
      operationId: get-a-playlists-trackshttpsdeveloperspotifycomwebapigetplayliststracks
      x-api-path-slug: usersuser-idplaylistsplaylist-idtracks-get
      parameters:
      - in: header
        name: Accept
        description: It is used to set specified media type
      - in: query
        name: fields
        description: A comma-separated list of fields to filter query
      - in: query
        name: limit
        description: The maximum number of items to return
      - in: query
        name: market
        description: The market (an ISO 3166-1 alpha-2 country code)
      - in: query
        name: offset
        description: The index of the first item to return
      - in: path
        name: playlist_id
        description: The Spotify playlist ID
      - in: path
        name: user_id
        description: The users Spotify user ID
      responses:
        200:
          description: OK
      tags:
      - Music
      - User
      - Playlists
      - Tracks
    post:
      summary: Add User Playlist Track
      description: '[Add Tracks to a Playlist](https://developer.spotify.com/web-api/add-tracks-to-playlist/)'
      operationId: add-tracks-to-a-playlisthttpsdeveloperspotifycomwebapiaddtrackstoplaylist
      x-api-path-slug: usersuser-idplaylistsplaylist-idtracks-post
      parameters:
      - in: header
        name: Accept
        description: It is used to set specified media type
      - in: path
        name: playlist_id
        description: The Spotify playlist ID
      - in: query
        name: position
        description: The position to insert the tracks, a zero-based index
      - in: query
        name: uris
        description: A comma-separated list of Spotify track URIs to add
      - in: path
        name: user_id
        description: The users Spotify user ID
      responses:
        200:
          description: OK
      tags:
      - Music
      - User
      - Playlists
      - Tracks
    put:
      summary: Update User Playlist Track
      description: '[Reorder or replace a Playlist''s Tracks](https://developer.spotify.com/web-api/reorder-playlists-tracks/)'
      operationId: reorder-or-replace-a-playlists-trackshttpsdeveloperspotifycomwebapireorderplayliststracks
      x-api-path-slug: usersuser-idplaylistsplaylist-idtracks-put
      parameters:
      - in: header
        name: Accept
        description: It is used to set specified media type
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: playlist_id
        description: The Spotify playlist ID
      - in: path
        name: user_id
        description: The users Spotify user ID
      responses:
        200:
          description: OK
      tags:
      - Music
      - User
      - Playlists
      - Tracks
x-streamrank:
  polling_total_time_average: 0
  polling_size_download_average: 0
  streaming_total_time_average: 0
  streaming_size_download_average: 0
  change_yes: 0
  change_no: 0
  time_percentage: 0
  size_percentage: 0
  change_percentage: 0
  last_run: ""
  days_run: 0
  minute_run: 0
---