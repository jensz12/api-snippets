# Sub count
Henter antallet af subscribere til en kanal

Kræver API key & channel id

```php
<?php
$sub = json_decode(file_get_contents('https://www.googleapis.com/youtube/v3/channels?part=statistics&id=CHANNEL-ID&key=API-KEY'), true);
$sub_count = $sub['items'][0]['statistics']['subscriberCount'];
?>
```

```php
<?php echo number_format("$sub_count;")  ?>
```
