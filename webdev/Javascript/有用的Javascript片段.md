#���õ�JavascriptƬ��
---
## 1. ȫѡ,��ѡ

### 1. jsʵ��

`ȫѡ��ȫ��ѡ`
��һ������Ϊ��ѡ�����ƣ��ڶ�������Ϊ��ȫѡ����ȫ����ѡ��
```javascript
function allCheck(name,boolValue) {  
    var allvalue = document.getElementsByName(name);   
    for (var i = 0; i < allvalue.length; i++) {        
        if (allvalue[i].type == "checkbox")             
            allvalue[i].checked = boolValue;             
    }  
}  
```

`��ѡ`
 ����Ϊ��ѡ������

```javascript
function reserveCheck(name){  
    var revalue = document.getElementsByName(name);   
    for(i=0;i<revalue.length;i++){  
        if(revalue[i].checked == true)   
            revalue[i].checked = false;  
        else   
            revalue[i].checked = true;  
    }  
}
```

```html
  <input type="radio" name="all" id="all" onclick="checkAll('test')" />  
    ȫѡ  
    <input type="radio" name="all" id="Checkbox1" onclick="uncheckAll('test')" />  
    ȫ��ѡ  
    <input type="radio" name="all" id="Checkbox2" onclick="switchAll('test')" />  
    ��ѡ<br /> 
```

### JQueryʵ��
```html

<!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">  
<html>  
<head>  
<meta http-equiv="Content-Type" content="text/html; charset=UTF-8">  
<meta http-equiv="pragma" content="no-cache">  
<meta http-equiv="cache-control" content="no-cache">  
<meta http-equiv="expires" content="0">  
<script type="text/javascript" src="./res/js/jquery-1.8.2.js">  
</script>  
<title>JQueryʵ��checkboxȫѡ����ѡ��ȫ��ѡ</title>  
<script type="text/javascript">  
  
      
    //��ѡ��ѡ��  
    function checkboxOnclick(){  
        if($("[name='test'][checked]").length>1){  
            $("input[name='test']").each(function(){  
                $(this).attr("checked",false);  
            });    
        }else{  
            $("input[name='test']").each(function(){  
                $(this).attr("checked",true);  
            });    
        }  
    }  
      
    //��ȡѡ�и�ѡ���ֵ��һ��������ɾ��ʱ��Ҫʹ��  
    function getCheckBoxValues(){  
        var idsStr="";  
        $("input[name='test']").each(function(){  
            if($(this).attr("checked") == "checked"){  
                if($(this).val()!=""){  
                    idsStr+=$(this).val()+",";  
                }  
            }  
        });  
        if(idsStr!=""){  
            //����ɾ��  
            alert(idsStr);  
        }else{  
            alert("��ѡ����Ҫɾ���ļ�¼!");  
        }  
          
    }  
</script>  
</head>  
<body>  
      
    <input name="test" value="" type="checkbox" onclick="checkboxOnclick()" /> ��ѡ�� <br />  
    <input name="test" value="1" type="checkbox" /> 1 <br />  
    <input name="test" value="2" type="checkbox" /> 2 <br />  
    <input name="test" value="3" type="checkbox" /> 3 <br />  
    <input name="test" value="4" type="checkbox" /> 4 <br />  
    <input name="test" value="5" type="checkbox" /> 5 <br />  
    <input name="test" value="6" type="checkbox" /> 6 <br />  
    <input type="button" value="��ȡѡ�и�ѡ���ֵ����" onclick="getCheckBoxValues()">  
</body>  
</html>  
```


###  ʹ��jQuery ȥ��checkbox��ѡ��Ԫ��
```
$("input[name='chockbname']:checkbox:checked").each()
```
(ȫѡ����ѡ���������ѡ�е�checkbox)[http://www.cnblogs.com/0201zcr/p/4704468.html]
(jquery��checkbox,radio,select�ȷ����ܽ�)[http://www.haorooms.com/post/checkandselect]


## jQuery ������е�radio, select��option
### radio
```html
<input type="radio" name="radio" id="radio1" value="1" />1    
<input type="radio" name="radio" id="radio2" value="2" />2    
<input type="radio" name="radio" id="radio3" value="3" />3    
<input type="radio" name="radio" id="radio4" value="4" />4  
```

```javascript
$("input[type='radio'][name='radio']:checked").length == 0 //"û���κε�ѡ��ѡ��" : "�Ѿ���ѡ��";    

$('input[type="radio"][name="radio"]:checked').val(); // ��ȡһ��radio��ѡ�����ֵ    

$("input[type='radio'][name='radio'][value='2']").attr("checked", "checked");// ����value = 2��һ��Ϊѡ��    

$("#radio2").attr("checked", "checked"); // ����id=radio2��һ��Ϊѡ��  

$("input[type='radio'][name='radio']").get(1).checked = true; // ����index = 1�����ڶ���Ϊ��ǰѡ��    

var isChecked = $("#radio2").attr("checked");// id=radio2��һ���ѡ��״̬��isChecked = true, ����isChecked = false;   

var isChecked = $("input[type='radio'][name='radio'][value='2']").attr("checked");// value=2��һ���ѡ��״̬��isChecked = true, ����isChecked = false; 
```

### checkbox
```html
<input type="checkbox" name="checkbox" id="checkAll" />ȫѡ/ȡ��ȫѡ    
<input type="checkbox" name="checkbox" id="checkbox_id1" value="1" />1    
<input type="checkbox" name="checkbox" id="checkbox_id2" value="2" />2    
<input type="checkbox" name="checkbox" id="checkbox_id3" value="3" />3    
<input type="checkbox" name="checkbox" id="checkbox_id4" value="4" />4    
<input type="checkbox" name="checkbox" id="checkbox_id5" value="5" />5
```


```javascript
var val = $("#checkbox_id1").val();// ��ȡָ��id�ĸ�ѡ���ֵ    
var isSelected = $("#checkbox_id3").attr("checked"); // �ж�id=checkbox_id3���Ǹ���ѡ���Ƿ���ѡ��״̬��ѡ����isSelected=true;����isSelected=false;  

$("#checkbox_id3").attr("checked", true);// or    
$("#checkbox_id3").attr("checked", 'checked');// ��id=checkbox_id3���Ǹ���ѡ��ѡ�У�����    

$("#checkbox_id3").attr("checked", false);// or    
$("#checkbox_id3").attr("checked", '');// ��id=checkbox_id3���Ǹ���ѡ��ѡ�У�������    

$("input[name=checkbox][value=3]").attr("checked", 'checked');// ��name=checkbox, value=3 ���Ǹ���ѡ��ѡ�У�����    

$("input[name=checkbox][value=3]").attr("checked", '');// ��name=checkbox, value=3 ���Ǹ���ѡ��ѡ�У�������    

$("input[type=checkbox][name=checkbox]").get(2).checked = true;// ����index = 2����������Ϊѡ��״̬    

$("input[type=checkbox]:checked").each(function(){ //���ڸ�ѡ��һ��ѡ�е��Ƕ��,���Կ���ѭ�����ѡ�е�ֵ    
    alert($(this).val());    
});    
// ȫѡ/ȡ��ȫѡ    
$(function() {    
    $("#checkAll").click(function(){    
            if($(this).attr("checked") == true){// ȫѡ    
                $("input[type=checkbox][name=checkbox]").each(function(){    
                        $(this).attr("checked", true);    
                    });    
            } else {// ȡ��ȫѡ    
                $("input[type=checkbox][name=checkbox]").each(function(){    
                    $(this).attr("checked", false);    
                });    
            }    
        });    
});
```

### select

```html
<select name="select" id="select_id" style="width: 100px;">    
    <option value="1">11</option>    
    <option value="2">22</option>    
    <option value="3">33</option>    
    <option value="4">44</option>    
    <option value="5">55</option>    
    <option value="6">66</option>    
</select>  
```

```javascript

/**  
 * jQuery��ȡselect�ĸ���ֵ  
 */    
jQuery("#select_id").change(function(){                         // 1.ΪSelect����¼�����ѡ������һ��ʱ����     
    //code...    
});    

var checkValue = jQuery("#select_id").val();                    // 2.��ȡSelectѡ�����Value   

var checkText = jQuery("#select_id :selected").text();          // 3.��ȡSelectѡ�����Text     

var checkIndex = jQuery("#select_id").attr("selectedIndex");    // 4.��ȡSelectѡ���������ֵ,���ߣ�jQuery("#select_id").get(0).selectedIndex;   

var maxIndex = jQuery("#select_id :last").attr("index");        // 5.��ȡSelect��������ֵ,���ߣ�jQuery("#select_id :last").get(0).index;    


/**  
 * jQuery����Select��ѡ����  
 */    
jQuery("#select_id").get(0).selectedIndex = 1;                  // 1.����Select����ֵΪ1����ѡ��    
jQuery("#select_id").val(4);                                    // 2.����Select��ValueֵΪ4����ѡ��    
/**  
 * jQuery���/ɾ��Select��Option��  
 */    
jQuery("#select_id").append("<option value='����'>����option</option>");    // 1.ΪSelect׷��һ��Option(������)     
jQuery("#select_id").prepend("<option value='��ѡ��'>��ѡ��</option>");   // 2.ΪSelect����һ��Option(��һ��λ��)    
jQuery("#select_id").get(0).remove(1);                                      // 3.ɾ��Select������ֵΪ1��Option(�ڶ���)    
jQuery("#select_id :last").remove();                                        // 4.ɾ��Select������ֵ���Option(���һ��)     
jQuery("#select_id [value='3']").remove();                                  // 5.ɾ��Select��Value='3'��Option     
jQuery("#select_id").empty();                                               // 6.��������б�    
```
