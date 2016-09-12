# Video List
Henter en liste over de seneste videoer på en Youtube kanal.

Kræver [API key](https://console.developers.google.com/apis/credentials) & channel id

```php 
<?php
$videos = json_decode(file_get_contents('https://www.googleapis.com/youtube/v3/videos?key=API-KEY&part=snippet&channelId=CHANNEL-ID&order=date&maxResults=NUMBER-OF-RESULTS'), true);
?>
```

```html
<?php foreach ($videos['items'] as $video): ?>

<div class="col-sm-6">
					<section class="thumbnail">
						<a href="https://youtu.be/<?php echo $video['id']['videoId']; ?>">
							<img class="img-responsive" src="https://i.ytimg.com/vi/<?php echo $video['id']['videoId']; ?>/maxresdefault.jpg" />
						</a>
						<div class="caption">
							<a href="https://youtu.be/<?php echo $video['id']['videoId']; ?>"><h4 class="text-ellipsis"><?php echo $video['snippet']['title'];?></h4></a>
						</div>
					</section>
				</div>
				<?php endforeach; ?>
```
