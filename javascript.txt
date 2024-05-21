
var isOparatorClicked=false;
var symbol=true;
var isMultipleClicked=true;
var referance=false;
let oldValue,newValue,str,store,str2,str3,varible; //string
let oldValueF;//float
let newValueF;//float
let result,num,result2=0,n1=0;//float
let ch,ch2,ch3='x';//char
let syntax;//try cache
let number;//double
const pi=Math.PI;
let value,position,first=1;//int
let doc;
try {
//division called according to previous operator
function division() {
    if(first==0) {
        result2=num=result2/n1;
    }
    varible=String(result2);
    document.getElementById('displayLabel').value=varible;
    if(ch3!='x') {
        ch2=ch3;
        position=varible.indexOf("e");
        if(position==-1) {
          document.getElementById('displayLabel3').value=str;
        }else {
            var stringLength2;
            stringLength2=varible.length;
            str2=varible.substring(0, position);
            str3=varible.substring(position+2, stringLength2);
            document.getElementById('displayLabel3').value=str2+"x10^"+str3;
        }
        if(varible=="NaN"||"undefined"){
            document.getElementById('displayLabel3').value="SYNTAX ERROR";
        }
    }
    first=0;
}
//Multiplication called according to previous operator
function multiplication() {
    if(first==0) {
        result2=num=result2*n1;
    }
    varible=String(result2);
    document.getElementById('displayLabel').value=varible;
    if(ch3!='x') {
        ch2=ch3;
        position=varible.indexOf("e");
        if(position==-1) {
            document.getElementById('displayLabel3').value=str;
        }else {
            var stringLength2;
            stringLength2=varible.length;
            str2=varible.substring(0, position);
            str3=varible.substring(position+2, stringLength2);
            document.getElementById('displayLabel3').value=str2+"x10^"+str3;
        }
        if(varible=="NaN"||"undefined"){
            document.getElementById('displayLabel3').value="SYNTAX ERROR";
        }
    }
    first=0;
}
//Subtraction called according to previous operator
function substraction() {
    if(first==0) {
        result2=num=result2-n1;
    }
    varible=String(result2);
    document.getElementById('displayLabel').value=varible;
    if(ch3!='x') {
        ch2=ch3;
        position=varible.indexOf("e");
        if(position==-1) {
          document.getElementById('displayLabel3').value=str;
        }else {
            var stringLength2;
            stringLength2=varible.length;
            str2=varible.substring(0, position);
            str3=varible.substring(position+2, stringLength2);
            document.getElementById('displayLabel3').value=str2+"x10^"+str3;
        }
        if(varible=="NaN"||"undefined"){
            document.getElementById('displayLabel3').value="SYNTAX ERROR";
        }
    }
    first=0;
}
//Addition called according to previous operator
function addition() {
    if(first==0) {
        result2=num=result2+n1;
    }
    varible=String(result2);
    document.getElementById('displayLabel').value=varible;
    if(ch3!='x') {
        ch2=ch3;
        position=varible.indexOf("e");
        if(position==-1) {
          document.getElementById('displayLabel3').value=str;
        }else {
            var stringLength2;
            stringLength2=varible.length;
            str2=varible.substring(0, position);
            str3=varible.substring(position+2, stringLength2);
            document.getElementById('displayLabel3').value=str2+"x10^"+str3;
        }
        if(varible=="NaN"||"undefined"){
            document.getElementById('displayLabel3').value="SYNTAX ERROR";
        }
    }
    first=0;
}
function number_Button(num){
    if(isOparatorClicked) {		
        document.getElementById('displayLabel').value=num;
        isOparatorClicked=false;
     }else {
        doc=document.getElementById('displayLabel').value;
        document.getElementById('displayLabel').value=doc+num;
     }
     doc=document.getElementById('displayLabel2').value;
     document.getElementById('displayLabel2').value=doc+num; 
}

function equall_Button(){   
        if(syntax=='@') {
            document.getElementById('displayLabel3').value="SYNTAX ERROR";
        }
        newValue=document.getElementById('displayLabel').value;  
        if(newValue!="%") {
            newValueF=parseFloat(newValue);
        }
        if(symbol) {
          oldValueF=parseFloat(oldValue);
        }
        symbol=true;
        if(ch3=='x') {
            switch (ch) {
                case'+':
                    if(newValue=="%") {
                        document.getElementById('displayLabel3').value="SYNTAX ERROR";
                    }else {
                        result=oldValueF+newValueF;
                        str=String(result);
                        position=str.indexOf("e");
                        if(position==-1) {
                            document.getElementById('displayLabel').value=str;
                            document.getElementById('displayLabel3').value=str;
                        }else {
                            var stringLength2;
                            stringLength2=str.length;
                            str2=str.substring(0, position);
                            str3=str.substring(position+2, stringLength2);
                            document.getElementById('displayLabel').value=str;
                            document.getElementById('displayLabel3').value=str2+"x10^"+str3;
                        }
                   }
                   break;
        
                case '-':
                    if(newValue=="%") {
                        document.getElementById('displayLabel3').value="SYNTAX ERROR";
                    }else {
                        result=oldValueF-newValueF;
                        str=String(result);
                        position=str.indexOf("e");
                        if(position==-1) {
                            document.getElementById('displayLabel').value=str;
                            document.getElementById('displayLabel3').value=str;
                        }else {
                            var stringLength2;
                            stringLength2=str.length;
                            str2=str.substring(0, position);
                            str3=str.substring(position+2, stringLength2);
                            document.getElementById('displayLabel').value=str;
                            document.getElementById('displayLabel3').value=str2+"x10^"+str3;
                        }
                    }
                    break;
        
                case '*':
                    if(newValue=="%") {
                        document.getElementById('displayLabel3').value="SYNTAX ERROR";
                    }else {
                        result=oldValueF*newValueF;
                        str=String(result);
                        position=str.indexOf("e");
                        if(position==-1) {
                            document.getElementById('displayLabel').value=str;
                            document.getElementById('displayLabel3').value=str;
                        }else {
                            var stringLength2;
                            stringLength2=str.length;
                            str2=str.substring(0, position);
                            str3=str.substring(position+2, stringLength2);
                            document.getElementById('displayLabel').value=str;
                            document.getElementById('displayLabel3').value=str2+"x10^"+str3;
                        }
                    }
                    break;
        
                case '/':
                    if(newValue=="%") {
                        document.getElementById('displayLabel3').value="SYNTAX ERROR";
                    }else {
                        result=oldValueF/newValueF;
                        str=String(result);
                        position=str.indexOf("e");
                        if(position==-1) {
                            document.getElementById('displayLabel').value=str;
                            document.getElementById('displayLabel3').value=str;
                        }else {
                            var stringLength2;
                            stringLength2=str.length;
                            str2=str.substring(0, position);
                            str3=str.substring(position+2, stringLength2);
                            document.getElementById('displayLabel').value=str;
                            document.getElementById('displayLabel3').value=str2+"x10^"+str3;
                        }
                    }
                    break;
            
                case '%':
                    if(newValue=="%") {
                        document.getElementById('displayLabel3').value="syntax error use method(x % y)";
                    }else {
                        result=(oldValueF/newValueF)*100;
                        str=String(result);
                        position=str.indexOf("e");
                        if(position==-1) {
                            document.getElementById('displayLabel').value=str;
                            document.getElementById('displayLabel3').value=str;
                        }else {
                            var stringLength2;
                            stringLength2=str.length;
                            str2=str.substring(0, position);
                            str3=str.substring(position+2, stringLength2);
                            document.getElementById('displayLabel').value=str;
                            document.getElementById('displayLabel3').value=str2+"x10^"+str3;
                        }
                    }
                    break;
                    
                case '^':
                    if(newValue=="%") {
                        document.getElementById('displayLabel3').value="SYNTAX ERROR";
                    }else {
                        powResult=Math.pow(oldValueF, newValueF);
                        str=String(powResult);
                        position=str.indexOf("e");
                        if(position==-1) {
                            document.getElementById('displayLabel').value=str;
                            document.getElementById('displayLabel3').value=str;
                        }else {
                            var stringLength2;
                            stringLength2=str.length;
                            str2=str.substring(0, position);
                            str3=str.substring(position+2, stringLength2);
                            document.getElementById('displayLabel').value=str;
                            document.getElementById('displayLabel3').value=str2+"x10^"+str3;
                        }
                    }
                    break;
                    
                case 's':  
                    number=(pi/180)*newValueF;
                    number=Math.sin(number);
                    str=String(number);
                    position=str.indexOf("e");
                    if(position==-1) {
                        document.getElementById('displayLabel').value=str;
                        document.getElementById('displayLabel3').value=str;
                    }else {
                        var stringLength2;
                        stringLength2=str.length;
                        str2=str.substring(0, position);
                        str3=str.substring(position+2, stringLength2);
                        document.getElementById('displayLabel').value=str;
                        document.getElementById('displayLabel3').value=str2+"x10^"+str3;
                    }
                    break;
                    
                case 'c':
                    number=(pi/180)*newValueF;
                    number=Math.cos(number);
                    str=String(number);
                    position=str.indexOf("e");
                    if(position==-1) {
                        document.getElementById('displayLabel').value=str;
                        document.getElementById('displayLabel3').value=str;
                    }else {
                        var stringLength2;
                        stringLength2=str.length;
                        str2=str.substring(0, position);
                        str3=str.substring(position+2, stringLength2);
                        document.getElementById('displayLabel').value=str;
                        document.getElementById('displayLabel3').value=str2+"x10^"+str3;
                    }
                    break;
  
                case 't':
                    number=(pi/180)*newValueF;
                    number=Math.tan(number);
                    str=String(number);
                    position=str.indexOf("e");
                    if(position==-1) {
                        document.getElementById('displayLabel').value=str;
                        document.getElementById('displayLabel3').value=str;
                    }else {
                        var stringLength2;
                        stringLength2=str.length;
                        str2=str.substring(0, position);
                        str3=str.substring(position+2, stringLength2);
                        document.getElementById('displayLabel').value=str;
                        document.getElementById('displayLabel3').value=str2+"x10^"+str3;
                    }
                    break;
                    
                case '#': //combination
                    
                    if(newValue=="%") {
                        document.getElementById('displayLabel3').value="syntax error use method(x c y)";
                    }else {
                        num=oldValueF-newValueF;
                        var n=1;
                        var r=1;
                        var k=1; //means (n-r)!
                        for(var i=1;i<=oldValueF;i++) {
                            n=n*i;
                        }
                        for(var j=1;j<=newValueF;j++) {
                            r=r*j;
                        }
                        for(var m=1;m<=num;m++) {
                            k=k*m;
                        }
                        number=n/(r*k);
                        str=String(number);
                        position=str.indexOf("e");
                        if(position==-1) {
                            document.getElementById('displayLabel').value=str;
                            document.getElementById('displayLabel3').value=str;
                        }else {
                            var stringLength2;
                            stringLength2=str.length;
                            str2=str.substring(0, position);
                            str3=str.substring(position+2, stringLength2);
                            document.getElementById('displayLabel').value=str;
                            document.getElementById('displayLabel3').value=str2+"x10^"+str3;
                        }
                    }
                    break;
                    
                case 'p':
                    if(newValue=="%") {
                        document.getElementById('displayLabel3').value="syntax error use method(x P y)";
                    }else {
                        num=oldValueF-newValueF;
                        var n=1;
                        var k=1; //means (n-r)!
                        for(var i=1;i<=oldValueF;i++) {
                            n=n*i;
                        }
                        for(var m=1;m<=num;m++) {
                            k=k*m;
                        }
                        number=n/k;
                        str=String(number);
                        position=str.indexOf("e");
                        if(position==-1) {
                            document.getElementById('displayLabel').value=str;
                            document.getElementById('displayLabel3').value=str;
                        }else {
                            var stringLength2;
                            stringLength2=str.length;
                            str2=str.substring(0, position);
                            str3=str.substring(position+2, stringLength2);
                            document.getElementById('displayLabel').value=str;
                            document.getElementById('displayLabel3').value=str2+"x10^"+str3;
                        }
                    }
                    break;
                
                case 'i': //aSin
                    
                    number=Math.asin(newValueF);
                    number=(180/pi)*number;
                    str=String(number);
                    position=str.indexOf("e");
                    if(position==-1) {
                        document.getElementById('displayLabel').value=str;
                        document.getElementById('displayLabel3').value=str;
                    }else {
                        var stringLength2;
                        stringLength2=str.length;
                        str2=str.substring(0, position);
                        str3=str.substring(position+2, stringLength2);
                        document.getElementById('displayLabel').value=str;
                        document.getElementById('displayLabel3').value=str2+"x10^"+str3;
                    }
                    break;
                    
                case 'o'://aCos
                    
                    number=Math.acos(newValueF);
                    number=(180/pi)*number;
                    str=String(number);
                    position=str.indexOf("e");
                    if(position==-1) {
                        document.getElementById('displayLabel').value=str;
                        document.getElementById('displayLabel3').value=str;
                    }else {
                        var stringLength2;
                        stringLength2=str.length;
                        str2=str.substring(0, position);
                        str3=str.substring(position+2, stringLength2);
                        document.getElementById('displayLabel').value=str;
                        document.getElementById('displayLabel3').value=str2+"x10^"+str3;
                    }
                    break;
                    
                case 'a'://aTan
                    
                    number=Math.atan(newValueF);
                    number=(180/pi)*number;
                    str=String(number);
                    position=str.indexOf("e");
                    if(position==-1) {
                        document.getElementById('displayLabel').value=str;
                        document.getElementById('displayLabel3').value=str;
                    }else {
                        var stringLength2;
                        stringLength2=str.length;
                        str2=str.substring(0, position);
                        str3=str.substring(position+2, stringLength2);
                        document.getElementById('displayLabel').value=str;
                        document.getElementById('displayLabel3').value=str2+"x10^"+str3;
                    }
                    break;
                    
                case 'g':   // log button
                    
                    number=Math.log10(newValueF);
                    str=String(number);
                    position=str.indexOf("e");
                    if(position==-1) {
                        document.getElementById('displayLabel').value=str;
                        document.getElementById('displayLabel3').value=str;
                    }else {
                        var stringLength2;
                        stringLength2=str.length;
                        str2=str.substring(0, position);
                        str3=str.substring(position+2, stringLength2);
                        document.getElementById('displayLabel').value=str;
                        document.getElementById('displayLabel3').value=str2+"x10^"+str3;
                    }
                    break;
                    
                case '√':
                    doc=document.getElementById('displayLabel').value;
                    number=parseFloat(doc);
                    number=Math.sqrt(number);
                    str=String(number);
                    position=str.indexOf("e");
                    if(position==-1) {
                        document.getElementById('displayLabel').value=str;
                        document.getElementById('displayLabel3').value=str;
                    }else {
                        var stringLength2;
                        stringLength2=str.length;
                        str2=str.substring(0, position);
                        str3=str.substring(position+2, stringLength2);
                        document.getElementById('displayLabel').value=str;
                        document.getElementById('displayLabel3').value=str2+"x10^"+str3;
                    }
                    break;
                case '2': //square function
                    doc=document.getElementById('displayLabel').value;
                    number=parseFloat(doc);
                    number=number*number;
                    str=String(number);
                    position=str.indexOf("e");
                    if(position==-1) {
                        document.getElementById('displayLabel').value=str;
                        document.getElementById('displayLabel3').value=str;
                    }else {
                        var stringLength2;
                        stringLength2=str.length;
                        str2=str.substring(0, position);
                        str3=str.substring(position+2, stringLength2);
                        document.getElementById('displayLabel').value=str;
                        document.getElementById('displayLabel3').value=str2+"x10^"+str3;
                    }
                    break;
                  
                case '!':
                    doc=document.getElementById('displayLabel').value;
                    value=parseFloat(doc);
                    number=1;
                    for(var i=1;i<=value;i++) {
                         number=number*i;
                    }
                     str=String(number);
                     position=str.indexOf("e");
                    if(position==-1) {
                        document.getElementById('displayLabel').value=str;
                        document.getElementById('displayLabel3').value=str;
                    }else {
                        var stringLength2;
                        stringLength2=str.length;
                        str2=str.substring(0, position);
                        str3=str.substring(position+2, stringLength2);
                        document.getElementById('displayLabel').value=str;
                        document.getElementById('displayLabel3').value=str2+"x10^"+str3;
                    }
                     break;
                
                case 'z':
                    if(newValue=="%") {
                        document.getElementById('displayLabel3').value="SYNTAX ERROR";
                    }else {
                        oldValueF=1/oldValueF;
                        powResult=Math.pow(newValueF,oldValueF);
                        str=String(powResult);
                        position=str.indexOf("e");
                        if(position==-1) {
                            document.getElementById('displayLabel').value=str;
                            document.getElementById('displayLabel3').value=str;
                        }else {
                            var stringLength2;
                            stringLength2=str.length;
                            str2=str.substring(0, position);
                            str3=str.substring(position+2, stringLength2);
                            document.getElementById('displayLabel').value=str;
                            document.getElementById('displayLabel3').value=str2+"x10^"+str3;
                        }
                    }
                    break;

                case 'H':   // ln button
                    
                    number=Math.log(newValueF);
                    str=String(number);
                    position=str.indexOf("e");
                    if(position==-1) {
                        document.getElementById('displayLabel').value=str;
                        document.getElementById('displayLabel3').value=str;
                    }else {
                        var stringLength2;
                        stringLength2=str.length;
                        str2=str.substring(0, position);
                        str3=str.substring(position+2, stringLength2);
                        document.getElementById('displayLabel').value=str;
                        document.getElementById('displayLabel3').value=str2+"x10^"+str3;
                    }
                    break;
                        
                case 'W'://x10^X
                    if(newValue=="%") {
                        document.getElementById('displayLabel3').value="SYNTAX ERROR";
                    }else {
                        oldValueF=oldValueF*10;
                        powResult=Math.pow(oldValueF, newValueF);
                        str=String(powResult);
                        position=str.indexOf("e");
                        if(position==-1) {
                            document.getElementById('displayLabel').value=str;
                            document.getElementById('displayLabel3').value=str;
                        }else {
                            var stringLength2;
                            stringLength2=str.length;
                            str2=str.substring(0, position);
                            str3=str.substring(position+2, stringLength2);
                            document.getElementById('displayLabel').value=str;
                            document.getElementById('displayLabel3').value=str2+"x10^"+str3;
                        }
                    }
                    break;
                    

                default  :
                document.getElementById('displayLabel3').value="SYNTAX ERROR";
            }
        }else {
            
            doc=document.getElementById('displayLabel').value;
            n1=parseFloat(doc);
            switch(ch3) {
            
                case '+':
                    addition();
                    break;
                case '-':
                    substraction();
                    break;
                case '/':
                    division();
                    break;
                case '*':
                    multiplication();
                    break;
            } 
        
            document.getElementById('displayLabel').value=varible;
            console.log(varible);
            position=varible.indexOf("e");
            if(position==-1) {
                document.getElementById('displayLabel3').value=varible;
            }else {
                var stringLength2;
                stringLength2=varible.length;
                str2=varible.substring(0, position);
                str3=varible.substring(position+2, stringLength2);
                document.getElementById('displayLabel').value=str;
                document.getElementById('displayLabel3').value=str2+"x10^"+str3;
            }
            if(varible=="NaN"||"undefined"){
                document.getElementById('displayLabel3').value="SYNTAX ERROR";
            }
        }
   }
function division_Button(){
    isOparatorClicked=true;
    oldValue=document.getElementById('displayLabel').value;
    ch='/';
    doc=document.getElementById('displayLabel2').value;
    document.getElementById('displayLabel2').value=doc+"÷";
    if(first==1){
        doc=document.getElementById('displayLabel').value;
        result2=num=parseFloat(doc);
        ch2='/';
    }
    else{
        doc=document.getElementById('displayLabel').value;
        n1=parseFloat(doc);
        ch3='/';
    }
    //Action corresponding to previous operator
    switch(ch2) {
        case '+':
            addition();
            break;
        case '-':
            substractio();
            break;
        case '/':
            division();
            break;
        case '*':
            multiplication();
            break;
    }
    document.getElementById('displayLabel').value="%";
}
function multiplication_Button(){
    isOparatorClicked=true;
    oldValue=document.getElementById('displayLabel').value;
    ch='*';
    doc=document.getElementById('displayLabel2').value;
    document.getElementById('displayLabel2').value=doc+"×";
    if(first==1){
        doc=document.getElementById('displayLabel').value;
        result2=num=parseFloat(doc);
        ch2='*';
    }
    else{
        doc=document.getElementById('displayLabel').value;
        n1=parseFloat(doc);
        ch3='*';
    }
    //Action corresponding to previous operator
    switch(ch2) {
        case '+':
            addition();
            break;
        case '-':
            substraction();
            break;
        case '/':
            division();
            break;
        case '*':
            multiplication();
            break;
    }
    document.getElementById('displayLabel').value="%";     
}
function minus_Button(){
    isOparatorClicked=true;
    oldValue=document.getElementById('displayLabel').value;
    ch='-';
    doc=document.getElementById('displayLabel2').value;
    document.getElementById('displayLabel2').value=doc+"-";
    if(first==1){
        doc=document.getElementById('displayLabel').value;
        result2=num=parseFloat(doc);
        ch2='-';
    }
    else{
        doc=document.getElementById('displayLabel').value;
        n1=parseFloat(doc);
        ch3='-';
    }
    //Action corresponding to previous operator
    switch(ch2) {
        case '+':
            addition();
            break;
        case '-':
            substraction();
            break;
        case '/':
            division();
            break;
        case '*':
            multiplication();
            break;
    }
    document.getElementById('displayLabel').value="%";    
}
function plus_Button(){
    isOparatorClicked=true;
    oldValue=document.getElementById('displayLabel').value;
    ch='+';
    doc=document.getElementById('displayLabel2').value;
    document.getElementById('displayLabel2').value=doc+"+";
    if(first==1){
        doc=document.getElementById('displayLabel').value;
        result2=num=parseFloat(doc);
        ch2='+';
    }
    else{
        doc=document.getElementById('displayLabel').value;
        n1=parseFloat(doc);
        ch3='+';
    }
    //Action corresponding to previous operator
    switch(ch2) {
        case '+':
            addition();
            break;
        case '-':
            substraction();
            break;
        case '/':
            division();
            break;
        case '*':
            multiplication();
            break;
    }
    document.getElementById('displayLabel').value="%";    
}
function percentage_Button(){
    isOparatorClicked=true;
    oldValue=document.getElementById('displayLabel').value;
    ch='%';
    doc=document.getElementById('displayLabel2').value;
    document.getElementById('displayLabel2').value=doc+"%";
    document.getElementById('displayLabel').value="%";
}
function root_Button(){
    isOparatorClicked=true;
    oldValue=document.getElementById('displayLabel').value;
    ch='z';
    doc=document.getElementById('displayLabel2').value;
    document.getElementById('displayLabel2').value=doc+"√";
    document.getElementById('displayLabel').value="%";
}
function clear_Button(){
    document.getElementById('displayLabel').value="";
    document.getElementById('displayLabel2').value="";
    document.getElementById('displayLabel3').value="";
    ch3='x';
    oldValue="";
    newValue="";
    str="";
    str2="";
    str3="";
    varible="";
    oldValueF=0;
    newValueF=0;
    result=0;
    result2=0; 
    n1=0;
    ch='1';
    ch2='1';
    number=0;
    value=0;
    position=-1;
    first=1;
}
function backspace_Button(){
    var stringLength;
    str=document.getElementById('displayLabel').value;
    stringLength=str.length;
    if(stringLength>=1) {
        str=str.substring(0, stringLength-1);
        document.getElementById('displayLabel').value=str;
    }
    var stringLength2;
    str2=document.getElementById('displayLabel2').value;
    stringLength2=str2.length;
    if(stringLength>=1) {
        str2=str2.substring(0, stringLength2-1);
        document.getElementById('displayLabel2').value=str2;
    }
}
function power_Button(){
    isOparatorClicked=true;
    oldValue=document.getElementById('displayLabel').value;
    ch='^';
    doc=document.getElementById('displayLabel2').value;
    document.getElementById('displayLabel2').value=doc+"^";
    document.getElementById('displayLabel').value="%";
}
function sin_Button(){
    isOparatorClicked=true;
    symbol=false;
    ch='s';
    doc=document.getElementById('displayLabel2').value;
    document.getElementById('displayLabel2').value=doc+"sin:";        
}
function cos_Button(){
    isOparatorClicked=true;
    symbol=false;
    ch='c';
    doc=document.getElementById('displayLabel2').value;
    document.getElementById('displayLabel2').value=doc+"cos:";        
}
function tan_Button(){
    isOparatorClicked=true;
    symbol=false;
    ch='t';
    doc=document.getElementById('displayLabel2').value;
    document.getElementById('displayLabel2').value=doc+"tan:";        
}
function asin_Button(){
    isOparatorClicked=true;
    symbol=false;
    ch='i';
    doc=document.getElementById('displayLabel2').value;
    document.getElementById('displayLabel2').value=doc+"sin-¹:";        
}
function acos_Button(){
    isOparatorClicked=true;
    symbol=false;
    ch='o';
    doc=document.getElementById('displayLabel2').value;
    document.getElementById('displayLabel2').value=doc+"cos-¹:";        
}
function atan_Button(){
    isOparatorClicked=true;
    symbol=false;
    ch='a';
    doc=document.getElementById('displayLabel2').value;
    document.getElementById('displayLabel2').value=doc+"tan-¹:";        
}
function log_Button(){
    isOparatorClicked=true;
    symbol=false;
    ch='g';
    doc=document.getElementById('displayLabel2').value;
    document.getElementById('displayLabel2').value=doc+"log:";        
}
function combination_Button(){
    isOparatorClicked=true;
    oldValue=document.getElementById('displayLabel').value;
    ch='#';
    doc=document.getElementById('displayLabel2').value;
    document.getElementById('displayLabel2').value=doc+"C";
    document.getElementById('displayLabel').value="%";
}
function permutation_Button(){
    isOparatorClicked=true;
    oldValue=document.getElementById('displayLabel').value;
    ch='p';
    doc=document.getElementById('displayLabel2').value;
    document.getElementById('displayLabel2').value=doc+"P";
    document.getElementById('displayLabel').value="%";
}
function sqrt_Button(){
    isOparatorClicked=true;
    symbol=false;
    ch='√';
    doc=document.getElementById('displayLabel2').value;
    document.getElementById('displayLabel2').value=doc+"√";        
}
function square_Button(){
    isOparatorClicked=true;
    symbol=false;
    ch='2';
    doc=document.getElementById('displayLabel2').value;
    document.getElementById('displayLabel2').value=doc+"²";        
}
function plusOrMinus_Button(){
    doc=document.getElementById('displayLabel').value;
    num=parseFloat(doc);
    num=-num;
    num=String(num);
    document.getElementById('displayLabel').value=num;
    str=document.getElementById('displayLabel2').value;
    str="-"+str;
    document.getElementById('displayLabel2').value=str;
}
function factorial_Button(){
    isOparatorClicked=true;
    symbol=false;
    ch='!';
    doc=document.getElementById('displayLabel2').value;
    document.getElementById('displayLabel2').value=doc+"!";   
}
function sto_Button(){

    store=document.getElementById('displayLabel').value;
}
function paste_Button(){
    document.getElementById('displayLabel').value=store;
    position=store.indexOf("e");
    if(position==-1) {
        doc=document.getElementById('displayLabel2').value;
        document.getElementById('displayLabel2').value=doc+store;
    }else {
        var stringLength2;
        stringLength2=store.length;
        str2=str.substring(0, position);
        str3=str.substring(position+2, stringLength2);
        doc=document.getElementById('displayLabel2').value;
        document.getElementById('displayLabel2').value=doc+str2+"x10^"+str3;
    }
}function pi_Button(){
    document.getElementById('displayLabel').value="3.14159262";
    
        doc=document.getElementById('displayLabel2').value;
        document.getElementById('displayLabel2').value=doc+"π";
}
function e_Button(){
    document.getElementById('displayLabel').value="2.718281828459";
    
        doc=document.getElementById('displayLabel2').value;
        document.getElementById('displayLabel2').value=doc+"e";
}
function ln_Button(){
    isOparatorClicked=true;
    symbol=false;
    ch='H';
    doc=document.getElementById('displayLabel2').value;
    document.getElementById('displayLabel2').value=doc+"ln:";        
}
function ten_Button(){
    isOparatorClicked=true;
    oldValue=document.getElementById('displayLabel').value;
    ch='W';
    doc=document.getElementById('displayLabel2').value;
    document.getElementById('displayLabel2').value=doc+"x10^";
    document.getElementById('displayLabel').value="%";
}
} catch (error) {
    syntax='@';
}