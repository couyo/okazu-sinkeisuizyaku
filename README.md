# o<html >

<head>
  <meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
  <title>okazu神経衰弱</title>
<script language="JavaScript"><!--//

	hatena=new Image();


	hatena.src="yuugiou.gif";

	pic_w=100;

	pic_h=150;

	hayasa=400;

	clear_dore=0;

	clear_moji='おめでとう！これで貴方もokazuマスターです。';

	clear_url='clear.html';

	masu_h=4;

	masu_w=5;


	pic=new Array();
	kazu=new Array();
	ikutu=0;
	atari=0;
	num=0;
	checks=0;
	mae = -1;
	c_moji = "";
	function img_load()
		{
		if(checks == 0)
			{
			for(i = 0; i < 10; i++)document.images["hidden"].src=pic[i].src;
			document.images["hidden"].src=hatena.src;
			}
		}

	function my_reset()
		{
		ikutu=0;	atari=0;	i=0;	j=0;	doko=0;
		c_moji = "";
		num=Math.floor(masu_w * masu_h / 10 / 2);
		max=10;	min=0;	ataris=new Array();
		if((masu_w * masu_h) % 20 != 0)alert('数値エラーです。\n升目の合計数が不正です。');
		else {
			while(i < num)
				{
				while(j < max)
					{
					kazu[j]=Math.floor(Math.random()*10);
					if(j == 0)j++;
					else 
						{
						a=min;
						while(a < j)
							{
							if(kazu[a] != kazu[j])a++;
							else break;
							}
						 if(a == j)j++;
						}
					if(max >= (10 * 2 * (i+1))+10){ break; }
					else if(j % 10 == 0){ min=max; max+=10; }
					}
				i++;
				}
			for(i = 0; i < masu_w * masu_h; i++)
				{
				pic[i]=new Image();
				pic[i].src=""+kazu[i]+".gif";
				document.images["pic"+i].src=hatena.src;
				}
			checks=0;
			}
		num=0;
		}

	function modosu()
		{
		atari_han(mae);
		if(i == ataris.length+1)document.images["pic"+mae].src=hatena.src;
		atari_han(tugi);
		if(i == ataris.length+1)document.images["pic"+tugi].src=hatena.src;
		return;
		}

	function atari_han(doko)
		{
		i=0;
		while(i < ataris.length+1)
			{
			if(ataris[i] != doko)i++;
			else break;
			}
		return i;
		}

	function sinkei(doko)
		{
		if(doko < 10)dore = "0" + doko + ",";
		else dore = doko + ",";
		if(checks == 1 && c_moji.indexOf(dore , 0) == -1)
			{
			checks = 2;
			atari_han(doko); 
			if(i == ataris.length+1)document.images["pic"+doko].src=pic[doko].src;
			if(ikutu == 1)
				{
				ikutu=0;
				if(pic[mae].src != pic[doko].src)
					{
					tugi=doko;
					a=0;
					clearTimeout(a);
					a=setTimeout('modosu()',hayasa);
					}
				else 
					{
					atari++;
					ataris[num]=mae;
					ataris[num+1]=doko;
					num++;
					if(mae < 10)c_moji += "0" + mae + ",";
					else c_moji += mae + ",";
					if(doko < 10)c_moji += "0" + doko + ",";
					else c_moji += doko + ",";
					}
				}
			else if(ikutu == 0)
				{
				mae=doko;
				ikutu++;
				}
			if(atari == Math.floor(masu_w * masu_h / 2))
				{
				if(clear_dore)location.href=clear_url;
				else alert(clear_moji);
				}
			}
		checks = 0;
		}

//-->
</script>

</head>

<body onLoad="my_reset();img_load();">

<div align="center">


<img src="" name="hidden" width="1" height="1" border="0">

<table cellpadding="0" border="1" cellspacing="0" align="center">

	<script language="JavaScript" type="text/javascript">
	<!--//Copyright (C) WEST MiRa http://www.west-mira.jp

		k = 0;
		for(i = 0; i < masu_h; i++)
			{
			document.write('<tr>');
			for(j = 0; j < masu_w; j++)
				{
				document.write('<td><a href="javascript:void(0);" onClick="checks++; sinkei('+k+');"><img src="'+hatena.src+'" name="pic'+k+'" border="0" width="'+pic_w+'" height="'+pic_h+'"><\/a><\/td>');
				k++;
				}
			document.write('<\/tr>');
			}

	//-->
	</script>

</table>

<form name="form1">
	<input type="button" value="START!" onClick="my_reset();">
	<input type="button" value="RESET" onClick="my_reset();">
 </form>


</div>

</body></html>kazu-sinkeisuizyaku
