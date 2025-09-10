# ps5_aigrand_docmodel

ध्यान से सुनो , 

```
{0:"Background", 
1: "Text", 
2: "Title", 
3 : "List", 
4: "Table", 
5: "Figure""}
ये सारे classes हैं जिनमे classify करना है 
```

ये सारे languages में करना है 
English  Hindi  Urdu  Arabic  Nepalese  Persian 

___________________________________

मगर उनके training  data के हिसाब से ------


वो text  को बैकग्राउंड मानता है \
title  को text \
लिस्ट को टाइटल \
(मतलब एक पिछले में classify करता है)
___________________________________

# अब सुनो क्या क्या करना बचा है :
 
 
## [major] test में सिर्फ अंग्रेजी में text था|


उसके लिए हमे problem statement में दिए गए datasets एस्तेमाल कर सकते हैं | 

एन सबका अध्ययन करो और किसी तरह से हमारे test data जैसा बदलने की कोशिश करो  

(हिन्दी उर्दू फारसी ही नहीं english में भी training data और मिले तो अच्छा ही रहेगा )

```
DocLayNet 
PubLayNet 
RvlCdip 
ICDAR-MLT 2019 
HI-OCR 
FUNSD 
SROIE 
``` 



## [major] ईस्को देखो क्या क्या कर सकते हैं  

The rotated ones may require  de
skewing first. The Ground truth bounding are for the de-skewed images. The 
ground truth bboxes are in HBB format


## [minor] देखो हम कहाँ कहाँ असफल हो रहे हैं 

मैंने test data को random split किया था , कोशिश करो **class wise split** करने की| उससे result अच्छा होगा पक्का 


## [minor] दिए गए data में ocr की images नहीं थी|

ocr का data भी निकालो ऊपर 1st वाले dataset से |

__________________________________

> पहले code चलाने का प्रयास तो करो देखो 2-3 epoch पे कितना वक्त ले रहा है |  

> pstatement के साथ दिए गए data की लिंक ग्रुप में से उठा लो | 

