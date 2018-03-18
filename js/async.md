// app.js
```js
const http = new EasyHTTP;

// get user
http.get('https://jsonplaceholder.typicode.com/users')
  .then(data => console.log(data))
  .catch(err => console.log(err));

const user = {
  name: 'ohda',
  username: 'yogicat',
  email: 'ohdayoda@gmail.com'
}

http.post('https://jsonplaceholder.typicode.com/users', user)
  .then(data => console.log(data))
  .catch(err => console.log(err));


http.put('https://jsonplaceholder.typicode.com/users/2', user)
  .then(data => console.log(data))
  .catch(err => console.log(err));

http.delete('https://jsonplaceholder.typicode.com/users/2')
  .then(data => console.log(data))
  .catch(err => console.log(err));
```

---

// easyhttp library
```js
class EasyHTTP {
  // make an http get req
  get(url) {
    return new Promise((resolve, reject) => {
      fetch(url)
        .then(res => res.json())
        .then(data => resolve(data))
        .catch(err => reject(err));
    })
  }

  // post req
  post(url, data) {
    return new Promise((resolve, reject) => {
      fetch(url, {
        method: 'POST',
        headers: {
          'Content-type': 'application/json'
        },
        body: JSON.stringify(data)
      })
        .then(res => res.json())
        .then(data => resolve(data))
        .catch(err => reject(err));
    })
  }
  // put req
  put(url, data) {
    return new Promise((resolve, reject) => {
      fetch(url, {
        method: 'PUT',
        headers: {
          'Content-type': 'application/json'
        },
        body: JSON.stringify(data)
      })
        .then(res => res.json())
        .then(data => resolve(data))
        .catch(err => reject(err));
    })
  }

  // delete req
  delete(url) {
    return new Promise((resolve, reject) => {
      fetch(url, {
        method: 'DELETE',
        headers: {
          'Content-type': 'application/json'
        }
      })
        .then(res => res.json())
        .then(data => resolve('data deleted'))
        .catch(err => reject(err));
    })
  }
}
```