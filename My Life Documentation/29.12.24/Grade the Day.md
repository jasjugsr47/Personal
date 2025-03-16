```dataview
table Name, Number as "Number Input", 
case
  Number < 40  => "U",
  Number < 45  => "E-",
  Number < 50  => "E",
  Number < 55  => "D-",
  Number < 60  => "D",
  Number < 65  => "C-",
  Number < 70  => "C",
  Number < 75  => "B-",
  Number < 80  => "B",
  Number < 85  => "A-",
  Number < 90  => "A",
  Number < 95  => "A*",
  Number <= 100 => "A**"
as Grade
from "folder/your-folder-name"
