# View count
Henter antallet af visninger på en kanal

Kræver [API key](https://console.developers.google.com/apis/credentials) & channel id

```php
<?php
$view_count = json_decode(file_get_contents('https://www.googleapis.com/youtube/v3/channels?part=statistics&id=CHANNEL_ID&key=API_KEY'), true);
$view_count = $view_count['items'][0]['statistics']['viewCount'];
?>
```

```php
<?php echo number_format("$view_count;") ?>
```
