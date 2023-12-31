# IastFramework
A package used to convert indic language to `iast` and `iast` to inidc langauge viceversa.

### Installation
```bash
pip install -i https://test.pypi.org/simple/ IastFramework # test pypi
pip install IastFramework  # still in development
```




### Usage
```python
import sqlite3
import os
import sys

from IastFramework import IAST

#create a IAST object
iast = IAST()

# customization
# iast = IAST(db_path='iast-token.db', table_name_alpha='IndianAlphabet',table_name_barakadi='Barakhadi')
```

### Converting All Indic language(hinid, telugu, kannada, Malayalam, Odia, Bengali&Assamese, Gujarati, tamil) to iast 
**`InProgress`** Research and Analysis is going on in  Tamil Script, Nastaliq Script, Sinhala Script.

```python
iast.to_iast('''ଧୃତରାଷ୍ଟ୍ର ଉଵାଚ |\tধৃতরাষ্ট্র উবাচ |\tધૃતરાષ્ટ્ર ઉવાચ |\tத்றுதராஷ்ட்ர உவாச |''')
# >>> 
# dhr̥tarāṣṭra uvāca |	dhr̥tarāṣṭra ubāca |	dhr̥tarāṣṭra uvāca |	ta்ṟutarāṣa்ṭa்ra uvāca |
```


### Convert `iast` to Indic Language 
Currently this can convert `IAST` to kannada, hindi, telugu, malyalam 

```python
word = 'kaṁ  itāḥ kiṁ  yuyutsavaḥ kl̥̄ kl̥ pāṇḍavānīkaṁ itāḥ kiṁ āṁ  īṁ   yuyutsuṁ  kiṁ rānsakhīṁstathā'
print(IAST.iast2tokens( word) )
# >>> ['k', 'a', 'ṁ', '  ', 'i', 't', 'ā', 'ḥ', ' ', 'k', 'i', 'ṁ', '  ', 'y', 'u', 'y', 'u', 't', 's', 'a', 'v', 'aḥ', ' ', 'k', 'l̥̄', ' ', 'k', 'l̥', ' ', 'p', 'ā', 'ṇ', 'ḍ', 'a', 'v', 'ā', 'n', 'ī', 'k', 'a', 'ṁ', ' ', 'i', 't', 'ā', 'ḥ', ' ', 'k', 'i', 'ṁ', ' ', 'ā', 'ṁ', '  ', 'ī', 'ṁ', '   ', 'y', 'u', 'y', 'u', 't', 's', 'u', 'ṁ', '  ', 'k', 'i', 'ṁ', ' ', 'r', 'ā', 'n', 's', 'a', 'kh', 'ī', 'ṁ', 's', 't', 'a', 'th', 'ā']
indic_lang = 'Telugu' # 'Kannada' # 'Telugu', 'Odia', 'Gujarati', 'Bengali-Assamsese', 
# 'Tamil' # in developement
IAST.dict_tokens2indic(dict_tokene_list,halant)
# >>> కం  ఇతాః కిం  యుయుత్సవః  పాణ్డవానీకం ఇతాః కిం ఆం  ఈం  కిం యుయుత్సుం రాన్సఖీంస్తథా
```


### Phonetic Hash for Phonetic Search 
```python
search_word = 'dhr̥tarāṣṭra uvāca'
search_word = search_word.strip().lower()



# to_iast
search_iast = iast.to_iast(search_word) # similar to idempotent matrx no loss of info if ':' not present
# >>> dhr̥tarāṣṭra uvāca
print(search_iast)

print("# Original Text:", search_word)
print('BASIC HASHING: ',IAST.basic_hash(search_iast))
print('NORMAL HASHING',IAST.normal_hash(search_iast))

# >>> Original Test: dhr̥tarāṣṭra uvāca
# >>> BASIC HASHING: drtrstr vc
# >>> NORMAL HASHING: drtarastra uvaca

```




### Contribute
**`InProgress`** Research and Analysis is going on in  Tamil Script, Nastaliq Script, Sinhala Script.<br>



### Issue
Please [open an issue ](https://github.com/dankarthik25/IAST-Framework/issues "open an issue ")<br>
here in case any bug was encountered. 
Mail id : dankarthik25@gmail.com
