# Latest Video
Henter den nyeste video

Kræver [API key](https://console.developers.google.com/apis/credentials) & channel ID. iFrame kan [customizes](https://developers.google.com/youtube/youtube_player_demo) 
```php
<?php
$video = json_decode(file_get_contents('https://www.googleapis.com/youtube/v3/search?key=API-KEY&part=id&channelId=CHANNEL-ID&order=date&maxResults=1&type=video'), true);
$video_id = $video['items'][0]['id']['videoId'];
?>
```

```html
<iframe class="embed-responsive-item" src="https://youtube.com/embed/<?php echo $video_id; ?>?showinfo=0&color=white&theme=light&fs=1">Brug en moderne browser TAK!!</iframe>
```
