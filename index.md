<html>
<head><title>Handle Generator</title></head>

<body>
<h1>Product Registration</h1>

<label>输入产品条码（如果不是条形码，请在最后一位后补充一个随机数字）</label>
<br>
<input id="handle" type="number"></input>
<br>

<iframe height="1200" width="600" src="http://translate.google.com/translate" align="middle" border="0">



<!-- -->
<label>Result shows here:</label>
<br>
<input id="handleText" readonly></input>
<br><button onclick="gen()">转换</button>
<script>

function copyHandle(){
	var copyText = document.getElementById("handleText");

	/* Select the text field */
	copyText.focus();
	copyText.select();
	copyText.setSelectionRange(0, 99999); /*For mobile devices*/

	/* Copy the text inside the text field */
	document.execCommand("copy");
}

function gen(){
	var tag=document.getElementById("handle");
	var handle=tag.value; 
	handle=handle.substring(0,handle.length-1);
	while (handle.length < 15) {
        handle = '0' + handle;
    }
	handle='alp-o'+handle;

	var handleText=document.getElementById("handleText")
	handleText.value=handle;

	copyHandle();
}

document.onkeydown = function (e) {
  e = e || window.event;
  switch (e.which || e.keyCode) {
        case 13 : gen();
            break;
  }
}

</script>

</body>

</html>
