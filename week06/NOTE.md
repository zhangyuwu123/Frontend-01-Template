# 每周总结可以写在这里

状态机：匹配abcabcabx
```
//abcabcabx
function match(str){
    let state = start
    for (const input of str) {
        console.log(input)
        state = state(input)
    }
    return state === end
}

function ftB(s){
    if(s == 'b'){
        return ftC
    }else{
        return start
    }
}

function ftC(s){
    if(s == 'c'){
        return ftA2
    }else{
        return start
    }
}

function ftA2(s){
    if(s == 'a'){
        return ftB2
    }else{
        return start
    }
}
function ftB2(s){
    if(s == 'b'){
        return ftX
    }else{
        return start
    }
}
function ftX(s){
    if(s == 'x'){
        return end
    }else{
        return ftC(s)
    }
}
function start(c){
    if(c == 'a'){
        return ftB
    }else {
        return start
    }
}

function end(){
    return end
}
var pattern = 'abcabx'
var temp = 'i am abcabcabx'
match(temp)
```

状态机：匹配ababababx
```
function match(str){
    let state = start
    for (const input of str) {
        console.log(input)
        state = state(input)
    }
    return state === end
}

function ftB(s){
    if(s == 'b'){
        return ftA2
    }else{
        return start
    }
}

function ftA2(s){
    if(s == 'a'){
        return ftB2
    }else{
        return start
    }
}
function ftB2(s){
    if(s == 'b'){
        return ftA3
    }else{
        return start
    }
}
function ftA3(s){
    if(s == 'a'){
        return ftB3
    }else{
        return start
    }
}
function ftB3(s){
    if(s == 'b'){
        return ftX
    }else{
        return start
    }
}
function ftX(s){
    if(s == 'x'){
        return end
    }else{
        return ftC(s)
    }
}
function start(c){
    if(c == 'a'){
        return ftB
    }else {
        return start
    }
}

function end(){
    return end
}
var pattern = 'abababx'
var temp = 'i am abababx'
match(temp)
```
