# Python_Tips
Here i'm going to save good tips and tricks for python development

> Example 1: How to return True.

<table>
  <caption>
    Don't repeat yourself (DRY)
  </caption>
  <thead>
    <tr>
      <th>❌</th>
      <th>✔️</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>
        ```python
        def func(x: int):
            if x == 1:  # Or check other condition
            return True
        ```
      </td>
      <td>
        ```python
        def func(x: int):
            return x == 1  # Or return other condition
        ```
      </td>
    </tr>
  </tbody>
</table>
