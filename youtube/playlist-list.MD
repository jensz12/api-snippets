# Playlist List
Henter en liste over playlister på en kanal

Kræver [API key](https://console.developers.google.com/apis/credentials) & channel id

```php
<?php
$playlists = json_decode(file_get_contents('https://www.googleapis.com/youtube/v3/playlists?key=API-KEY&part=snippet&channelId=CHANNEL-ID&order=date&maxResults=50'), true);
$playlist_id = $playlists['items'][0]['id'];
?>
```
```html
	<div class="row">
				<?php foreach ($playlists['items'] as $playlist): ?>
				<div class="col-sm-6">
					<section class="thumbnail">
						<a href="https://youtube.com/playlist?list=<?php echo $playlist['id']['playlistId']; ?>">
							<img class="img-responsive" src="<?php echo $playlist['snippet']['thumbnails']['medium']['url']; ?>" width="100%" />
						</a>
						<div class="caption">
							<a href="https://youtube.com/playlist?list=<?php echo $playlist['id']['playlistId']; ?>"><h4 class="text-ellipsis"><?php echo $playlist['snippet']['title'];?></h4></a>
						</div>
					</section>
				</div>
				<?php endforeach; ?>
			</div>
```
