## Before adding the print statement outside spawner.spawn()
![Screenshot](https://github.com/user-attachments/assets/8feddf1d-d868-49f5-80b0-721da72aebd7)

## After adding the print statement outside spawner.spawn()

![Screenshot](https://github.com/user-attachments/assets/ed25e04f-27e5-4778-a678-785990dd1102)

This happens because spawner.spawn(...) schedules the task, but it doesn't run it immediately.
The 3rd print statement runs right after, and it will execute it synchronously. 