<!DOCTYPE html>
<html lang="ja">
<head>
<meta charset="utf-8">
<title>宝さがしゲーム</title>
<style>
body{
display:flex;
flex-wrap:wrap;
}
.box{
width:50px;
height:50px;
background:springgreen;
cursor:pointer;
transition:0.8s;
margin:0 8px 8px 0;
text-align:center;
line-height:50px;
}
.treasure{
background:gold;
border-radius:50%;
transform:rotate(360deg);
}
.empty{
transform:scale(0.8);
}
</style>
</head>
<body>
<script>
const num=14;
const treasure=Math.floor(Math.random()*num*num);
const num1=Math.floor(treasure/num);
const num2=treasure%num;
var num3,num4;
for(let i=0;i<num*num;i++){
const div=document.createElement('div');
div.classList.add('box');
div.addEventListener('click',()=>{
if(document.count.elements[0].value>0){
if(i===treasure){
div.textContent='発見!';
div.classList.add('treasure');
document.count.elements[0].value=0;
}else{
num3=Math.floor(i/num);num4=i%num;
if(num1>num3)num3=num1-num3;else num3=num3-num1;
if(num2>num4)num4=num2-num4;else num4=num4-num2;
div.textContent=(num3+num4);
div.classList.add('empty');
var sec=document.count.elements[0].value; 
document.count.elements[0].value=parseInt(sec-1);
}}});
document.body.appendChild(div);
if((i+1)%num==0)document.body.append("</n>");
}
</script>
<form name="count">
残り<input type="text" value="3">回<br>
<input type="button" value="リセット" onclick="window.location.reload();">
</form>
ルール<br>
①クリックできるのは3回まで。<br>
②はずれには宝までの距離が書かれている。
</boby>
</html>
