# 2102-5
Second Day of Zoom Tools 
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
