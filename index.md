## Welcome to GitHub Pages

Bu hesap denemedir [Aktif Github hesabım](https://github.com/sertacguler) 

	
	
	 <input type="button" onclick="disable = true;" value="Disable" />
	 <input type="button" onclick="disable = false;" value="Enable" />


'''

<html>
<head>
<link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css" integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T" crossorigin="anonymous">
<script type="text/javascript">
disable = new Boolean();
disable1 = new Boolean();
disable2 = new Boolean();
disable3 = new Boolean();

 function highlight(a) {
  if(disable==false)a.className='highlight'
 }
 
 function x(a) {
  if(disable1==true)a.className='div'
  else a.className='div disabled'
 }

 function y(a) {
  if(disable2==true)a.className='highlight'
  else a.className='div disabled'
 }
 
 function z(a) {
  if(disable3==true)a.className='highlight'
  else a.className='div disabled'
 }
 
 
 
 
 
 
 
 function normal(a) {
  a.className='normal'
 }
</script>
<style type="text/css">

.div.disabled {
  opacity: 0.25; 
  cursor: not-allowed;
}

 table#tblTest {
  width: 100%;
  margin-top: 10px;
  font-family: verdana,arial,sans-serif;
  font-size:12px;
  color:#333333;
  border-width: 1px;
  border-color: #666666;
  border-collapse: collapse;
 }

 table#tblTest tr.highlight td {
  background-color: #8888ff;
 }

 table#tblTest tr.normal {
  background-color: #ffffff;
 }

 table#tblTest th {
  white-space: nowrap; 
  border-width: 1px;
  padding: 8px;
  border-style: solid;
  border-color: #666666;
  background-color: #dedede;
 }

 table#tblTest td {
  border-width: 1px;
  padding: 8px;
  border-style: solid;
  border-color: #666666;
  background-color: #ffffff;
 }
</style>
</head>
<body>
<div class="container">
  <div class="row justify-content-md-center">
    <div class="col col-lg-2">
      <table id="tblTest" class="table">
	  <thead>
		<tr>
		  <th scope="col">Şehir Seç</th>
		</tr>
	  </thead>
	  <tbody>
	   <tr onclick="disable1 = true" onMouseOver="highlight(this)" onMouseOut="normal(this)" >
        <td>İstanbul(Asya)</td>    
    </tr>
    <tr onMouseOver="highlight(this)" onMouseOut="normal(this)" >
        <td>İstanbul(Avrupa)</td>   
    </tr>
    <tr onMouseOver="highlight(this)" onMouseOut="normal(this)" > 
        <td>Ankara</td> 
    </tr>
    <tr onMouseOver="highlight(this)" onMouseOut="normal(this)" >
        <td>İzmir</td> 
    </tr>
    <tr onMouseOver="highlight(this)" onMouseOut="normal(this)" >
        <td>Bursa</td>  
    </tr>
    <tr onMouseOver="highlight(this)" onMouseOut="normal(this)" >
        <td>Antalya</td>  
    </tr>
	  </tbody>
	</table>
    </div>
    <div class="col col-lg-2">
	<div onMouseOver="x(this)" onMouseOut="x(this)">
    <table id="tblTest" class="table">
		<thead>
			<tr>
				<th scope="col">Film Seç</th>
			</tr>
		</thead>
		<tbody>
			<tr onclick="disable2 = true"  onMouseOver="x(this)" onMouseOut="normal(this)" >
				<td>Emma</td>  
			</tr>
			<tr onMouseOver="x(this)" onMouseOut="normal(this)" >
				<td>Avengers</td>   
			</tr>
			<tr onMouseOver="x(this)" onMouseOut="normal(this)" > 
				<td>Recep İvedik 6</td> 
			</tr>
			<tr onMouseOver="x(this)" onMouseOut="normal(this)" >
				<td>Prison Break</td> 
			</tr>
			<tr onMouseOver="x(this)" onMouseOut="normal(this)" >
				<td>G.O.R.A</td> 
			</tr>
			<tr onMouseOver="x(this)" onMouseOut="normal(this)" >
				<td>Adanalı</td> 
			</tr>
		 </tbody>
	</table>
   </div>
   </div>
    <div class="col col-lg-2">
	<div onMouseOver="y(this)" onMouseOut="y(this)">
		    <table id="tblTest" class="table">
	  <thead>
		<tr>
		  <th scope="col">Tarih Seç</th>
		</tr>
	  </thead>
	  <tbody>
	   <tr  onclick="disable3 = true" onMouseOver="y(this)" onMouseOut="normal(this)" >
        <td>Bugün</td>
    </tr>
    <tr onMouseOver="y(this)" onMouseOut="normal(this)" >
        <td>13 Ara Sal</td>   
    </tr>
    <tr onMouseOver="y(this)" onMouseOut="normal(this)" > 
        <td>14 Ara Çar</td> 
    </tr>
    <tr onMouseOver="y(this)" onMouseOut="normal(this)" >
        <td>15 Ara Per</td> 
    </tr>
	  </tbody>
	</table>
	</div>
    </div> 
	<div class="col col-lg-2">
	<div onMouseOver="z(this)" onMouseOut="z(this)">
		    <table id="tblTest" class="table">
	  <thead>
		<tr>
		  <th scope="col">Seans Seç</th>
		</tr>
	  </thead>
	  <tbody>
	   <tr onMouseOver="z(this)" onMouseOut="normal(this)" >
        <td>11:00</td>
    </tr>
    <tr onMouseOver="z(this)" onMouseOut="normal(this)" >
        <td>13:00</td>   
    </tr>
    <tr onMouseOver="z(this)" onMouseOut="normal(this)" > 
        <td>16:00</td> 
    </tr>
    <tr onMouseOver="z(this)" onMouseOut="normal(this)" >
        <td>19:00</td> 
    </tr>
	  </tbody>
	</table>
	</div>
	
    </div>
  </div>
</div>
</body>
</html>

'''


https://medium.com/@sunitj/few-things-you-need-to-know-about-timezone-f0849c606cc9
https://stackoverflow.com/jobs/357864/junior-fullstack-engineer-m-f-d-jvm-private-scout24



https://www.hepsiburada.com/lingbao-jiguanshi-midio-gercek-mekanik-aydinlatmali-klavye-p-HBV0000087GKT?magaza=UcuzBi%C5%9Feyler&wt_gl=cpc.6802.shop.elk.it-ssc&gclid=EAIaIQobChMIyrj-rt3p5wIVh7PtCh2C1QTCEAQYAiABEgKvkvD_BwE


https://medium.com/free-code-camp/the-react-handbook-b71c27b0a795
https://codesandbox.io/s/
https://codepen.io/

Reactjs english word input exmple
https://react-select.com/advanced#portaling


https://goalkicker.com/
https://goalkicker.com/

https://momentjs.com/timezone/docs/

http://tr.thetimenow.com/australia/sydney

https://stackoverflow.com/questions/10615828/how-to-use-timezone-offset-in-nodejs



<!DOCTYPE html> 
<html> 
  
<head> 
    <title> 
        Türkçe Karakter
    </title> 
</head> 
  
<body style="text-align:center;"> 
  
    <h1>Türkçe Karakter</h1> 
          
    <textarea type="text" id="textarea"></textarea>
	
    <input type="button" value="Click Here!" onclick="myGeeks()">
	
    <p id = "two" ></p> 
	
    <script> 
        function myGeeks() { 
            const str = document.getElementById("textarea").value; 
            let charArray = str.split(""); 

			for(let x in charArray){
				switch(charArray[x]){
					case 'Ş':
						charArray.splice(x, 1, 'S');
					  break;
					case 'ş':
						charArray.splice(x, 1, 's');
						break;
					case 'Ç':
						charArray.splice(x, 1, 'C');
						break;
					case 'ç':
						charArray.splice(x, 1, 'c');
					    break;
					case 'Ü':
						charArray.splice(x, 1, 'U');
						break;
					case 'ü':
						charArray.splice(x, 1, 'u');
						break;
					case 'Ö':
						charArray.splice(x, 1, 'O');
					    break;
					case 'ö':
						charArray.splice(x, 1, 'o');
						break;
					case 'Ğ':
						charArray.splice(x, 1, 'G');
						break;
					case 'ğ':
						charArray.splice(x, 1, 'g');
						break;
					case 'İ':
						charArray.splice(x, 1, 'I');
						break;
					case 'ı':
						charArray.splice(x, 1, 'i');
						break;
					default:
						
				}	
			}
			
			const strTwo = document.getElementById("two");
			strTwo.textContent = charArray.join("");
        } 
    </script> 
</body> 
  
</html>                     









yapacağın ilk şey Mercurial kaydedilmesini için kullanacağı kullanıcı adını ayarlamak
on a Windows system in %USERPROFILE%\Mercurial.ini
```
[ui]
username = John Doe <john@example.com>
```

2 - Varolan Mercurial proje üzerinde çalışmak 
(Working on an existing Mercurial project)
```
$ hg clone https://www.mercurial-scm.org/repo/hg mercurial-repo
```
requesting all changes
adding changesets
adding manifests
adding file changes
added 9633 changesets with 19124 changes to 1271 files
updating to branch default
1084 files updated, 0 files merged, 0 files removed, 0 files unresolved


This will create a new directory called "mercurial-repo"



3 - Setting up a new Mercurial project (Yeni Mercurial projeyi kurma)
```
cd project/
$ hg init           # creates .hg
```
You'll want to start by creating a repository in the directory containing your project:
(Projenizi içeren dizinde bir depo oluşturarak başlamak isteyeceksiniz:)

```
$ hg add            # add those 'unknown' files
$ hg commit         # commit all changes into a new changeset, edit changelog entry
```
```
hg commit:
```
save your changes in the current repository 
(Geçerli depoda değişiklikleri kaydedin)

```
hg commit -m 'My changes' :
```
save your changes in the current repository with comment for my changes.

```
hg log:
```
see all changes in your repository 
(sizin veri havuzundaki tüm değişiklikleri görmek)

```
hg pull:
```
get all changes from another repository into the current one
 (Geçerli birine başka deposundaki bütün değişiklikleri almak)

```
hg push:
```
get all changes from your repository into another one 
(Başka bir birine deposundaki bütün değişiklikleri almak)

```
hg merge:
```
join different lines of history 
(tarihin farklı çizgileri katılmak)



```
hg serve:
```
create an instant-webserver. People can see the history there and pull from it 
(bir anlık web sunucusu oluşturun. İnsanlar orada geçmişini görmek ve ondan indirebiliriz)







If you want to see a nice graph of the history, just do hg serve in your repository and then direct your browser to

    http://127.0.0.1:8000
    
    
![TortoiseHg](https://raw.githubusercontent.com/SertacGG/SertacGG.github.io/master/tortoiseHg.png)

    
