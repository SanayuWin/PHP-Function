# Function PHP


Function Change Format Date

```php
$date = DateTime::createFromFormat('d/m/Y', $DateBefore);
$DateAfter = $date->format('Y-m-d');
```
Function Convert Text
```php
function ConvertText($Data){
  $Data = str_replace("''","\"",$Data);
  $val=trim($Data);
  $val=str_replace("\\'","'",$val);
  $val=stripslashes($val);
  $val=htmlspecialchars($val,ENT_NOQUOTES); 		
  $Data=htmlspecialchars($val,ENT_QUOTES); 
  $Data=str_replace("@","&#64;",$Data);	
  return $Data;
}
```

Function Check Text
```php
function Chk_S($text){
  $text = str_replace("&amp;","&",$text);
  $text = str_replace("amp;","",$text);
  $text = str_replace("&quot;","''",$text);
  $text = str_replace("&lt;","<",$text);
  $text = str_replace("&gt;",">",$text);
  $text = str_replace("&#39;","'",$text);
  $text = str_replace("&#039;","'",$text);
  return $text;
}
```

Function Date
```php
// Month ++
$ArrDate = array();
while($TempDate <= $DateEnd){
  $SetArr = explode("-",$TempDate);
  $Year = $SetArr[0];
  $ArrDate[$Year][$TempDate] = $TempDate;
  $TempDate = date('Y-m', strtotime($TempDate . ' +1 month'));
}

```

