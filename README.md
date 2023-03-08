## Introduction 簡介
g2p is made by Python with the dictionary files of [g2p](https://github.com/Kyubyong/g2p) which is developed by Park, Kyubyong & Kim, Jongseok.

原始由Park, Kyubyong & Kim, Jongseok所開發的

## 安裝方式 
pip install git+https://github.com/zxp54332/g2p.git

## 20200918 Updates:
新增單詞詞性標註  
```
import g2p_en

g2p = g2p_en.G2p()
# Regular usage I
print(g2p("This is great."))
"""
(['DH', 'IH1', 'S', ' ', 'IH1', 'Z', ' ', 'G', 'R', 'EY1', 'T', ' ', '.'], 'this is great .')
"""

# Regular usage II
print(g2p("read"))
"""
(['R', 'IY1', 'D'], 'read')
"""

# Vocabulary usage
print(g2p("read", vocabulary=True, pos="VBD"))
"""
(['R', 'EH1', 'D'], 'read')
"""

# Vocabulary without pos specification results in ValueError
print(g2p("read", vocabulary=True))
"""
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
  File "/home/ponddy/virtualEnvs/g2p_test/lib/python3.6/site-packages/g2p_en/g2p.py", line 158, in __call__
    raise ValueError("pos argument is required for vocabulary input.")
ValueError: pos argument is required for vocabulary input.
"""

# Sentence with vocabulary == True and pos specification  results in ValueError
print(g2p("This is great.", vocabulary=True, pos='V'))
"""
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
  File "/home/ponddy/virtualEnvs/g2p_test/lib/python3.6/site-packages/g2p_en/g2p.py", line 175, in __call__
    raise ValueError("not vocabulary input!")
ValueError: not vocabulary input!
"""

```
