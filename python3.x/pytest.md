## PyTest
> Some tips after working with pytest

#### Weird shit

* When you have few `autouse=True****` fixtures they runned in alphabetic ordering.

    If two fixture with SAME SCOPE marked as autoused ordering will be alphabetic cuz internally pytest calls `dir` that will shuffle output in such order

    https://github.com/pytest-dev/pytest/blob/master/_pytest/fixtures.py#L1085-L1127
