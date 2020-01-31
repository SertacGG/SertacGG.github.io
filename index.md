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



Reactjs english word input exmple
https://react-select.com/advanced#portaling


https://goalkicker.com/
