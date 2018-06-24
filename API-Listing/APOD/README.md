# APOD
NASA "Astronomy Picture Of the Day" (<a href="https://apod.nasa.gov/apod/">APOD</a>)

# Demo
For Demo access --- [<a href="http://geekresearchlab.net/NASA/open_api/apod/test_api_service.php">CLICK HERE</a>]

# Code-Base

<code><?php</code>

<code>$my_api_key = "<YOUR API KEY>";</code>

<code>$send_req_link = "https://api.nasa.gov/planetary/apod?api_key=";</code>

<code>$send_req = $send_req_link.$my_api_key;</code>

<code>$catchJson = file_get_contents($send_req);</code>

<code>$decodeJson = json_decode($catchJson, true);</code>

<code>$show_date = $decodeJson["date"];</code>

<code>$show_explanation = $decodeJson["explanation"];</code>

<code>$show_hdurl = $decodeJson["hdurl"];</code>

<code>$show_mediatype = $decodeJson["media_type"];</code>

<code>$show_serviceversion = $decodeJson["service_version"];</code>

<code>$show_title = $decodeJson["title"];</code>

<code>$show_url = $decodeJson["url"];</code>

<code>echo "title: ".$show_title;</code>

<code>echo '<br>';</code>

<code>echo "Explanation: ".$show_explanation;</code>

<code>echo '<br>';</code>

<code>echo "URL: ".$show_url;</code>

<code>echo '<br>';</code>

<code>echo "HD_URL: ".$show_hdurl;</code>

<code>echo '<br>';</code>

<code>echo "Media Type: ".$show_mediatype;</code>

<code>echo '<br>';</code>

<code>echo "Service Version: ".$show_serviceversion;</code>

<code>echo '<br>';</code>

<code>echo "Date: ".$show_date;</code>

<code>?></code>
