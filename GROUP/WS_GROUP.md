
---

## WebSocket Chat Handler

This WebSocket handler manages WebSocket connections for chat functionality.

### Request

- **URL:** ws:.../ws/chat/{GroupID}
- **Headers:**
    - Authorization: Bearer {token}

### Messages

- **Type:** message
    - **Payload:**
      ```json
      {
        "type": "message",
        "text": "Hello, world!",
        "parentMessage": "123"
      }
      ```
    - **Description:** Sends a message to the chat. Can include a parent message ID for replies.

- **Type:** reaction
    - **Payload:**
      ```json
      {
        "type": "reaction",
        "operation": "add",
        "emoji": "👍",
        "messageID": "456"
      }
      ```
    - **Description:** Adds a reaction to a message.

- **Type:** reaction
    - **Payload:**
      ```json
      {
        "type": "reaction",
        "operation": "remove",
        "reactionID": "789"
      }
      ```
    - **Description:** Removes a reaction from a message.

### Response

- **Type:** message
    - **Payload:**
```json
      {
      "id": 6,
      "user_id": "02cc50b8-748a-45bf-9f82-b87e9b5b52dd",
      "chat_id": 1,
      "parent_message_id": 2,
      "parent_message": {
          "ID": 2,
          "username": "asdfghj",
          "text": "dfghjkjk"
      },
  "text": "dfghjkjk",
  "reaction": [
  {
  "ID": 3,
  "Emoji": "dfghjkjk",
  "UserID": "02cc50b8-748a-45bf-9f82-b87e9b5b52dd",
  "MessageID": 6,
  "username": "Admin",
  "CreatedAt": "2024-02-27T23:36:37.925668+06:00",
  "UpdatedAt": "2024-02-27T23:36:37.925668+06:00"
  }
  ],
  "read": true,
  "username": "asdfghj",
  "created_at": "2024-02-27T23:36:10.807255+06:00",
  "updated_at": "2024-02-28T12:08:27.349750307+06:00"
}

 ```



