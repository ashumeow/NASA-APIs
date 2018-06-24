# APOD
NASA "Astronomy Picture Of the Day" (<a href="https://apod.nasa.gov/apod/">APOD</a>)

# Demo
For my Demo access --- [<a href="http://geekresearchlab.net/NASA/open_api/apod/test_api_service.php">CLICK HERE</a>]

# Source Code
```
<?php

$my_api_key = "<ENTER YOUR API KEY>";
$send_req_link = "https://api.nasa.gov/planetary/apod?api_key=";

$send_req = $send_req_link.$my_api_key;
$catchJson = file_get_contents($send_req);
$decodeJson = json_decode($catchJson, true);

$show_date = $decodeJson["date"];
$show_explanation = $decodeJson["explanation"];
$show_hdurl = $decodeJson["hdurl"];
$show_mediatype = $decodeJson["media_type"];
$show_serviceversion = $decodeJson["service_version"];
$show_title = $decodeJson["title"];
$show_url = $decodeJson["url"];

echo "title: ".$show_title;
echo '<br>';
echo "Explanation: ".$show_explanation;
echo '<br>';
echo "URL: ".$show_url;
echo '<br>';
echo "HD_URL: ".$show_hdurl;
echo '<br>';
echo "Media Type: ".$show_mediatype;
echo '<br>';
echo "Service Version: ".$show_serviceversion;
echo '<br>';
echo "Date: ".$show_date;

?>
```
