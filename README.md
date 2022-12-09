# Guidelines

This repo contains my personal contributing guidelines.

---

## General Guidelines

* **Use** semantic versioning - `MAJOR.MINOR.PATCH` - [https://semver.org](https://semver.org)
* **Use** `.gitignore`s to only push to repositories what can't be automatically generated

---

## Git Commits

Commits should be prefixed with what they change in the project. Present tense should be used within commit messages. 
</br>
`fix: ` for fixes & patches
</br>
`add: ` for commits that add features
</br>
`update: ` for commits that change a feature already present
</br>
`i18n: ` for commits that add or change the localization
</br>
`docs: ` for commits that add or change the documentation
</br>
`build: ` for commits that build a new release or change building scripts
</br>
`test: ` for commits that add or change tests
</br>
`move: ` for commits that move files and change their in-project paths
</br>
`del: ` for commits that remove features
</br>
`style: ` for commits that fix formatting
</br>
`git: ` for git-related commits

---

## General Syntax Standards

* Opening brackets **should** be inline with their opening statement.
* **Use** "" (double quotes) to wrap strings and '' (single quotes) for strings inside them.
* Files **should** be structured like this:
  - general imports
  - application specific imports
  - class definitions
  - main function
  - additional functions
* **Use** spaces between arguments in functions
* **Use** spaces between arguments in expressions
* **Use** camelCase for function names
* **Use** CapitalizedCamelCase for class names

---

## Language-Specific Syntax Standards

#### Dart
```dart
// Comment
class Example {
  var x = 0;
  var y = 0;
  // constructor
  Example(this.x, this.y);
}

void main() {
  var b = true; // bool
  var s = "Moraczanin"; // str (String)
  var i = 1; // int
  var ii = 3.14; // double
  var e = i + ii; // expression
  var l = [ i, ii ]; // list
  var ll = [
    b,
    s,
    i,
    ii,
    e
  ]; // long list
  var d = {
    "key1": "value1",
    "key2": "value2"
  }; // dict (Map)

  delayedPrint("d's key1 value equals ${d['key1']}");
  
  var example = Example(1, 1);
  
  // cfs if-elif-else
  if (example.x != 0 && example.y != 0) {
    print("Example isn't (0,0)");
  } else if (example.x == 0) {
    print("Example is (0,y)");
  } else {
    print("Example is unknown");
  }

  // cfs for
  for (i; i < 5; i++) {
    print("Counting... $i");
  }
  
  // cfs while
  while (i <= 10) {
    print("Counting... $i");
    i += 1;
  }
  
  print("Example's x equals ${example.x}, and y equals ${example.y}");
}

Future<void> delayedPrint(message) async {
  await Future.delayed(
    Duration(seconds: 1)
  );
  print(message);
}
```

#### Python
```python
# Comment
import asyncio

class Example:
    # constructor
    def __init__(self, x = 0, y = 0):
        self.x = x
        self.y = y
        
async def main():
    b = True # bool
    s = "Moraczanin" # str
    i = 1 # int
    ii = 3.14 # float
    e = i + ii # expression
    l = [ i, ii ] # list
    ll = [
        b,
        s,
        i,
        ii,
        e
    ] # long list
    d = {
        "key1": "value1",
        "key2": "value2"
    } # dict
    
    await delayedPrint(f"d's key1 equals {d['key1']}")
    
    example = Example(1, 1)
    
    # cfs if-elif-else
    if (example.x != 0) and (example.y != 0):
        print("Example isn't (0,0)")
    elif example.x == 0:
        print("Example is (0,y)")
    else:
        print("Example is unknown")
        
    # cfs for
    for i in range(2, 5):
        print(f"Counting... {i - 1}")
        
    # cfs while
    while i <= 10:
        print(f"Counting... {i}")
        i += 1
        
    print(f"Example's x equals {example.x}, and y equals {example.y}")
    
async def delayedPrint(message):
    await asyncio.sleep(1)
    print(message)
    
if __name__ == "__main__":
    asyncio.run(main())
```
