# Python_Tips
Here i'm going to save good tips and tricks for python development
<hr>

## Example 1: How to return True.
<table>
  <thead><tr><th>❌</th><th>✔️</th></tr></thead>
  <tbody>
    <tr>
      <td><pre><code class="python">def is_one(x: int):<br>    if x == 1:  # Or check other condition<br>        return True</code></pre></td>
      <td><pre><code class="python">def is_one(x: int):<br>    return x == 1  # Or return other condition</code></pre></td>
    </tr>
  </tbody>
</table>
<hr>

## Example 2: How to set maximum (or minimum).
<table>
  <thead><tr><th>❌</th><th>✔️</th></tr></thead>
  <tbody>
    <tr>
      <td><pre><code class="python">def upper_limit_3():<br>    x = int(input('x = '))<br>    if x > 3:<br>        x = 3<br>    return x</code></pre></td>
      <td><pre><code class="python">def upper_limit_3():<br>    x = int(input('x = '))<br>    retrun min(x, 3)</code></pre></td>
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
        <pre>
          <code class="python">
            from datetime import time<br>
            def can_buy_alco(age: int, money: float, time_of_purchase: time):<br>
                if age >= 18 and money > 100 and time_of_purchase <= time(22):<br>
                    return True<br>
                return False<br>
            print(can_buy_alco(19, 105, time(19, 15)))  # returns True
          </code>
        </pre>
      </td>
      <td>
        <pre>
          <code class="python">
            from datetime import time<br>
            def can_buy_alco(age: int, money: float, time_of_purchase: time):<br>
                conditions = [<br>
                    age >= 18,<br>
                    money > 100,<br>
                    time_of_purchase <= time(22)<br>
                ]<br>
                if all(conditions):<br>
                    return True<br>
                return False<br>
            print(can_buy_alco(15, 105, time(23, 15)))
          </code>
        </pre>
      </td>
    </tr>
  </tbody>
</table>
