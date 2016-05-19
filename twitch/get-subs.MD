# Get Subs
Henter en liste over subscribere til en Twitch kanal

Kræver API OAuth key med scope ```channel_subscriptions```

```php
<?php
$twitch_subs = json_decode(file_get_contents('https://api.twitch.tv/kraken/channels/CHANNEL-NAME/subscriptions?oauth_token=API-TOKEN&limit=100&client_id=CLIENT-ID'), true);

$total_subs = $twitch_subs['_total'] -1;
$subs = array();

foreach ($twitch_subs['subscriptions'] as $sub) {
	if ($sub['user']['name'] == 'CHANNEL-NAME')
		continue;
	
	if (isset($sub['user']['logo']))
		$avatar = $sub['user']['logo'];
	else
		$avatar = 'https://static-cdn.jtvnw.net/jtv_user_pictures/xarth/404_user_150x150.png';
	
	$subs[$sub['user']['name']] = array(
		'name' => $sub['user']['display_name'],
		'avatar' => $avatar
	);
}

ksort($subs);
?>
```
```html
	<?php foreach ($subs as $sub): ?>
				<img src="<?php echo $sub['avatar']; ?>" height="60" width="60" class="player" data-toggle="tooltip" data-placement="top" title="<?php echo $sub['name']; ?>"/>
				<?php endforeach; ?>
```
