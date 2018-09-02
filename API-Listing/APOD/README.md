# APOD
NASA "Astronomy Picture Of the Day" (<a href="https://apod.nasa.gov/apod/">APOD</a>)

# Demo
For my Demo access --- [<a href="http://geekresearchlab.net/NASA/open_api/apod/test_api_service.php">CLICK HERE</a>]

# Source Code
```php
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
# Build your own EXE & Generate a Simple Log
Using a <a href="https://github.com/elnormous/HTTPRequest">HTTP Header Library</a>, you can try the below source code of mine.<br>
Supported Compiler: C++ 11 with <a href="https://github.com/ashumeow/NASA-APIs/tree/master/API-Listing/APOD/linkers">Linker settings</a><br>
Runs in both <a href="https://github.com/ashumeow/NASA-APIs/tree/master/API-Listing/APOD/dll">Windows</a> and Linux 
```cpp
#include "<Your HTTP Header Name>"
#include <cstdio>
#include <iostream>
int main(int argc, char* argv[]) {
    try
    {
        http::Request request("<YOUR PHP URL>");
        http::Response response = request.send("GET");
        std::cout << response.body.data() << std::endl;
        freopen( "<YOUR OUTPUT LOG FILE NAME>", "a", stdout );
        std::cout << response.body.data() << std::endl;
    }
    catch (const std::exception& e)
    {
        std::cerr << "Request failed, error: " << e.what() << std::endl;
    }
}
```
Demo access available --- <a href="https://github.com/ashumeow/NASA-APIs/tree/master/API-Listing/APOD/demo">Click Me!</a>
