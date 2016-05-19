# Playlist List
Henter en liste over playlister på en kanal

Kræver API key & channel id

```php
<?php
$videos = json_decode(file_get_contents('https://www.googleapis.com/youtube/v3/search?key=AIzaSyDBzIBpp0A9HUcrkwhLVJ_k1cLdwrk0pLE&part=snippet&channelId=UCdyZ-HOwl8zSdyfieRURWfg&order=date&maxResults=50&type=playlist'), true);
$latest_video_id = $videos['items'][0]['id']['videoId'];
?>
```
```html
	<div class="row">
				<?php foreach ($videos['items'] as $video): ?>
				<div class="col-sm-6">
					<section class="thumbnail">
						<a href="https://youtube.com/playlist?list=<?php echo $video['id']['playlistId']; ?>">
							<img class="img-responsive" src="<?php echo $video['snippet']['thumbnails']['medium']['url']; ?>" width="100%" />
						</a>
						<div class="caption">
							<a href="https://youtube.com/playlist?list=<?php echo $video['id']['playlistId']; ?>"><h4 class="text-ellipsis"><?php echo $video['snippet']['title'];?></h4></a>
						</div>
					</section>
				</div>
				<?php endforeach; ?>
			</div>
```
