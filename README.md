## Before adding the print statement outside spawner.spawn()
![Screenshot](https://github.com/user-attachments/assets/8feddf1d-d868-49f5-80b0-721da72aebd7)

## After adding the print statement outside spawner.spawn()

![Screenshot](https://github.com/user-attachments/assets/ed25e04f-27e5-4778-a678-785990dd1102)

This happens because spawner.spawn(...) schedules the task, but it doesn't run it immediately.
The 3rd print statement runs right after, and it will execute it synchronously. 

## After removing drop(spawner);

![Screenshot](https://github.com/user-attachments/assets/a349ddd9-9414-417b-99a2-23203bead865)

## After adding multiple spawners
![Screenshot](https://github.com/user-attachments/assets/1e989c8c-18d8-4337-aa7a-dedce855d9f9)

After commenting out `drop(spawner);` , it is telling the executor that no more tasks are coming. And because
it's using synchronous channel, the executor's loop will wait forever on `.recv()`