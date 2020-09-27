<html>
<head><title>Handle Generator</title></head>

<body>
<h1>Product Registration</h1>

<label>输入产品条码（如果不是条形码，请在最后一位后补充一个随机数字）</label>
<br>
<input id="handle" type="number"></input>
<br>

<label>输入产品英文名称</label>
<br>
<input id="enName" type="text"></input>
<br>

<label>输入产品中文名称</label>
<br>
<input id="cnName" type="text"></input>
<br>

<label>输入网站售卖单位（盒/box，袋/bag、pack，个/EA）</label>
<br>
<input id="soldByOnline" type="text"></input>
<br>

<label>输入店内计价单位（磅/LB，个/EA）</label>
<br>
<input id="soldByInstore" type="text"></input>
<br>

<label>输入规格（）</label>
<br>
<input id="specs" type="text"></input>
<br>

<label>输入最大重量</label>
<br>
<input id="weight" type="text"></input>
<br>

<label>输入店内售价</label>
<br>
<input id="price" type="text"></input>
<br>

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
