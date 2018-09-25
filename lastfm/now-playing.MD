# Now Playing
Viser hvad der i øjeblikket bliver scrobblet til en Last.FM konto

Kræver et [API Key](http://www.last.fm/api/account/create) & et [PHP libary](https://github.com/matto1990/PHP-Last.fm-API)

```php
<?php
require 'lastfmapi/lastfmapi.php';

$authVars['apiKey'] = 'API KEY GOES HERE';
$auth = new lastfmApiAuth('setsession', $authVars);

$apiClass = new lastfmApi();
$packageClass = $apiClass->getPackage($auth, 'user');

if ($artists = $packageClass->getRecentTracks(array('user' => 'USERNAME GOES HERE', 'limit' => 2))) {
	foreach ($artists as $artist) {
		echo '<p><a href="'.$artist['url'].'" target="_parent">'.$artist['artist']['name'].' - '.$artist['name'].' - '.$artist['album']['name'].'</a></p>';
		
		if (isset($artist['nowplaying']))
			echo '<img src="'.$artist['images']['medium'].'" alt="" />';
	}
}
else {
	echo 'Hmm der opstod en API fejl, tjek <a href="http://www.last.fm/api/errorcodes">Last.FM API</a> for flere detaljer om problemet. Fejlkode '.$packageClass->error['code'].' - </b><i>'.$packageClass->error['desc'].'</i>';
}
//print_r($artists);
?>
```
