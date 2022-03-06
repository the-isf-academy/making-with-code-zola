---
title: [YouTube Data]
type: checkup
---
# Youtube 

This is a walkthrough to downloading your YouTube watch history. 

## Downloading Data

{{< code-action "Follow along with this video and the steps below to download your YouTube watch history." >}} 

<br>
<br>


{{< youtube "eq1SKWlidJ4" >}}

> 0. **Go to [Google Takeout](https://takeout.google.com/settings/takeout).** Make sure you are logged into the Google account you would like to download your Youtube data from. 
> 0. **Select `Deselect all`.** This will ensure you only download your Youtube data, as opposed to all of the data Google assosicates with your account.
> 0. **Scroll to the bottom and find `YouTube and YouTube Music` and check the box.** 
> 0. **Select `Multiple Formats`.** 
> 0. **For `History`, select `HTML` and choose `JSON`. Then, click `OK`.**
> 0. **Select `Next step`**
> 0. **Scroll down, select `Create export`.**
> 
> This may take awhile. It may only take a few minutes or an hour. You will recieve an email when your data is ready for download.


{{< code-action "Once your data is ready to download, you'll need to locate the correct file.." >}} 

{{< figure src="images/courses/cs9/unit01/youtube_download.gif" width="100%" >}}
> 0. **Download the first export.** You do not need to download all of the exports. 
> 0. **Open the `.zip` file.**
> 0. **Navigate to the `Takeout 6/YouTube and YouTube Music/history` folder.**
> 0. **Move the `watch_history.json` into your `desktop/cs9/unit_01` folder.**

<!-- ---

## API Key -->
