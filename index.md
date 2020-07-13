## Welcome to GitHub Pages

Bu hesap denemedir [Aktif Github hesabım](https://github.com/sertacguler) 

https://stackoverflow.com/questions/33012936/copy-dependency-of-a-maven-project-to-specific-folder

https://medium.com/@sunitj/few-things-you-need-to-know-about-timezone-f0849c606cc9

https://stackoverflow.com/jobs/357864/junior-fullstack-engineer-m-f-d-jvm-private-scout24




https://medium.com/free-code-camp/the-react-handbook-b71c27b0a795
https://codesandbox.io/s/
https://codepen.io/

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

    
*****************************
https://medium.com/javarevisited/the-2019-react-js-developer-roadmap-9a8e290b8a56
*****************************
