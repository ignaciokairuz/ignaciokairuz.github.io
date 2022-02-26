<iframe title="Marcas & Modelos x Categoría - TABLA DINÁMICA" width="600" height="373.5" src="https://app.powerbi.com/view?r=eyJrIjoiN2ZlOTYxZTktOTVlMS00ZWNlLTgxMDItZmJkOTFjNTM5NmM2IiwidCI6Ijk4NzJkMTVhLWEzMjgtNDc0MS1hMGZjLWIzMTA4YmE1MDY2NyJ9" frameborder="0" allowFullScreen="true"></iframe>
<!DOCTYPE html>
<html><head>
<meta http-equiv="content-type" content="text/html; charset=UTF-8">
<meta charset="UTF-8">
<style type="text/css">
:root {
  font-family: sans-serif;
}
img {
  border: 0;
}
th {
  text-align: start;
  white-space: nowrap;
}
th > a {
  color: inherit;
}
table[order] > thead > tr > th {
  cursor: pointer;
}
table[order] > thead > tr > th::after {
  display: none;
  width: .8em;
  margin-inline-end: -.8em;
  text-align: end;
}
table[order="asc"] > thead > tr > th::after {
  content: "\2193"; /* DOWNWARDS ARROW (U+2193) */
}
table[order="desc"] > thead > tr > th::after {
  content: "\2191"; /* UPWARDS ARROW (U+2191) */
}
table[order][order-by="0"] > thead > tr > th:first-child > a ,
table[order][order-by="1"] > thead > tr > th:first-child + th > a ,
table[order][order-by="2"] > thead > tr > th:first-child + th + th > a {
  text-decoration: underline;
}
table[order][order-by="0"] > thead > tr > th:first-child::after ,
table[order][order-by="1"] > thead > tr > th:first-child + th::after ,
table[order][order-by="2"] > thead > tr > th:first-child + th + th::after {
  display: inline-block;
}
table.remove-hidden > tbody > tr.hidden-object {
  display: none;
}
td {
  white-space: nowrap;
}
table.ellipsis {
  width: 100%;
  table-layout: fixed;
  border-spacing: 0;
}
table.ellipsis > tbody > tr > td {
  overflow: hidden;
  text-overflow: ellipsis;
}
/* name */
/* name */
th:first-child {
  padding-inline-end: 2em;
}
/* size */
th:first-child + th {
  padding-inline-end: 1em;
}
td:first-child + td {
  text-align: end;
  padding-inline-end: 1em;
}
/* date */
td:first-child + td + td {
  padding-inline-start: 1em;
  padding-inline-end: .5em;
}
/* time */
td:first-child + td + td + td {
  padding-inline-start: .5em;
}
.symlink {
  font-style: italic;
}
.dir ,
.symlink ,
.file {
  margin-inline-start: 20px;
}
.dir::before ,
.file > img {
  margin-inline-end: 4px;
  margin-inline-start: -20px;
  max-width: 16px;
  max-height: 16px;
  vertical-align: middle;
}
.dir::before {
  content: url(resource://content-accessible/html/folder.png);
}
</style>
<link rel="stylesheet" media="screen, projection" type="text/css" href="chrome://global/skin/dirListing/dirListing.css">
<script type="application/javascript">
'use strict';
var gTable, gOrderBy, gTBody, gRows, gUI_showHidden;
document.addEventListener("DOMContentLoaded", function() {
  gTable = document.getElementsByTagName("table")[0];
  gTBody = gTable.tBodies[0];
  if (gTBody.rows.length < 2)
    return;
  gUI_showHidden = document.getElementById("UI_showHidden");
  var headCells = gTable.tHead.rows[0].cells,
      hiddenObjects = false;
  function rowAction(i) {
    return function(event) {
      event.preventDefault();
      orderBy(i);
    }
  }
  for (var i = headCells.length - 1; i >= 0; i--) {
    var anchor = document.createElement("a");
    anchor.href = "";
    anchor.appendChild(headCells[i].firstChild);
    headCells[i].appendChild(anchor);
    headCells[i].addEventListener("click", rowAction(i), true);
  }
  if (gUI_showHidden) {
    gRows = Array.from(gTBody.rows);
    hiddenObjects = gRows.some(row => row.className == "hidden-object");
  }
  gTable.setAttribute("order", "");
  if (hiddenObjects) {
    gUI_showHidden.style.display = "block";
    updateHidden();
  }
}, "false");
function compareRows(rowA, rowB) {
  var a = rowA.cells[gOrderBy].getAttribute("sortable-data") || "";
  var b = rowB.cells[gOrderBy].getAttribute("sortable-data") || "";
  var intA = +a;
  var intB = +b;
  if (a == intA && b == intB) {
    a = intA;
    b = intB;
  } else {
    a = a.toLowerCase();
    b = b.toLowerCase();
  }
  if (a < b)
    return -1;
  if (a > b)
    return 1;
  return 0;
}
function orderBy(column) {
  if (!gRows)
    gRows = Array.from(gTBody.rows);
  var order;
  if (gOrderBy == column) {
    order = gTable.getAttribute("order") == "asc" ? "desc" : "asc";
  } else {
    order = "asc";
    gOrderBy = column;
    gTable.setAttribute("order-by", column);
    gRows.sort(compareRows);
  }
  gTable.removeChild(gTBody);
  gTable.setAttribute("order", order);
  if (order == "asc")
    for (var i = 0; i < gRows.length; i++)
      gTBody.appendChild(gRows[i]);
  else
    for (var i = gRows.length - 1; i >= 0; i--)
      gTBody.appendChild(gRows[i]);
  gTable.appendChild(gTBody);
}
function updateHidden() {
  gTable.className = gUI_showHidden.getElementsByTagName("input")[0].checked ?
                     "" :
                     "remove-hidden";
}
</script>
<link rel="icon" type="image/png" href="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABAAAAAQCAYAAAAf8%2F9hAAAAGXRFWHRTb2Z0d2FyZQBBZG9iZSBJbWFnZVJlYWR5ccllPAAAAjFJREFUeNqsU8uOElEQPffR3XQ3ONASdBJCSBxHos5%2B3Bg3rvkCv8PElS78gPkO%2FATjQoUdO2ftrJiRh6aneTb9sOpC4weMN6lcuFV16pxDIfI8x12OYIDhcPiu2Wx%2B%2FHF5CW1Z6Jyegt%2FTNEWSJIjjGFEUIQxDrFYrWFSzXC4%2FdLvd95pRKpXKy%2BpRFZ7nwaWo1%2BsGnQG2260BKJfLKJVKGI1GEEJw7ateryd0v993W63WEwjgxfn5obGYzgCbzcaEbdsIggDj8Riu6z6iUk9SYZMSx8W0LMsM%2FSKK75xnJlIq80anQXdbEp0OhcPJ0eiaJnGRMEyyPDsAKKUM9clkYoDo3SZJzzSdp0VSKYmfV1co%2Bz580kw5KDIM8RbRfEnUf1HzxtQyMAGcaGruTKczMzEIaqhKifV6jd%2BzGQQB5llunF%2FM52BizC2K5sYPYvZcu653tjOM9O93wnYc08gmkgg4VAxixfqFUJT36AYBZGd6PJkFCZnnlBxMp38gqIgLpZB0y4Nph18lyWh5FFbrOSxbl3V4G%2BVB7T4ajYYxTyuLtO%2BCvWGgJE1Mc7JNsJEhvgw%2FQV4fo%2F24nbEsX2u1d5sVyn8sJO0ZAQiIYnFh%2BxrfLz%2Fj29cBS%2FO14zg3i8XigW3ZkErDtmKoeM%2BAJGRMnXeEPGKf0nCD1ydvkDzU9Jbc6OpR7WIw6L8lQ%2B4pQ1%2FlPF0RGM9Ns91Wmptk0GfB4EJkt77vXYj%2F8m%2B8y%2FkrwABHbz2H9V68DQAAAABJRU5ErkJggg%3D%3D">
<title>Index of file:///home/nacho/Desktop/</title>
<!-- base href="file:///home/nacho/Desktop/" -->
</head>
<body dir="ltr">
<h1>Index of file:///home/nacho/Desktop/</h1>
<p id="UI_goUp"><a class="up" href="file:///home/nacho/">Up to higher level directory</a></p>
<p id="UI_showHidden" style="display: block;"><label><input type="checkbox" checked="checked" onchange="updateHidden()">Show hidden objects</label></p>
<table order="" class="">
 <thead>
  <tr>
   <th><a href="">Name</a></th>
   <th><a href="">Size</a></th>
   <th colspan="2"><a href="">Last Modified</a></th>
  </tr>
 </thead>
 <tbody>
<tr>
 <td sortable-data="2(Thorndike Health, Home &amp; Learning) Chip Heath - Switch_ How to Change Things When Change Is Hard-Thorndike Press (2011).epub"><table class="ellipsis"><tbody><tr><td><a class="file" href="file:///home/nacho/Desktop/(Thorndike%20Health,%20Home%20&amp;%20Learning)%20Chip%20Heath%20-%20Switch_%20How%20to%20Change%20Things%20When%20Change%20Is%20Hard-Thorndike%20Press%20(2011).epub"><img src="Index%20of%20file%20_home_nacho_Desktop__files/a_010" alt="File:">(Thorndike
 Health, Home &amp; Learning) Chip Heath - Switch_ How to Change Things 
When Change Is Hard-Thorndike Press (2011).epub</a></td></tr></tbody></table></td>
 <td sortable-data="2653667">2592 KB</td>
 <td sortable-data="1629859203000000">8/24/21</td>
 <td>August 24, 2021</td>
</tr><tr class="hidden-object">
 <td sortable-data="2.Rhistory"><table class="ellipsis"><tbody><tr><td><a class="file" href="file:///home/nacho/Desktop/.Rhistory"><img src="Index%20of%20file%20_home_nacho_Desktop__files/a_012" alt="File:">.Rhistory</a></td></tr></tbody></table></td>
 <td sortable-data="0"></td>
 <td sortable-data="1606160440000000">11/23/20</td>
 <td>November 23, 2020</td>
</tr><tr class="hidden-object">
 <td sortable-data="2.~lock.Essay_Writing_Guide.odt#"><table class="ellipsis"><tbody><tr><td><a class="file" href="file:///home/nacho/Desktop/.~lock.Essay_Writing_Guide.odt%23"><img src="Index%20of%20file%20_home_nacho_Desktop__files/a_011" alt="File:">.~lock.Essay_Writing_Guide.odt#</a></td></tr></tbody></table></td>
 <td sortable-data="68">1 KB</td>
 <td sortable-data="1645881115000000">2/26/22</td>
 <td>February 26, 2022</td>
</tr><tr>
 <td sortable-data="21610753680200.jpeg"><table class="ellipsis"><tbody><tr><td><a class="file" href="file:///home/nacho/Desktop/1610753680200.jpeg"><img src="Index%20of%20file%20_home_nacho_Desktop__files/a_009" alt="File:">1610753680200.jpeg</a></td></tr></tbody></table></td>
 <td sortable-data="39389">39 KB</td>
 <td sortable-data="1619645079000000">4/28/21</td>
 <td>April 28, 2021</td>
</tr><tr>
 <td sortable-data="2ABOUTM.txt"><table class="ellipsis"><tbody><tr><td><a class="file" href="file:///home/nacho/Desktop/ABOUTM.txt"><img src="Index%20of%20file%20_home_nacho_Desktop__files/a_008" alt="File:">ABOUTM.txt</a></td></tr></tbody></table></td>
 <td sortable-data="295">1 KB</td>
 <td sortable-data="1617935038000000">4/8/21</td>
 <td>April 8, 2021</td>
</tr><tr>
 <td sortable-data="2Al Sweigart - Automate the Boring Stuff with Python_ Practical Programming for Total Beginners-No Starch Press (2020).epub"><table class="ellipsis"><tbody><tr><td><a class="file" href="file:///home/nacho/Desktop/Al%20Sweigart%20-%20Automate%20the%20Boring%20Stuff%20with%20Python_%20Practical%20Programming%20for%20Total%20Beginners-No%20Starch%20Press%20(2020).epub"><img src="Index%20of%20file%20_home_nacho_Desktop__files/a_010" alt="File:">Al Sweigart - Automate the Boring Stuff with Python_ Practical Programming for Total Beginners-No Starch Press (2020).epub</a></td></tr></tbody></table></td>
 <td sortable-data="5003552">4887 KB</td>
 <td sortable-data="1639697506000000">12/16/21</td>
 <td>December 16, 2021</td>
</tr><tr>
 <td sortable-data="1BK--DEFINIT"><table class="ellipsis"><tbody><tr><td><a class="dir" href="file:///home/nacho/Desktop/BK--DEFINIT/">BK--DEFINIT</a></td></tr></tbody></table></td>
 <td></td>
 <td sortable-data="1611390740000000">1/23/21</td>
 <td>January 23, 2021</td>
</tr><tr>
 <td sortable-data="2Bachrach Estanislao. - En Cambio. Aprendé a modificar tu cerebro para cambiar tu vida y sentirte mejor.pdf"><table class="ellipsis"><tbody><tr><td><a class="file" href="file:///home/nacho/Desktop/Bachrach%20Estanislao.%20-%20En%20Cambio.%20Aprend%C3%A9%20a%20modificar%20tu%20cerebro%20para%20cambiar%20tu%20vida%20y%20sentirte%20mejor.pdf"><img src="Index%20of%20file%20_home_nacho_Desktop__files/a_002" alt="File:">Bachrach Estanislao. - En Cambio. Aprendé a modificar tu cerebro para cambiar tu vida y sentirte mejor.pdf</a></td></tr></tbody></table></td>
 <td sortable-data="5777858">5643 KB</td>
 <td sortable-data="1614996308000000">3/5/21</td>
 <td>March 5, 2021</td>
</tr><tr>
 <td sortable-data="2Business Ideas - Important.txt"><table class="ellipsis"><tbody><tr><td><a class="file" href="file:///home/nacho/Desktop/Business%20Ideas%20-%20Important.txt"><img src="Index%20of%20file%20_home_nacho_Desktop__files/a_008" alt="File:">Business Ideas - Important.txt</a></td></tr></tbody></table></td>
 <td sortable-data="444">1 KB</td>
 <td sortable-data="1621364583000000">5/18/21</td>
 <td>May 18, 2021</td>
</tr><tr>
 <td sortable-data="1CHECK THIS EVERY DAY"><table class="ellipsis"><tbody><tr><td><a class="dir" href="file:///home/nacho/Desktop/CHECK%20THIS%20EVERY%20DAY/">CHECK THIS EVERY DAY</a></td></tr></tbody></table></td>
 <td></td>
 <td sortable-data="1622862890000000">6/5/21</td>
 <td>June 5, 2021</td>
</tr><tr>
 <td sortable-data="2CONSTANCY.txt"><table class="ellipsis"><tbody><tr><td><a class="file" href="file:///home/nacho/Desktop/CONSTANCY.txt"><img src="Index%20of%20file%20_home_nacho_Desktop__files/a_008" alt="File:">CONSTANCY.txt</a></td></tr></tbody></table></td>
 <td sortable-data="240">1 KB</td>
 <td sortable-data="1622257384000000">5/29/21</td>
 <td>May 29, 2021</td>
</tr><tr>
 <td sortable-data="1Coursera"><table class="ellipsis"><tbody><tr><td><a class="dir" href="file:///home/nacho/Desktop/Coursera/">Coursera</a></td></tr></tbody></table></td>
 <td></td>
 <td sortable-data="1624400512000000">6/22/21</td>
 <td>June 22, 2021</td>
</tr><tr>
 <td sortable-data="1DEVELOPMENT APPS"><table class="ellipsis"><tbody><tr><td><a class="dir" href="file:///home/nacho/Desktop/DEVELOPMENT%20APPS/">DEVELOPMENT APPS</a></td></tr></tbody></table></td>
 <td></td>
 <td sortable-data="1612622389000000">2/6/21</td>
 <td>February 6, 2021</td>
</tr><tr>
 <td sortable-data="2Dreams.txt"><table class="ellipsis"><tbody><tr><td><a class="file" href="file:///home/nacho/Desktop/Dreams.txt"><img src="Index%20of%20file%20_home_nacho_Desktop__files/a_008" alt="File:">Dreams.txt</a></td></tr></tbody></table></td>
 <td sortable-data="720">1 KB</td>
 <td sortable-data="1616775631000000">3/26/21</td>
 <td>March 26, 2021</td>
</tr><tr>
 <td sortable-data="2Essay_Writing_Guide.odt"><table class="ellipsis"><tbody><tr><td><a class="file" href="file:///home/nacho/Desktop/Essay_Writing_Guide.odt"><img src="Index%20of%20file%20_home_nacho_Desktop__files/a_004" alt="File:">Essay_Writing_Guide.odt</a></td></tr></tbody></table></td>
 <td sortable-data="38095">38 KB</td>
 <td sortable-data="1620579135000000">5/9/21</td>
 <td>May 9, 2021</td>
</tr><tr>
 <td sortable-data="1FOLDER"><table class="ellipsis"><tbody><tr><td><a class="dir" href="file:///home/nacho/Desktop/FOLDER/">FOLDER</a></td></tr></tbody></table></td>
 <td></td>
 <td sortable-data="1628356461000000">8/7/21</td>
 <td>August 7, 2021</td>
</tr><tr>
 <td sortable-data="2Home is wherever i'm with you"><table class="ellipsis"><tbody><tr><td><a class="file" href="file:///home/nacho/Desktop/Home%20is%20wherever%20i'm%20with%20you"><img src="Index%20of%20file%20_home_nacho_Desktop__files/a_007" alt="File:">Home is wherever i'm with you</a></td></tr></tbody></table></td>
 <td sortable-data="91059">89 KB</td>
 <td sortable-data="1616207978000000">3/19/21</td>
 <td>March 19, 2021</td>
</tr><tr>
 <td sortable-data="2How I Built a Web Scraper with Beautiful Soup and Used it to Land My First&nbsp;Job.html"><table class="ellipsis"><tbody><tr><td><a class="file" href="file:///home/nacho/Desktop/How%20I%20Built%20a%20Web%20Scraper%20with%20Beautiful%20Soup%20and%20Used%20it%20to%20Land%20My%20First%C2%A0Job.html"><img src="Index%20of%20file%20_home_nacho_Desktop__files/a_003" alt="File:">How I Built a Web Scraper with Beautiful Soup and Used it to Land My First&nbsp;Job.html</a></td></tr></tbody></table></td>
 <td sortable-data="64616">64 KB</td>
 <td sortable-data="1622653533000000">6/2/21</td>
 <td>June 2, 2021</td>
</tr><tr>
 <td sortable-data="2IMPROVEMENTS.txt"><table class="ellipsis"><tbody><tr><td><a class="file" href="file:///home/nacho/Desktop/IMPROVEMENTS.txt"><img src="Index%20of%20file%20_home_nacho_Desktop__files/a_008" alt="File:">IMPROVEMENTS.txt</a></td></tr></tbody></table></td>
 <td sortable-data="4906">5 KB</td>
 <td sortable-data="1623022097000000">6/6/21</td>
 <td>June 6, 2021</td>
</tr><tr>
 <td sortable-data="2Iwil.jpeg"><table class="ellipsis"><tbody><tr><td><a class="file" href="file:///home/nacho/Desktop/Iwil.jpeg"><img src="Index%20of%20file%20_home_nacho_Desktop__files/a_009" alt="File:">Iwil.jpeg</a></td></tr></tbody></table></td>
 <td sortable-data="9423">10 KB</td>
 <td sortable-data="1619351745000000">4/25/21</td>
 <td>April 25, 2021</td>
</tr><tr>
 <td sortable-data="2Job Board | Adecco.html"><table class="ellipsis"><tbody><tr><td><a class="file" href="file:///home/nacho/Desktop/Job%20Board%20|%20Adecco.html"><img src="Index%20of%20file%20_home_nacho_Desktop__files/a_003" alt="File:">Job Board | Adecco.html</a></td></tr></tbody></table></td>
 <td sortable-data="92688">91 KB</td>
 <td sortable-data="1611746617000000">1/27/21</td>
 <td>January 27, 2021</td>
</tr><tr>
 <td sortable-data="1Linked in"><table class="ellipsis"><tbody><tr><td><a class="dir" href="file:///home/nacho/Desktop/Linked%20in/">Linked in</a></td></tr></tbody></table></td>
 <td></td>
 <td sortable-data="1620946351000000">5/13/21</td>
 <td>May 13, 2021</td>
</tr><tr>
 <td sortable-data="2Notes.txt"><table class="ellipsis"><tbody><tr><td><a class="file" href="file:///home/nacho/Desktop/Notes.txt"><img src="Index%20of%20file%20_home_nacho_Desktop__files/a_008" alt="File:">Notes.txt</a></td></tr></tbody></table></td>
 <td sortable-data="8611">9 KB</td>
 <td sortable-data="1627573519000000">7/29/21</td>
 <td>July 29, 2021</td>
</tr><tr>
 <td sortable-data="2ORDER.txt"><table class="ellipsis"><tbody><tr><td><a class="file" href="file:///home/nacho/Desktop/ORDER.txt"><img src="Index%20of%20file%20_home_nacho_Desktop__files/a_008" alt="File:">ORDER.txt</a></td></tr></tbody></table></td>
 <td sortable-data="426">1 KB</td>
 <td sortable-data="1623539196000000">6/12/21</td>
 <td>June 12, 2021</td>
</tr><tr>
 <td sortable-data="2Plain Text.txt"><table class="ellipsis"><tbody><tr><td><a class="file" href="file:///home/nacho/Desktop/Plain%20Text.txt"><img src="Index%20of%20file%20_home_nacho_Desktop__files/a_008" alt="File:">Plain Text.txt</a></td></tr></tbody></table></td>
 <td sortable-data="2160">3 KB</td>
 <td sortable-data="1618242754000000">4/12/21</td>
 <td>April 12, 2021</td>
</tr><tr>
 <td sortable-data="1Pygame - The Great Farmer (copy 1)"><table class="ellipsis"><tbody><tr><td><a class="dir" href="file:///home/nacho/Desktop/Pygame%20-%20The%20Great%20Farmer%20(copy%201)/">Pygame - The Great Farmer (copy 1)</a></td></tr></tbody></table></td>
 <td></td>
 <td sortable-data="1613402133000000">2/15/21</td>
 <td>February 15, 2021</td>
</tr><tr>
 <td sortable-data="2Questions.txt"><table class="ellipsis"><tbody><tr><td><a class="file" href="file:///home/nacho/Desktop/Questions.txt"><img src="Index%20of%20file%20_home_nacho_Desktop__files/a_008" alt="File:">Questions.txt</a></td></tr></tbody></table></td>
 <td sortable-data="941">1 KB</td>
 <td sortable-data="1622066303000000">5/26/21</td>
 <td>May 26, 2021</td>
</tr><tr>
 <td sortable-data="1RESUMES CV"><table class="ellipsis"><tbody><tr><td><a class="dir" href="file:///home/nacho/Desktop/RESUMES%20CV/">RESUMES CV</a></td></tr></tbody></table></td>
 <td></td>
 <td sortable-data="1620934048000000">5/13/21</td>
 <td>May 13, 2021</td>
</tr><tr>
 <td sortable-data="2Resume (copy 1).pdf"><table class="ellipsis"><tbody><tr><td><a class="file" href="file:///home/nacho/Desktop/Resume%20(copy%201).pdf"><img src="Index%20of%20file%20_home_nacho_Desktop__files/a_002" alt="File:">Resume (copy 1).pdf</a></td></tr></tbody></table></td>
 <td sortable-data="156600">153 KB</td>
 <td sortable-data="1620933124000000">5/13/21</td>
 <td>May 13, 2021</td>
</tr><tr>
 <td sortable-data="2Study Anything Faster.odt"><table class="ellipsis"><tbody><tr><td><a class="file" href="file:///home/nacho/Desktop/Study%20Anything%20Faster.odt"><img src="Index%20of%20file%20_home_nacho_Desktop__files/a_004" alt="File:">Study Anything Faster.odt</a></td></tr></tbody></table></td>
 <td sortable-data="366758">359 KB</td>
 <td sortable-data="1621550868000000">5/20/21</td>
 <td>May 20, 2021</td>
</tr><tr>
 <td sortable-data="1T P ' S"><table class="ellipsis"><tbody><tr><td><a class="dir" href="file:///home/nacho/Desktop/T%20P%20'%20S/">T P ' S</a></td></tr></tbody></table></td>
 <td></td>
 <td sortable-data="1620421566000000">5/7/21</td>
 <td>May 7, 2021</td>
</tr><tr>
 <td sortable-data="2TODAY'S RESULTS.txt"><table class="ellipsis"><tbody><tr><td><a class="file" href="file:///home/nacho/Desktop/TODAY'S%20RESULTS.txt"><img src="Index%20of%20file%20_home_nacho_Desktop__files/a_008" alt="File:">TODAY'S RESULTS.txt</a></td></tr></tbody></table></td>
 <td sortable-data="37">1 KB</td>
 <td sortable-data="1622670207000000">6/2/21</td>
 <td>June 2, 2021</td>
</tr><tr>
 <td sortable-data="1TRIÑANES"><table class="ellipsis"><tbody><tr><td><a class="dir" href="file:///home/nacho/Desktop/TRI%C3%91ANES/">TRIÑANES</a></td></tr></tbody></table></td>
 <td></td>
 <td sortable-data="1627100183000000">7/24/21</td>
 <td>July 24, 2021</td>
</tr><tr>
 <td sortable-data="2The Best Abs Workout The Only 6 Exercises You Need to Get a Six-Pack | GQ.html"><table class="ellipsis"><tbody><tr><td><a class="file" href="file:///home/nacho/Desktop/The%20Best%20Abs%20Workout%20The%20Only%206%20Exercises%20You%20Need%20to%20Get%20a%20Six-Pack%20|%20GQ.html"><img src="Index%20of%20file%20_home_nacho_Desktop__files/a_003" alt="File:">The Best Abs Workout The Only 6 Exercises You Need to Get a Six-Pack | GQ.html</a></td></tr></tbody></table></td>
 <td sortable-data="383207">375 KB</td>
 <td sortable-data="1618413717000000">4/14/21</td>
 <td>April 14, 2021</td>
</tr><tr>
 <td sortable-data="2The Tech Twins Resume Template.pdf"><table class="ellipsis"><tbody><tr><td><a class="file" href="file:///home/nacho/Desktop/The%20Tech%20Twins%20Resume%20Template.pdf"><img src="Index%20of%20file%20_home_nacho_Desktop__files/a_002" alt="File:">The Tech Twins Resume Template.pdf</a></td></tr></tbody></table></td>
 <td sortable-data="71113">70 KB</td>
 <td sortable-data="1612196341000000">2/1/21</td>
 <td>February 1, 2021</td>
</tr><tr>
 <td sortable-data="2The-Pitch-Canvas©_V7_9.pdf"><table class="ellipsis"><tbody><tr><td><a class="file" href="file:///home/nacho/Desktop/The-Pitch-Canvas%C2%A9_V7_9.pdf"><img src="Index%20of%20file%20_home_nacho_Desktop__files/a_002" alt="File:">The-Pitch-Canvas©_V7_9.pdf</a></td></tr></tbody></table></td>
 <td sortable-data="209150">205 KB</td>
 <td sortable-data="1611578728000000">1/25/21</td>
 <td>January 25, 2021</td>
</tr><tr>
 <td sortable-data="2Walter Isaacson - Steve Jobs -Simon &amp; Schuster (2011).epub"><table class="ellipsis"><tbody><tr><td><a class="file" href="file:///home/nacho/Desktop/Walter%20Isaacson%20-%20Steve%20Jobs%20-Simon%20&amp;%20Schuster%20(2011).epub"><img src="Index%20of%20file%20_home_nacho_Desktop__files/a_010" alt="File:">Walter Isaacson - Steve Jobs -Simon &amp; Schuster (2011).epub</a></td></tr></tbody></table></td>
 <td sortable-data="2394295">2339 KB</td>
 <td sortable-data="1623898427000000">6/16/21</td>
 <td>June 16, 2021</td>
</tr><tr>
 <td sortable-data="2chrome-efmjfjelnicpmdcmfikempdhlmainjcb-Default.desktop"><table class="ellipsis"><tbody><tr><td><a class="file" href="file:///home/nacho/Desktop/chrome-efmjfjelnicpmdcmfikempdhlmainjcb-Default.desktop"><img src="Index%20of%20file%20_home_nacho_Desktop__files/a_005" alt="File:">chrome-efmjfjelnicpmdcmfikempdhlmainjcb-Default.desktop</a></td></tr></tbody></table></td>
 <td sortable-data="324">1 KB</td>
 <td sortable-data="1642861613000000">1/22/22</td>
 <td>January 22, 2022</td>
</tr><tr>
 <td sortable-data="1data analysis log"><table class="ellipsis"><tbody><tr><td><a class="dir" href="file:///home/nacho/Desktop/data%20analysis%20log/">data analysis log</a></td></tr></tbody></table></td>
 <td></td>
 <td sortable-data="1628435599000000">8/8/21</td>
 <td>August 8, 2021</td>
</tr><tr>
 <td sortable-data="2distractions.txt"><table class="ellipsis"><tbody><tr><td><a class="file" href="file:///home/nacho/Desktop/distractions.txt"><img src="Index%20of%20file%20_home_nacho_Desktop__files/a_008" alt="File:">distractions.txt</a></td></tr></tbody></table></td>
 <td sortable-data="123">1 KB</td>
 <td sortable-data="1622143929000000">5/27/21</td>
 <td>May 27, 2021</td>
</tr><tr>
 <td sortable-data="2english.txt"><table class="ellipsis"><tbody><tr><td><a class="file" href="file:///home/nacho/Desktop/english.txt"><img src="Index%20of%20file%20_home_nacho_Desktop__files/a_008" alt="File:">english.txt</a></td></tr></tbody></table></td>
 <td sortable-data="705">1 KB</td>
 <td sortable-data="1645326624000000">2/20/22</td>
 <td>February 20, 2022</td>
</tr><tr>
 <td sortable-data="1esto es otra cosa"><table class="ellipsis"><tbody><tr><td><a class="dir" href="file:///home/nacho/Desktop/esto%20es%20otra%20cosa/">esto es otra cosa</a></td></tr></tbody></table></td>
 <td></td>
 <td sortable-data="1627047132000000">7/23/21</td>
 <td>July 23, 2021</td>
</tr><tr>
 <td sortable-data="1ignaciokairuz"><table class="ellipsis"><tbody><tr><td><a class="dir" href="file:///home/nacho/Desktop/ignaciokairuz/">ignaciokairuz</a></td></tr></tbody></table></td>
 <td></td>
 <td sortable-data="1611923676000000">1/29/21</td>
 <td>January 29, 2021</td>
</tr><tr>
 <td sortable-data="1images"><table class="ellipsis"><tbody><tr><td><a class="dir" href="file:///home/nacho/Desktop/images/">images</a></td></tr></tbody></table></td>
 <td></td>
 <td sortable-data="1620410689000000">5/7/21</td>
 <td>May 7, 2021</td>
</tr><tr>
 <td sortable-data="2images.jpeg"><table class="ellipsis"><tbody><tr><td><a class="file" href="file:///home/nacho/Desktop/images.jpeg"><img src="Index%20of%20file%20_home_nacho_Desktop__files/a_009" alt="File:">images.jpeg</a></td></tr></tbody></table></td>
 <td sortable-data="8403">9 KB</td>
 <td sortable-data="1619351724000000">4/25/21</td>
 <td>April 25, 2021</td>
</tr><tr>
 <td sortable-data="2k.txt"><table class="ellipsis"><tbody><tr><td><a class="file" href="file:///home/nacho/Desktop/k.txt"><img src="Index%20of%20file%20_home_nacho_Desktop__files/a_008" alt="File:">k.txt</a></td></tr></tbody></table></td>
 <td sortable-data="0"></td>
 <td sortable-data="1636077362000000">11/4/21</td>
 <td>November 4, 2021</td>
</tr><tr>
 <td sortable-data="2libre-search.sh"><table class="ellipsis"><tbody><tr><td><a class="file" href="file:///home/nacho/Desktop/libre-search.sh"><img src="Index%20of%20file%20_home_nacho_Desktop__files/a_006" alt="File:">libre-search.sh</a></td></tr></tbody></table></td>
 <td sortable-data="247">1 KB</td>
 <td sortable-data="1620585252000000">5/9/21</td>
 <td>May 9, 2021</td>
</tr><tr>
 <td sortable-data="1links"><table class="ellipsis"><tbody><tr><td><a class="dir" href="file:///home/nacho/Desktop/links/">links</a></td></tr></tbody></table></td>
 <td></td>
 <td sortable-data="1621834094000000">5/24/21</td>
 <td>May 24, 2021</td>
</tr><tr>
 <td sortable-data="2pic01.jpg"><table class="ellipsis"><tbody><tr><td><a class="file" href="file:///home/nacho/Desktop/pic01.jpg"><img src="Index%20of%20file%20_home_nacho_Desktop__files/a_013" alt="File:">pic01.jpg</a></td></tr></tbody></table></td>
 <td sortable-data="12821">13 KB</td>
 <td sortable-data="1623190513000000">6/8/21</td>
 <td>June 8, 2021</td>
</tr><tr>
 <td sortable-data="2project that I explained on my blog post about scraping.py"><table class="ellipsis"><tbody><tr><td><a class="file" href="file:///home/nacho/Desktop/project%20that%20I%20explained%20on%20my%20blog%20post%20about%20scraping.py"><img src="Index%20of%20file%20_home_nacho_Desktop__files/a" alt="File:">project that I explained on my blog post about scraping.py</a></td></tr></tbody></table></td>
 <td sortable-data="2493">3 KB</td>
 <td sortable-data="1624368466000000">6/22/21</td>
 <td>June 22, 2021</td>
</tr><tr>
 <td sortable-data="1scalpel_recovered_files"><table class="ellipsis"><tbody><tr><td><a class="dir" href="file:///home/nacho/Desktop/scalpel_recovered_files/">scalpel_recovered_files</a></td></tr></tbody></table></td>
 <td></td>
 <td sortable-data="1620788518000000">5/12/21</td>
 <td>May 12, 2021</td>
</tr><tr>
 <td sortable-data="1test"><table class="ellipsis"><tbody><tr><td><a class="dir" href="file:///home/nacho/Desktop/test/">test</a></td></tr></tbody></table></td>
 <td></td>
 <td sortable-data="1621911445000000">5/24/21</td>
 <td>May 24, 2021</td>
</tr><tr>
 <td sortable-data="1urban dictionary project"><table class="ellipsis"><tbody><tr><td><a class="dir" href="file:///home/nacho/Desktop/urban%20dictionary%20project/">urban dictionary project</a></td></tr></tbody></table></td>
 <td></td>
 <td sortable-data="1632081174000000">9/19/21</td>
 <td>September 19, 2021</td>
</tr></tbody></table>
</body></html>
