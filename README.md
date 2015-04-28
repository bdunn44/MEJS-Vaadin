MEJS-Vaadin
===========

This Vaadin add-on provides a MediaElement.js media player component with hooks into client-side events and methods that allow you to play music/videos, control the player from the server side, and listen to player events such as Paused, Seeked, PlaybackEnded, etc.

MediaElement.js is a fully-featured HTML5 audo & video player with Flash and Silverlight fallback for older browsers. It supports a wide array of audio formats. See the MediaElement.js website for more details.

Vaadin Directory: http://vaadin.com/addon/mediaelementjs-player

Code Example
=============
```java
import com.kbdunn.vaadin.addons.mediaelement.MediaComponent;

// Audio player with PlaybackEndedListener
MediaElementPlayer audioPlayer = new MediaElementPlayer();
layout.addComponent(audioPlayer);
audioPlayer.setSource(new FileResource(new File("/path/to/song.mp3")));
audioPlayer.addPlaybackEndedListener(new PlaybackEndedListener() {

        @Override
        public void playbackEnded(MediaElementPlayer component) {
                component.setSource(new FileResource(new File("/path/to/next/song.m4a")));
                component.play();
        }
});
audioPlayer.play();

// Video player
MediaElementPlayer videoPlayer = new MediaElementPlayer(MediaElementPlayer.Type.VIDEO);
layout.addComponent(videoPlayer);
videoPlayer.setSource(new FileResource(new File("/path/to/video.mp4")));

// YouTube player
MediaElementPlayer videoPlayer = new MediaElementPlayer(MediaComponent.Type.VIDEO);
layout.addComponent(videoPlayer);
videoPlayer.setSource(new ExternalResource("https://youtu.be/kh29_SERH0Y"));
```
