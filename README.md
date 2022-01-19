# Docker + ReactJS

## Docker Commands

### Docker Image

`docker build -t <image-name> .` <!--<.> is for current directory-->

### Docker Container

Run docker container \
`docker run -d -p 3000:3000 --name <container-name> <image-name>`

*Sync app folder with container app folder, using Volume:* \
`docker run -v <dirLocalDirectoryPath:containerDirectoryPath> -d -p 3000:3000 --name <container-name> <image-name>` \
*Sync app folder with container app folder, using Volume and readonly:* \
`docker run -v <dirLocalDirectoryPath:containerDirectoryPath:ro> -d -p 3000:3000 --name <container-name> <image-name>` \
*example using Powershell:* \
`docker run -v ${pwd}\src:/app/src -d -p 3000:3000 --name <container-name> <image-name>` \
*example using CMD:* \
`docker run -v %cd%\src:/app/src -d -p 3000:3000 --name <container-name> <image-name>` \
*example using Windows Environment:* \
- `docker run -v %cd%\src:/app/src -e CHOKIDAR_USEPOLLING=true -d -p 3000:3000 --name <container-name> <image-name>` \

- `docker run -v %cd%\src:/app/src -e CHOKIDAR_USEPOLLING=true -e REACT_APP_NAME=reactApp1 -d -p 3000:3000 --name <container-name> <image-name>` \

- Using an env file: `docker run -v %cd%\src:/app/src -env-file ./.env -d -p 3000:3000 --name <container-name> <image-name>` \

*example using Linux:* \
`docker run -v $(pwd)/src:/app/src -d -p 3000:3000 --name <container-name> <image-name>` \

Interact with container: \
`docker exec -it <container-name> bash`

## Create React App

This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

## Available Scripts

In the project directory, you can run:

### `npm start`

Runs the app in the development mode.\
Open [http://localhost:3000](http://localhost:3000) to view it in your browser.

The page will reload when you make changes.\
You may also see any lint errors in the console.

### `npm test`

Launches the test runner in the interactive watch mode.\
See the section about [running tests](https://facebook.github.io/create-react-app/docs/running-tests) for more information.

### `npm run build`

Builds the app for production to the `build` folder.\
It correctly bundles React in production mode and optimizes the build for the best performance.

The build is minified and the filenames include the hashes.\
Your app is ready to be deployed!

See the section about [deployment](https://facebook.github.io/create-react-app/docs/deployment) for more information.

### `npm run eject`

**Note: this is a one-way operation. Once you `eject`, you can't go back!**

If you aren't satisfied with the build tool and configuration choices, you can `eject` at any time. This command will remove the single build dependency from your project.

Instead, it will copy all the configuration files and the transitive dependencies (webpack, Babel, ESLint, etc) right into your project so you have full control over them. All of the commands except `eject` will still work, but they will point to the copied scripts so you can tweak them. At this point you're on your own.

You don't have to ever use `eject`. The curated feature set is suitable for small and middle deployments, and you shouldn't feel obligated to use this feature. However we understand that this tool wouldn't be useful if you couldn't customize it when you are ready for it.
