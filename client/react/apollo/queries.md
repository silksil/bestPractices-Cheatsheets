You can query like this:
```js
{
  company(id:"1"){
    id
    name
    description
  }
}
```

It is not necessary, but you can name the query:
```js
query findCompany{
  company(id:"1"){
    id
    name
    description
  }
}
```

If you use a query name twice, you have the name the result if it comes back. It is not necessary, to name both.
```js
{
  apple: company(id:"1"){
    id
    name
    description
  },
  google: company(id:"1"){
    id
    name
    description
  }
}
```
### Query Fragment
If you duplicate certain properties you can define a query fragment:

```js
fragment companyDetails on Company {
  id
  name
  Namedescription
}
```

Then, include it in the query:
```js
{
  apple: company(id:"1"){
    ...companyDetails
  },
  google: company(id:"1"){
    ...companyDetails
  }
}

### Query Reruns? Update all components with it
You relate a query to a component, all components related to that query will be re-rendered.
