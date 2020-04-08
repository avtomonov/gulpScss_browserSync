# gulpScss_browserSync
Сборка SCSS и browser sync
скачиваем в любую папку  
выбираем папку в теминале например cd c:/sync  
npm i  
browser-sync  
gulp default  

***
скрипт на сайт для динамический стилей  
<script>
  var count = 0;
  function CSSLoad(file){
    var link = document.createElement("link");
    link.setAttribute("rel", "stylesheet");
    link.setAttribute("type", "text/css");
    link.setAttribute("href", file);
    count++;
    link.setAttribute("data-quck-scss", count);
    $('body').append(link);
    setTimeout(function(){
      $('[data-quck-scss]:not([data-quck-scss="'+ count +'"])').remove();
    }, 500)
  }
  setInterval(function(){
     CSSLoad('http://192.168.0.194:3000/css/main.css');
  }, 1000)
</script>

