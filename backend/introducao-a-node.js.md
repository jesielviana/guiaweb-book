---
description: Em construção...
---

# Introdução a Node.js

 Node.js não é uma linguagem de programação, tampouco um framework. A definição mais apropriada seria: um ambiente de runtime para Javascript que roda em cima de uma engine conhecida como Google v8.  [Waldemar Neto](https://leanpub.com/construindo-apis-testaveis-com-nodejs)

 [Node.js®](https://nodejs.org/) is a JavaScript runtime built on Chrome's V8 JavaScript engine. 

Em construção...

```javascript
const express = require('express')
const app = express()
const port = 3000

app.get('/', (req, res) => {
  res.send('Hello World!')
})

app.listen(port, () => {
  console.log(`Example app listening at http://localhost:${port}`)
})
```

