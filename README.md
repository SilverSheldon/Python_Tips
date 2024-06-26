# Python_Tips
Here i'm going to save good tips and tricks for python development
<hr>

## Example 1: How to return True/False.
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

## Example 3: How to check all conditons.
<table>
  <thead><tr><th>❌</th><th>✔️</th></tr></thead>
  <tbody>
    <tr>
      <td>
        <pre class="python">
from datetime import time<br>
def can_buy_alco(age, money, time_of_purchase: time):
    if age >= 18 and money > 100 and time_of_purchase <= time(22):
        return 'You can buy alco'
    return 'You can't buy alco'<br>
print(can_buy_alco(19, 105, time(19, 15)))</pre></td>
      <td>
        <pre class="python">
from datetime import time<br>
def can_buy_alco(age, money, time_of_purchase: time):
    conditions = (
        age >= 18,
        money > 100,
        time_of_purchase <= time(22)
    )
    if all(conditions):
        return 'You can buy alco'
    return 'You can't buy alco'<br>
print(can_buy_alco(15, 105, time(23, 15)))</pre></td></tr></tbody></table>
<hr>

## Example 4: How to check any conditon (at least one of them).
<table>
  <thead><tr><th>❌</th><th>✔️</th></tr></thead>
  <tbody>
    <tr>
      <td>
        <pre class="python">
def can_delete_user(user_id: int):
    ADMINS = [...]
    MODERATORS = [...]
    if user_id in ADMINS or user_id in MODERATORS:
        return 'You can delete user'
    return 'You can't delete user'<br>
print(can_delete_user(user_id=1234))</pre></td>
      <td>
        <pre class="python">
def can_delete_user(user_id: int):
    ADMINS = [...]
    MODERATORS = [...]
    conditions = [
        user_id in ADMINS,
        user_id in MODERATORS,
    ]
    if any(conditions):
        return 'You can delete user'
    return 'You can't delete user'<br>
print(can_delete_user(user_id=1234))</pre></td></tr></tbody>
</table>
<hr>

## Example 5: How to generate list *with integer numbers*.
<table>
  <thead><tr><th>❌</th><th>✔️</th></tr></thead>
  <tbody>
    <tr>
      <td>
        <pre class="python">
lst = [] 
for i in range(10):
    lst.append(i)</pre>
Or:<br>
        <pre class="python">lst = [i for i in range(10)]</pre></td>
      <td>
        <pre class="python">lst = list(range(10))</pre></td></tr></tbody>
</table>
<hr>

## Example 6: How to work with power of two.
(sometimes it's useful to remember about bitwise operations)

<table>
  <thead><tr><th>❌</th><th>✔️</th></tr></thead>
  <tbody>
    <tr>
      <td>
        <pre class="python">
def is_binary(n):
    if n == 1:
        return True
    elif n <= 0:
        return False
    else:
        if n % 2 != 0:
            return False
        else:
            return is_binary(n // 2)</pre></td>
      <td>
        <pre class="python">
def is_binary(n):
    return n & (n - 1) == 0</pre></td></tr></tbody>
</table>
<hr>

## Example 7: How to orginize a lot of similar conditions.

<table>
  <thead><tr><th>❌</th><th>✔️</th></tr></thead>
  <tbody>
    <tr>
      <td>
        <pre class="python">
def colorize_text(text, color=None):
    if color == 'red':
        return f"\033[31m{text}\033[m"
    elif color == 'green':
        return f"\033[32m{text}\033[m"
    elif color == 'yellow':
        return f"\033[33m{text}\033[m"
    else:
        return text</pre>
Or:<br>
        <pre class="python">
def colorize_text(text, color=None):
    match color:
        case 'red':
            return f"\033[31m{text}\033[m"
        case 'green':
            return f"\033[32m{text}\033[m"
        case 'yellow':
            return f"\033[33m{text}\033[m"
    return text</pre></td>
      <td>
        <pre class="python">
def colorize_text(text, color=None):
    colors = {
        'red': "\033[31m",
        'green': "\033[32m",
        'yellow': "\033[33m",
    }
    return f"{colors.get(color, '')}{text}\033[m"</pre></td></tr></tbody>
</table>
<hr>

## Example 8: How to make `while` shorter.
(sometimes it's useful to remember about valrus operator)

<table>
  <thead><tr><th>❌</th><th>✔️</th></tr></thead>
  <tbody>
    <tr>
      <td>
        <pre class="python">
s = input("Enter smth: ")
while s != "":
    print(s.upper())
    s = input("Enter smth: ")</pre></td>
      <td>
        <pre class="python">
while (s := input("Enter smth: ")) != "":
    print(s.upper())</pre></td></tr></tbody>
</table>