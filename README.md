# Python_Tips
Here i'm going to save good tips and tricks for python development
<hr>

## Example 1: How to return True.
<table>
  <thead><tr><th>❌</th><th>✔️</th></tr></thead>
  <tbody>
    <tr>
      <td><pre>def func(x: int):<br>    if x == 1:  # Or check other condition<br>        return True</pre></td>
      <td><pre>def func(x: int):<br>    return x == 1  # Or return other condition</pre></td>
    </tr>
  </tbody>
</table>
<hr>

## Example 2: How to set maximum (or minimum).
<table>
  <thead><tr><th>❌</th><th>✔️</th></tr></thead>
  <tbody>
    <tr>
      <td><pre>def upper_limit_3():<br>    x = int(input('x = '))<br>    if x > 3:<br>        x = 3<br>    return x</pre></td>
      <td><pre>def upper_limit_3():<br>    x = int(input('x = '))<br>retrun max(x, 3)</pre></td>
    </tr>
  </tbody>
</table>
