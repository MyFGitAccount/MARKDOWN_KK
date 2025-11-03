# Login process flow chart:

```flow
st=>start: User Login
e=>end: Login success
op1=>operation: Require user to enter username
op2=>operation: Require user to enter password
cond1=>condition: Is first time user?
op3=>operation: Let user enter new username
op4=>operation: Let user enter new password

st->op1->op2->cond1
cond1(yes)->op3->op4->e
cond1(no)->e
```

