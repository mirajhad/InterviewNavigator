# Duplicate Element

var arr=[1,2,3,3,3];

let unique=[];

for(let i=0;i<arr.length;i++){

if(unique.indexOf(arr[i])==-1){

    unique.push(arr[i])

}

}

console.log(unique);
