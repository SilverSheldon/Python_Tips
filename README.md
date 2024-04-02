# Python_Tips
Here i'm going to save good tips and tricks for python development
<hr>

## Example 1: How to return True.
<table>
  <thead><tr><th>❌</th><th>✔️</th></tr></thead>
  <tbody>
    <tr>
      <td><pre class="python">def is_one(x: int):<br>    if x == 1:  # Or check other condition<br>        return True</pre></td>
      <td><pre class="python">def is_one(x: int):<br>    return x == 1  # Or return other condition</pre></td>
    </tr>
  </tbody>
</table>
<hr>

## Example 2: How to set maximum (or minimum).
<table>
  <thead><tr><th>❌</th><th>✔️</th></tr></thead>
  <tbody>
    <tr>
      <td><pre class="python">def upper_limit_3():<br>    x = int(input('x = '))<br>    if x > 3:<br>        x = 3<br>    return x</pre></td>
      <td><pre class="python">def upper_limit_3():<br>    x = int(input('x = '))<br>    retrun min(x, 3)</pre></td>
    </tr>
  </tbody>
</table>
<hr>

## Example 3: How to evaluate against any conditon.
<table>
  <thead><tr><th>❌</th><th>✔️</th></tr></thead>
  <tbody>
    <tr>
      <td>
```python
from datetime import time
def can_buy_alco(age: int, money: float, time_of_purchase: time):
    if age >= 18 and money > 100 and time_of_purchase <= time(22):
        return True
    return False
print(can_buy_alco(19, 105, time(19, 15)))  # returns True
```
      </td>
      <td>
```python
from datetime import time
def can_buy_alco(age: int, money: float, time_of_purchase: time):
    conditions = [
        age >= 18,
        money > 100,
        time_of_purchase <= time(22)
    ]
    if all(conditions):
        return True
    return False
print(can_buy_alco(15, 105, time(23, 15)))
```
      </td>
    </tr>
  </tbody>
</table>
