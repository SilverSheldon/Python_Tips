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

## Example 3: How to check all conditon.
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
print(can_buy_alco(19, 105, time(19, 15)))
        </pre>
      </td>
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
print(can_buy_alco(15, 105, time(23, 15)))  # False
        </pre>
      </td>
    </tr>
  </tbody>
</table>
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
print(can_delete_user(user_id=1234))
        </pre>
      </td>
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
print(can_delete_user(user_id=1234))
        </pre>
      </td>
    </tr>
  </tbody>
</table>
