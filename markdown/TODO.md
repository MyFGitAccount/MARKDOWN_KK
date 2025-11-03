# Login process flow chart:

```markdown
```flow
st=>start: Login
op=>operation: Enter credentials
cond=>condition: Valid?
e=>end: Success

st->op->cond
cond(yes)->e
cond(no)->op
