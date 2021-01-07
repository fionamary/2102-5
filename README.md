# 2102-5
Second Day of Zoom Tools 
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
console.log("hello world");

const students = [];

function makeStudent(username,first,last,gradeLevel){
  const student = {};
  student.username = username;
  student.first = first;
  student.last = last;
  student.gradeLevel = gradeLevel;
  console.log(student);
  return student;
}

students.push(makeStudent("FionaAwsome","Fiona","Awsome",12));
students.push(makeStudent("Lucy","Lucy","Bishop",11));
console.log(students);

function pickStudent(){
  let randomStudentNum = Math.floor(Math.random()*students.length);
  let student = students[randomStudentNum];
  let element = document.getElementById("picked");
  element.innerHTML = student.first + " " + student.last;
}

pickStudent();
let pickButton = document.getElementById("pickStudent");
pickButton.addEventListener("click",pickStudent);
    </script>

  

</body>

</html>
 
