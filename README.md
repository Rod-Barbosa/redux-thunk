This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

## Project
![Screenshot1](https://res.cloudinary.com/dxrbrkfvv/image/upload/v1598551949/github/redux-thunk_ddle7d.png)


### Thunk & Redux

This is the meat and potatoes of this project. using Axios to Create, Update and Delete posts from JSON Placeholder API

```
export const getPosts = () => async dispatch =>{
  const result = await axios.get(`https://jsonplaceholder.typicode.com/posts`)
  dispatch({
    type: GET_POSTS,
    payload: result.data
  })
}


// get a post
export const getPost = (id) => async dispatch =>{
  const result = await axios.get(`https://jsonplaceholder.typicode.com/posts/${id}`)
  dispatch({
    type: GET_POST,
    payload: result.data,
  })
};

// create a post
export const createPost = (post) => async dispatch =>{
  const result = await axios.post(`https://jsonplaceholder.typicode.com/posts`,
  post)
  dispatch({
    type: CREATE_POST,
    payload: result.data
  });
}

// update a post
export const updatePost = (post) => async dispatch =>{
  const result = await axios.put(`https://jsonplaceholder.typicode.com/posts/${post.id}`,
post)
  dispatch({
    type: UPDATE_POST,
    payload: result.data,
  })
}

// delete a post
export const deletePost = (id) => async dispatch =>{
  
  await axios.delete(`https://jsonplaceholder.typicode.com/posts/${id}`)
  
  dispatch({
    type: DELETE_POST,
    payload: id,
  })
};
```

Async dispatch might not look that intuitive, but once you get it... it is just a matter of repeating it over and over
