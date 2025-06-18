## ***L2 Task summary ***

1.Compare:
2.Files Changed.
3.History.
4.Blame.
5.Commits

1.File:app/api/chat/route.ts

Summary:

1.Cleanup Error Response handling:
- Rewrote the return statement to for invalid id in a readable format using better Typescript aligment.
2.Added onFinish() Function:
- marks the responseComplete status true and then and closes the mcp client connections
3.Removed Chat creation and Storage logic.

Reason for change:
-Improves the readiblity of the code and helps in better understanding of the code.
-Avoids hanging connections after chat completion.

Type of change:
1.Refactoring 
2.Bug fixing/improvement.

2.File:app/action.ts

Summary:
1.Added global map to store various standbox instances for different requests.

2.Added startsandbox() Function:
-Validate the input fields.
-Check if sandbox exists for the given id , if exists starts it and stored the sandbox in the active sandbox global map.

3.Added stopSandbox() Function:
- Check if the sandbox with the given id is present in the active sandbox map ,stop it and remove from the map.

Type of change:
Feature Addition

3.File:components/tool-invocation.tsx
Summary:
1.Refactorizing 
- Rewrote import statements,conditional statmentements, error handling, variable declarations,UI style properties
into better Typescript alignment for better understanding of code and clarity.

Type of change:
1.Refactorization

4.File :components/mcp-server-manager.tsx

Summary:
-Added code to remove selected servers from selectedServers
-Added code to add selected servers from selectedServers
-Added toggleServerStatus() which controls the servers , provides better error handling for starting servers and logging.
-Updated code to stop server from running along with error handling.
-Updated restartServer() function to restart the server
-Added function getServerDisplayUrl() to display the correct server URL.

Type of change:
1.Feature Addition
2.Improvement

5.File:components/chat.tsx

Summary:

1.Updated code to fetch chat with ChatID.
2.Added Error handling to return empty chat instead of throwing an error.

Type of change:
1.Improvement 
2.Bug fix 








