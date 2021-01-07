# 2102-5
Second Day of Zoom Tools 
<!DOCTYPE html>
<html lang="en" >

<head>

  <meta charset="UTF-8">
  
<link rel="apple-touch-icon" type="image/png" href="https://cpwebassets.codepen.io/assets/favicon/apple-touch-icon-5ae1a0698dcc2402e9712f7d01ed509a57814f994c660df9f7a952f3060705ee.png" />
<meta name="apple-mobile-web-app-title" content="CodePen">

<link rel="shortcut icon" type="image/x-icon" href="https://cpwebassets.codepen.io/assets/favicon/favicon-aec34940fbc1a6e787974dcd360f2c6b63348d4b1f4e06c77743096d55480f33.ico" />

<link rel="mask-icon" type="" href="https://cpwebassets.codepen.io/assets/favicon/logo-pin-8f3771b1072e3c38bd662872f6b673a722f4b3ca2421637d5596661b4e2132cc.svg" color="#111" />


  <title>CodePen - 2101-5</title>
  
  
  
  
<style>
.student{
  background:Pink;
  border-style:groove;
  text-align:center;
  width:90%;
  margin:auto;
}
</style>

  
  
  
  

</head>

<body translate="no" >
  <div id="container">
  <div class="student" id="isaacallnutt">
    Isaac Allnutt
  </div>
    <div class="student" id="giangaspar">
    Gian Gasper
  </div>
</div>

<button id="pickStudent">
  Pick Student
</button>
<div>
  Random Student: <span id="picked">...</span>
</div>
  
  
      <script id="rendered-js" >
console.clear();

const students = [];

function makeStudent(username, first, last, gradeLevel) {
  const student = {};
  student.username = username;
  student.first = first;
  student.last = last;
  student.gradeLevel = gradeLevel;
  student.clickcount = 0;
  return student;
}

students.push(makeStudent("isaacallnutt", "Isaac", "Allnutt", 12));
students.push(makeStudent("giangasper", "Gian", "Gaspar", 11));
students.push(makeStudent("edencampbell", "Eden", "Campbell", 10));
students.push(makeStudent("fionaalhadeff", "Fiona", "Alhadef", 10));
students.push(makeStudent("emmasindel-dempsy", "Emma", "Sindel-Dempsy", 11));
students.push(makeStudent("mckenzieroberts", "Mckenzie", "Roberts", 12));
students.push(makeStudent("samsakaguchi", "Sam", "Sakaguchi", 12));
students.push(makeStudent("aldencutler", "Alden", "Cutler", 12));
students.push(makeStudent("johnsawyer", "John", "Sawyer", 12));
students.push(makeStudent("itaimalakoff", "Itai", "Malakoff", 12));









function pickStudent() {
  let randomStudentNum = Math.floor(Math.random() * students.length);
  let student = students[randomStudentNum];
  let element = document.getElementById("picked");
  element.innerHTML = student.first + " " + student.last;
}

pickStudent();
let pickButton = document.getElementById("pickStudent");
pickButton.addEventListener("click", pickStudent);

function renderList() {
  console.log("renderList", students);
  students.sort(function(a,b){return a.clickcount-b.clickcount})
  content = "";
  for (let i = 0; i < students.length; i++) {
    content += `<div class="student" id="${students[i].username}">
    ${students[i].first} ${students[i].last} ${students[i].clickcount}
  </div>`;
  }
  let element = document.getElementById("container");
  element.innerHTML = content;
}

renderList();

function listclick(e){
  console.log("listclick",e.target.id)
  for(let i = 0; i < students.length; i++){
    if(students[i].username == e.target.id){
      students[i].clickcount++;
    }
  }
  renderList();
}

let renderclick = document.getElementById("container");
renderclick.addEventListener("click",listclick);
    </script>

  

</body>

</html>
