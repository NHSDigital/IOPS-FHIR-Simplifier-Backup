## RESTful Interactions
<head>

<style>
#div1 {
    max-width: 500px;
    max-height: 250px;
}
</style>

<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.4.1/jquery.min.js">
</script>

<script type='text/javascript'>

function xmlToString(xmlData) { 

    var xmlString;
    //IE
    if (window.ActiveXObject){
        xmlString = xmlData.xml;
    }
    // code for Mozilla, Firefox, Opera, etc.
    else{
        xmlString = (new XMLSerializer()).serializeToString(xmlData);
    }
    return xmlString;
}   

</script>

<script>
$(document).ready(function(){
  $("#getpatno").click(function(){
     $( "#div1" ).empty();
     var format= $("#format option:selected").text();
     var newurl="https://vonk.fire.ly/Patient?family="+$("#familyname").val()+"&_format="+format;
    console.log(newurl);
    $.ajax({url: newurl, 
    type: 'GET',
    success: function(result){
       if (format == 'xml'){
           $("#div1").text(xmlToString(result));
       }
       else{
            $("#div1").html(JSON.stringify(result,undefined,2));
       }
    },
    error: function (data){
        var output = data;
        if (output === undefined){
            console.log("Error! Action could not be performed");
        }
        else{
            console.log("Validation failed");
        }
    }
    });
  });
});
</script>
</head>
<body>


<p>Format:</p> 
        <select id="format"> 
            <option value="1">json</option> 
            <option value="2">xml</option> 
        </select> <br/>

patient family name: <input id="familyname"></text>
<button id="getpatno">Get</button>
<pre>
<div id="div1"><h2></h2></div>
</pre>

</body>