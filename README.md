<h3 align="center">
  Learning Node.js Concepts
</h3>

<p align="center">
  <a href="https://github.com/wesleyasilva">
    <img alt="Make by Wesley Adam" src="https://img.shields.io/badge/make%20by-Wesley%20Adam-%2304D361">
  </a>

  <img alt="License" src="https://img.shields.io/badge/license-MIT-%2304D361">

  <a href="https://github.com/wesleyasilva?tab=stars">
    <img alt="Stargazers" src="https://img.shields.io/github/stars/wesleyasilva/Learning-Node.js-Concepts?style=social">
  </a>
</p>

<p align="center">
  <a href="#about">About</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#license">License</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#getting-started">Getting Started</a>
</p>

## About

This is an application to store portfolio repositories, which allows the creation, listing, updating and removal of repositories, and also allows the repositories to receive "likes".

### Application Rotes

In the project template, the app.js file has the following routes to achieve the respective goals:

- **`POST /repositories`**: The route must receive `title`, `url` and `techs` inside the request body, the URL being the link to the github of that repository. When registering a new project, it must be stored inside an object in the following format: `{ id: "uuid", title: 'Learn Node.js', url: 'http://github.com/...' , techs: ["Node.js", "..."], likes: 0 }`; Make sure the ID is a UUID, and always start likes as 0;

- **`GET /repositories`**: Route to list all repositories;

- **`PUT /repositories/:id`**: The route should only change the `title`, `url` and `techs` of the repository that have the `id` equal to the `id` present in the route parameters;

- **`DELETE /repositories/:id`**: The route must delete the repository with the `id` present in the route parameters;

- **`POST /repositories/:id/like`**: The route must increase the number of likes from the specific repository chosen through the `id` present in the route parameters, at each call of this route, the number of likes must be increased by 1;

### Test Especifications

Each test, there is a brief description of what the application must meet in order to pass the tests:

- **`should be able to create a new repository`**: For this test to pass, the application must allow a repository to be created, and return a json with the created project;

- **`should be able to list the repositories`**: For this test to pass, the application must allow an array with all the repositories that have been created so far to be returned;

- **`should be able to update repository`**: For this test to pass, the application must allow changing only the `url`, `title` and `techs` fields;

- **`should not be able to update a repository that does not exist`**: For this test to pass, the application must validate in the update route whether the repository id sent by url exists or not. Otherwise, return an error with status `400`;

- **`should not be able to update repository likes manually`**: For this test to pass, the update route is not allowed to directly change the likes of this repository, keeping the same number of likes as the repository already had before the update. This is because the only place that should update this information is the route responsible for increasing the number of likes;

- **`should be able to delete the repository`**: For this test to pass, the application must allow the delete route to delete a project, and when doing the deletion, return an empty response, with status `204`;

- **`should not be able to delete a repository that does not exist`**: For this test to pass, the application validate in the delete route if the repository id sent by url exists or not. If not, return an error with status `400`;

- **`should be able to give a like to the repository`**: For this test to pass, the application must allow a repository with the given id to receive likes. The likes value must be incremented by 1 at each request, and as a result, return a json containing the repository with the updated number of likes;

- **`should not be able to like a repository that does not exist`**: For this test to pass, the application must validate in the like route if the repository id sent by the url exists or not. If not, return an error with status `400`;

## Getting Started

To test this application, you must have **<a href="https://yarnpkg.com/getting-started">yarn package</a>** installed on your computer and enjoy.

**Start the project and download its dependencies**

```
yarn init -y

```

**Running Test**

```
yarn test

```

## License

This project is under the MIT license
