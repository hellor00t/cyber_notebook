---
description: Flask Snippets and Workflow
---

# flask

## Flask SQL Alchemy DB

### Flask SQL Alchemy DB Setup

```bash
$ flask db init
```

### Flask SQ Alchemy DB Models Update

```
$ flask db migrate -m "<message>"
$ flask db upgrade
```

### Flask Commit to SQL Alchemy DB

```bash
>> data = <DB Model Class>(<field>='<value>')
>>> db.session.add(data)
>>> db.session.commit()
```



