# gulpScss_browserSync
Сборка SCSS и browser sync

npm i  
browser-sync  
gulp default  
<script>
  var count = 0;
  function CSSLoad(file){
    var link = document.createElement("link");
    link.setAttribute("rel", "stylesheet");
    link.setAttribute("type", "text/css");
    link.setAttribute("href", file);
    link.setAttribute("data-quck-scss", count);
    $('head').append(link);
    setTimeout(function(){
      $('[data-quck-scss]:not([data-quck-scss="'+ count +'"])').remove();
    }, 100)
  }
  setInterval(function(){
     CSSLoad('http://192.168.0.194:3000/css/main.css');
  }, 1000)
</script>

