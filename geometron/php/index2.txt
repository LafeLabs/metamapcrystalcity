<?php
    $url = "https://raw.githubusercontent.com/LafeLabs/metamapcrystalcity/master/geometron/json/dna2.txt";
    $dnaraw = file_get_contents($url);
    $dna =json_decode($dnaraw);
    $baseurl = explode("json",$url)[0];
  
?>
<!doctype html>
<html>
<head>
<title>index</title>
<!-- 
PUBLIC DOMAIN, NO COPYRIGHTS, NO PATENTS.
-->
<script id = "bytecodeScript">
/*
<?php
foreach ($dna as $value) {
    if(explode("/",$value)[0]   == "bytecode"){
        echo file_get_contents($baseurl.$value)."\n";
    }    
}
?>
*/
</script>
<script id = "topfunctions">
<?php
foreach ($dna as $value) {
    if(explode("/",$value)[1]   == "topfunctions.txt"){
        echo file_get_contents($baseurl.$value)."\n";
    }    
}

?>   
</script>
<script id = "actions">
function doTheThing(localCommand){    
    if(localCommand >= 040 && localCommand <= 0176){
        currentHTML += String.fromCharCode(localCommand);
        currentWord += String.fromCharCode(localCommand);
    }
    if(localCommand >= 0200 && localCommand <= 0277){//shapes 
        if(!(localCommand == 0207 && editMode == false) ){
            drawGlyph(currentTable[localCommand]);    	    
        }
    }
    if(localCommand >= 01000 && localCommand <= 01777){//symbol glyphs
            drawGlyph(currentTable[localCommand]);    	    
    } 

    <?php

    foreach ($dna as $value) {
        if(explode("/",$value)[1]   == "actions03xx.txt"){
            echo file_get_contents($baseurl.$value)."\n";
        }    
    }
    echo "\n";
    foreach ($dna as $value) {
        if(explode("/",$value)[1]   == "actions0xx.txt"){
            echo file_get_contents($baseurl.$value)."\n";
        }    
    }
    echo "\n";
    ?>    
}
</script>

<?php
    foreach ($dna as $value) {
        if(explode("/",$value)[1]   == "jslibrary.txt"){
            echo file_get_contents($baseurl.$value)."\n";
        }    
    }
?>

</head>
<body>
<div id = "jsondata" style = "display:none">
<?php
    echo file_get_contents("json/currentjson.txt");
?>
</div>
<div id = "page">
<?php

    foreach ($dna as $value) {
        if(explode("/",$value)[1]   == "page.txt"){
            echo file_get_contents($baseurl.$value)."\n";
        }    
    }

?>
</div>
<script>
</script>
<script id = "init">
init();
function init(){
<?php
    foreach ($dna as $value) {
        if(explode("/",$value)[1] == "init.txt"){
            echo file_get_contents($baseurl.$value)."\n";
        }    
    }
?>
}
</script>
<script id = "redraw">
redraw();
function redraw(){
<?php
    foreach ($dna as $value) {
        if(explode("/",$value)[1] == "redraw.txt"){
            echo file_get_contents($baseurl.$value)."\n";
        }    
    }
?>
}
</script>
<script id = "pageevents">
<?php
   foreach ($dna as $value) {
        if(explode("/",$value)[1] == "pageevents.txt"){
            echo file_get_contents($baseurl.$value)."\n";
        }    
    }
?>
</script>
<?php
    echo "<style>\n";
    foreach ($dna as $value) {
        if(explode("/",$value)[1] == "style.txt"){
            echo file_get_contents($baseurl.$value)."\n";
        }    
    }?>
    echo "</style>\n";
?>
</body>
</html>