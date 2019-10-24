### xlsxwriter
---
https://github.com/jmcnamara/XlsxWriter

https://xlsxwriter.readthedocs.io/

```py
// xlsxwriter/test/excel_comparsion_test.py
import unittest
import os
from .helperfunctions import _compare_xlsx_files

class ExcelComparisonTest(unittest.TestCase):
  
  def set_filename(self, filename):
    self.maxDiff = None
    self.got_filename = ''
    self.exp_filename = ''
    self.ignore_files = []
    self.ignore_elements = {}
    self.ignore_elements = {}
    self.test_dir = 'xlsxwriter/test/comparison/'
    self.vba_dir = self.test_dir + 'xlsx_files/'
    self.image_dir = self.test_dir + 'images/'

    self.exp_filename = self.test_dir + 'xlsx_files/' + filename
    
    self.got_filename = self.test_dir + '_test_' + filename
    
  def set_text_fiel(self, filename):
    self.txt_filename = self.test_dir + 'xlsx_files/' + filename
  
  def assertExcelEqual(self):
    got, exp = _compare_xlsx_files(self.got_filename,
        self.exp_filename,
        self.ignore_files,
        self.ignore_elements)
    
    self.assertEqual(exp, got)
  
  def tearDown(self):
    if os.path.exists(self.got_filename):
      os.remove(self.got_filename)
```

```
```

```
```


