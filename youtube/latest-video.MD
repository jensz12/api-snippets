<?php
$video = json_decode(file_get_contents('https://www.googleapis.com/youtube/v3/search?key=API-KEY&part=id&channelId=CHANNEL-ID&order=date&maxResults=1'), true);
$video_id = $video['items'][0]['id']['videoId'];
?>
