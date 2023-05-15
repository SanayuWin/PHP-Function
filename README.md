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
$TempDate = $DateStart;
$ArrDate = array();
while($TempDate <= $DateEnd){
	$SetArr = explode("-",$TempDate);
	$Year = $SetArr[0];
	$ArrDate[$Year][$TempDate] = $TempDate;
	$TempDate = date('Y-m', strtotime($TempDate . ' +1 month'));
}
```

FPDF
Function spacing  height
```php
private $lineHeight;

function SetLineHeight($height) {
	$this->lineHeight = $height;
}

function MultiCell($w, $h, $txt, $border = 0, $align = 'J', $fill = false) {
	$lineHeight = $this->lineHeight ? $this->lineHeight : $h;
	parent::MultiCell($w, $lineHeight, $txt, $border, $align, $fill);
}

// Use
$pdf->SetLineHeight(0.08); // Set line spacing height to 0.08
$pdf->MultiCell(0.63, 0.15, iconv('UTF-8', 'TIS-620', $Simple), 1, 'L', false);


```
