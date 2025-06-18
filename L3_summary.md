L3 Task Summary

Aim:
- Merge the latest changes from both branches.
- Ensure:
  1. All key features are integrated
  2. Merge conflicts are resolved
  3. The app builds and runs

Steps Followed:

1.Clone the forked repo-
```
  git clone https://github.com/idosal/scira-mcp-ui-chat.git
  cd scira-mcp-ui-chat
```

2.Connecting the orginal repo scira-mcp-ui-chat to the forked repo idosal/scira-mcp-ui-chat to get latest changes 

```
git remote add upstream https://github.com/zaidmukaddam/scira-mcp-chat.git 
```

3.Getting the changes made to the original repo 

``` git fetch upstream  ```

4.Adding original repo's changes to the forked repo (Leads to merge conflicts)

``` git merge upstream/main ```

5.Resolving the conflicts in the files-
 
 - components\chat.tsx
 - components\markdown.tsx
 - pnpm-lock.yaml
 - lib\mcp-client.ts

6. Build and run the app

``` pnpm dev```
Starts the nextjs server at the port http://localhost:3000/ 

7.Push the code 

``` git remote add origin https://github.com/rutujakenjalkar/IntershipTestAssignment.git
 - git push -u origin main
```

