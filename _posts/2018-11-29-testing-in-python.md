---
layout: post
title: "Testing in Python"
tags: [ software ]
description: "Comparison of unittest and pytest."
---

Up until now, I've predominately used Python as a scripting and utility language.  My current reading topics include how to structure python projects, ensure that they're self contained (refuse to add the project filepath to the system PATH), add testing, refresher on coding standards and conventions, etc.

So obviously the big question is what do you use for tests?  To help decide, I put together a simple demo project to play with unittest and pytest.

The demo project is structured as follows:
```
\test_project
  demo.py
  test\
    test_demo.py
    run_all_tests.py*
```


**demo.py**

```
def demoFunction():
  return 'test'
```

### unittest

Unittest is Python's built in testing library.  It gives the user more control over the types of asserts, but does require additional setup to implement tests.

```
import unittest
from demo import *

class TestDemo(unittest.TestCase):
  def testDemo(self):
    """The demo function returns a string"""
    self.assertEquals(demoFunction(), "test")

if __name__ == '__main__':
  unittest.main()
```

*Since my project will contain a number of test files/functions, I added a simple test runner to the test directory.
```
# run_all_tests 
import unittest

# reference the parent directory
import sys
sys.path.append("../")

# discover all tests located within the current directory
loader = unittest.TestLoader()
start_dir = '.'
suite = loader.discover(start_dir)

# execute all tests
runner = unittest.TextTestRunner()
runner.run(suite)
```

### pytest

Pytest is a popular alternative that removes a lot of boiler plate code and uses 'magic' behind the scenes to search and interpret the tests.

```
# reference the parent directory
import sys
sys.path.append("../")

import pytest
from demo import *

def test_demo():
  assert demoFunction() == "test"
```

### Decisions, Decisions

The sample code above demonstrates the simplicity of adding a new test in pytest, but there may be edge cases where its interpretation and execution cause issues.  Unittest's explicivity requires more effort to add a new test, but may allow the user to better define complex tests and prevent conflicts.

Since I'm attempting to add coverage and require tests going forward, I'll start with pytest.  Time will tell if any issues arise.
