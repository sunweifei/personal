# 在README 中记录编程中的小总结
## 滑轮控制
```
// 鼠标滑轮控制div 左右滑动
      function addEvent(obj,xEvent,fn) {
          if(obj.attachEvent){
            obj.attachEvent('on'+xEvent,fn);
          }else{
            obj.addEventListener(xEvent,fn,false);
          }
      }
      var oDiv = document.getElementById('test');
      addEvent(oDiv,'mousewheel',onMouseWheel);
      addEvent(oDiv,'DOMMouseScroll',onMouseWheel);
      // 当滚轮事件发生时，执行onMouseWheel这个函数
      function onMouseWheel() {
        var ev = ev || window.event;
            var down = true; // 定义一个标志，当滚轮向下滚时，执行一些操作
                down = ev.wheelDelta?ev.wheelDelta<0:ev.detail>0;
                var move_s=down>0?-50:50
                console.log(move_s)
            if(down){
                oDiv.scrollLeft += move_s;
            }else{
                oDiv.scrollLeft += move_s;
            }
            if(ev.preventDefault){/*FF 和 Chrome*/
                ev.preventDefault();// 阻止默认事件
            }
            return false;
      }
 ```
 ## 判断数组是否有重复元素 
 ```
 /*
 * @param {Array} arr
 * @return {Boolean}  repeat true
 */
 
 function isCheck(arr){
        var b = arr.join(",")
        for(let i = 0 ; i < b.length ; i++){
            if(b.replace(arr[i],"").indexOf(arr[i]) > -1){
                return true
            }
        }
        return false
    }
 ```
