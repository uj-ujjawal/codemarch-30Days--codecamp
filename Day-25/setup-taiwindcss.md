# How to setup tailwindcss

## requirement

- node-js : to install tailwind nodejs is required.
  - to check node js is installed or not: go to terminal/cmd and type: node -v
  - if it display the version of node js then it's installed otherwise have to install it.

## Next to setup tailwind

- open the your project directory in terminal and follow the following command

  ```js
  npm init -y //to initialize npm and create package.json file
  ```

  ```js
  npm install tailwindcss  //to install tailwindcss in our project
  ```

  ```js
  npx tailwindcss init //to create **tailwind.config.js** file
  ```

- create a **src** directory
  - in this dir,
    - create a file called **input.css** (we can use any name we want)
    - create a .html file in the same directory in which we will write our html coed.
    - we have to update path in **tailwind.config.js** file under `content=[]` so it can find where html and js file so it can work and apply tailwind properties on it.
  - let's suppose we will keep all *html* and *js* file in **src** dir then,
    - to update  goto **inside tailwind.config.js**  update `content=[]` to `content=[".\src\**\*.{html,js}"]`
  
  - now import tailwindcss into our **input.css** file

    ```css
    @tailwind base;
    @tailwind components;
    @tailwind utilities;
    ```

- now we are ready to run it.
- type the following command and tailwind css will start.

  ```js
  npx tailwindcss -i ./src/input.css -o ./dist/output.css --watch
  ```

- this is optional --  to not write that long command again and again to run tailwindcss
  - goto **package.json** file under `script` tag add one more line

  ```json
  "build:tailwindcss":npx tailwindcss -i ./src/input.css -o ./dist/output.css --watch
  ```
  
- now we can run it by simply typing `npm run build:tailwindcss`
