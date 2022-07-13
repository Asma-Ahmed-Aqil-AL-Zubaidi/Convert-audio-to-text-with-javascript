# Convert-audio-to-text-with-javascript
Convert audio to text with javascript .
1-The first step is to create 
<img width="416" alt="image" src="https://user-images.githubusercontent.com/108140215/178854602-904b8f4a-dc38-4fca-9ed2-22998229ad51.png">






2-the html page
This is the HTML code
![Uploading <!DOCTYPE html>
<html lang="em">
  <head>
<title>
    converts audio to text
</title>
<meta charset="UTF-8/">

<style>
  body{
  background-color:aquamarine;

  }
.output{
  display :blank;
  width:88%;
  height:400%;
  margin:55px auto;

}
</style>
</head>

<body>
<hi> speak </hi>
<p> Convert text to speech
</p>
<button class="btn-start"> record audio</button>
<button class="btn-end">end of recording</button>
<textarea class="output"></textarea>

<script> src="javascript.js"</script>
</body>
</html>

‏لقطة الشاشة ١٤٤٣-١٢-١٥ في ٢.٣٢.١٧ ص.png…]()


3-The second step is writing the javascript code and using the appropriate library + connecting the javascript with the html

 This is the javascript code
 
 
class SpeechRecogitionApi{
 constructor(options) {
    const speechToText = window.speechRecogition || window.webkitSpeechRecognition;
    this.speechApi = new speechToText();
    this.output = options.output ? options.output:document.createElement("div");
    this.speechApi.continuous =true;
    this.speechApi.interimResult=false;
    this.speechApi.onresult = (event)=> {
        var resultIndes =event.resultIndes;
        var transcript =event.resultIndes[resultIndes][0].transcript;
        this.output.textcontent +=transcript;
     }
 }
int(){
    this.speechApi.start();

}
stop(){

    this.speechApi.stop();
}
}
window.onload =function() {
var speech =new SpeechRecognitionApi({
    output: document.querySelector(".output")


})

document.querySelector(".btn-start").addEventListener("click",()=> {
    speech.init();
})
document.querySelector(".btn-end").addEventListener("click",()=> {

   speech.stop();
})
}
<img width="872" alt="‏لقطة الشاشة ١٤٤٣-١٢-١٥ في ٢ ٣٣ ٥٤ ص" src="https://user-images.githubusercontent.com/108140215/178854444-66d79d25-ee67-4ef6-a197-ae5ed6642466.png">


4-This is the result
<img width="416" alt="image" src="https://user-images.githubusercontent.com/108140215/178854700-14918fb4-9968-47b4-9099-2a6eb42fe9c9.png">

<img width="416" alt="image" src="https://user-images.githubusercontent.com/108140215/178854710-92fac296-2bfd-4628-8597-5aff962da575.png">

