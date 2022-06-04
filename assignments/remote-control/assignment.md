# Assignment: Websocket Remote Control

## Description

Your task is to implement remote control backend using `RobotJS` library and websocket.

The backend should be able to do the following:

- Start websocket server
- Handle websocket connection
- Move mouse (Up, Down, Left, Right)
- Draw circle, rectangle and square  
- Send current mouse coordinates
- Send desktop capture

## Technical requirements

- Task can be implemented on Javascript or Typescript
- Use 16 LTS version of Node.js
- Only [ws](https://www.npmjs.com/package/ws), [robotjs](https://www.npmjs.com/package/robotjs), `cross-env`, `typescript`, `ts-node`, `eslint` and its plugins, `webpack` and its plugins, `prettier`, `@types/*` are allowed
- The program is started by npm script `start` in following way:
```bash
npm run start 
```
- After starting the program displays websocket parameters
- After program work finished the program should end websocket work correctly  
- After each received command program should display the command and result
- All commands should be ended with **\0**

List of websocket commands and their syntax (<- - cmd from frontend, -> - answer):
- Navigation over the x and y axis
    - Move mouse up
    ```bash
    <- mouse_up {y px}
    ```
    - Move mouse down
    ```bash
    <- mouse_down {y px}
    ```
    - Move mouse left
    ```bash
    <- mouse_left {x px}
    ```
    - Move mouse right
    ```bash
    <- mouse_right {x px}
    ```
    - Send mouse coordinates
    ```bash
    <- mouse_coord
    -> mouse coord {x px} {y px}
    ```
- Drawing
    - Draw circle with pushed left button: 
    ```bash
    <- draw_circle {px}
    ```
    - Draw rectangle with pushed left button: 
    ```bash
    <- draw_rectangle {px} {px}
    ```
    - Draw square with pushed left button: 
    ```bash
    <- draw_square {px}
    ```
- Print screen
    - Make print screen command and send image:
    ```bash
    <- prnt_scrn
    -> prnt scrn {bitmap buf}
    ```
    