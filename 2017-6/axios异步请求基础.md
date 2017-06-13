# axios

标签（空格分隔）： JS

---
- GET请求

```
//通过给定的ID来发送请求
axios.get('/user?ID=12345')
  .then(function(response){
    console.log(response);
  })
  .catch(function(err){
    console.log(err);
  });
 
 
//以上请求也可以通过这种方式来发送
axios.get('/user',{
  params:{
    ID:12345
  }
})
.then(function(response){
  console.log(response);
})
.catch(function(err){
  console.log(err);
});
```
- POST请求

```
axios.post('/user',{
  firstName:'Fred',
  lastName:'Flintstone'
})
.then(function(res){
  console.log(res);
})
.catch(function(err){
  console.log(err);
});
```

- 一次发送多个请求

```
axios.all([
      axios.get("url1"),
      axios.get("url2"),
      axios.get("url3"),
      axios.get("url999")
  ]).then(axios.spread(function(res1,res2,res3,res999){   
      console.log(res1.data);
      console.log(res2.data);
      console.log(res3.data);
      console.log(res4.data);
    }))
```

- json数据POST请求



```
数据格式
{page:1,city:["郑州","北京"]}

axios.post(url, json).then(response => response.data)
  .then(data => {
    console.log(data);
  });
 
```

- 返回内容

```
{
  data:{},
  status:200,
  //从服务器返回的http状态文本
  statusText:'OK',
  //响应头信息
  headers: {},
  //`config`是在请求的时候的一些配置信息
  config: {}
}

获取响应数据
axios.get('/user/12345')
then(function(res){
  console.log(res.data);
  console.log(res.status);
  console.log(res.statusText);
  console.log(res.headers);
  console.log(res.config);
})
```




