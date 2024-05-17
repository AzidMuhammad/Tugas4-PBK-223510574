# Vue Component Communication Example

This project demonstrates communication between parent, child, and grandchild components in a Vue.js application. It includes modal functionality to display child and grandchild components.

## Project Structure

- `App.vue`: The root component that contains the `ParentComponent`.
- `ParentComponent.vue`: The parent component that can display the `ChildComponent` in a modal.
- `ChildComponent.vue`: The child component that can display the `GrandchildComponent` in a modal and send messages to the parent component.
- `GrandchildComponent.vue`: The grandchild component that sends messages to the child component.
- `Modal.vue`: A reusable modal component used to display the child and grandchild components.

## Features

- **Parent-Child Communication:** The child component sends messages to the parent component.
- **Child-Grandchild Communication:** The grandchild component sends messages to the child component.
- **Modal Dialogs:** Child and grandchild components are displayed in modals.

## Installation

1. Clone the repository:
    ```bash
    git clone https://github.com/your-username/vue-component-communication.git
    cd vue-component-communication
    ```

2. Install the dependencies:
    ```bash
    npm install
    ```

3. Start the development server:
    ```bash
    npm run serve
    ```

## Usage

1. **Parent Component:**
    - Displays a message and a button to open the child component in a modal.
    - Updates the message when receiving an event from the child component.

2. **Child Component:**
    - Displays a message and a button to open the grandchild component in a modal.
    - Sends a message to the parent component via an event.
    - Updates the parent's message when receiving an event from the grandchild component.

3. **Grandchild Component:**
    - Displays a message.
    - Sends a message to the child component via an event.
