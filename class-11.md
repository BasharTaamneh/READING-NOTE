# Audio, Video, Images

## HTML Images

Images can improve the design and the appearance of a web page.


![image](https://images.ctfassets.net/hrltx12pl8hq/3MbF54EhWUhsXunc5Keueb/60774fbbff86e6bf6776f1e17a8016b4/04-nature_721703848.jpg?fit=fill&w=480&h=270)

**HTML Images Syntax**

The HTML \<img> tag is used to embed an image in a web page.

Images are not technically inserted into a web page; images are linked to web pages. The \<img> tag creates a holding space for the referenced image.

The \<img> tag is empty, it contains attributes only, and does not have a closing tag.

The \<img> tag has two required attributes:

- src - Specifies the path to the image
- alt - Specifies an alternate text for the image

*The src Attribute*

The required src attribute specifies the path (URL) to the image.

**Note:** When a web page loads; it is the browser, at that moment, that gets the image from a web server and inserts it into the page. Therefore, make sure that the image actually stays in the same spot in relation to the web page, otherwise your visitors will get a broken link icon. The broken link icon and the alt text are shown if the browser cannot find the image.

**The alt Attribute**

The required alt attribute provides an alternate text for an image, if the user for some reason cannot view it (because of slow connection, an error in the src attribute, or if the user uses a screen reader).

The value of the alt attribute should describe the image:


## HTML Audio

The HTML \<audio> element is used to play an audio file on a web page.


**Example**

    <audio controls>
    <source src="horse.ogg" type="audio/ogg">
    <source src="horse.mp3" type="audio/mpeg">
     Your browser does not support the audio element.
     </audio>

<audio controls>
  <source src="horse.ogg" type="audio/ogg">
  <source src="horse.mp3" type="audio/mpeg">
Your browser does not support the audio element.
</audio>




---------------------------


**HTML Audio - How It Works**

The controls attribute adds audio controls, like play, pause, and volume.

The \<source> element allows you to specify alternative audio files which the browser may choose from. The browser will use the first recognized format.

The text between the \<audio> and \</audio> tags will only be displayed in browsers that do not support the \<audio> element.



**HTML \<audio> Autoplay**


To start an audio file automatically, use the autoplay attribute:

Example

    <audio controls autoplay>
    <source src="horse.ogg" type="audio/ogg">
    <source src="horse.mp3" type="audio/mpeg">
    Your browser does not support the audio element.
    </audio>


- Add muted after autoplay to let your audio file start playing automatically (but muted):

Example

    <audio controls autoplay muted>
     <source src="horse.ogg" type="audio/ogg">
    <source src="horse.mp3" type="audio/mpeg">
    Your browser does not support the audio element.
    </audio>



## HTML Video

The HTML \<video> element is used to show a video on a web page.

**The HTML \<video> Element**

To show a video in HTML, use the \<video> element:

Example


<video width="320" height="240" controls>
  <source src="movie.mp4" type="video/mp4">
  <source src="movie.ogg" type="video/ogg">
Your browser does not support the video tag.
</video>


    <video width="320" height="240" controls>
    <source src="movie.mp4" type="video/mp4">
    <source src="movie.ogg" type="video/ogg">
    Your browser does not support the video tag.
    </video>




- How it Works

The controls attribute adds video controls, like play, pause, and volume.

It is a good idea to always include width and height attributes. If height and width are not set, the page might flicker while the video loads.

The \<source> element allows you to specify alternative video files which the browser may choose from. The browser will use the first recognized format.

The text between the \<video> and \</video> tags will only be displayed in browsers that do not support the \<video> element.



**HTML \<video> Autoplay**


To start a video automatically, use the autoplay attribute:

Example


    <video width="320" height="240" autoplay>
     <source src="movie.mp4" type="video/mp4">
     <source src="movie.ogg" type="video/ogg">
    Your browser does not support the video tag.
    </video>



Add muted after autoplay to let your video start playing automatically (but muted):

