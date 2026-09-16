\# Git Rescue Workflow



\## 1. Bisect Finding



The regression was introduced in commit `c99fb4209e6fb6e5ed2789893fdb2f893d61d6c6`.



This commit broke the BULK20 discount by causing orders with 5 or more items to return the full price instead of applying the 20% discount.



\## 2. Branching Strategy



For a team of 4, I would recommend GitHub Flow. It is simple and practical for a small team because the main branch can stay stable while each feature or bug fix is worked on in a separate branch. Each branch can be reviewed through a pull request before it is merged back into main.



\## 3. Secret Removal



I removed the `.env` file from tracking and added `.env` to `.gitignore` so it will not be committed again.



However, the secret is still visible in old commits because Git keeps the full history of tracked files. To fully remove it, we would need to rewrite the repository history using a tool such as `git filter-repo` or BFG Repo-Cleaner, then force-push the cleaned history. In a real project, the exposed credentials should also be changed or rotated immediately.



This assignment did not require fully rewriting the history because that step is more destructive and can cause problems for anyone who already cloned or pulled the repository.



\## 4. History Rewriting



It was acceptable to rewrite history in Task 2 because the commits were still only on my local machine and had not been shared with teammates yet.



It would not be acceptable to rewrite commits that teammates had already pulled because rewriting history changes commit hashes. This can cause conflicts between their local copies and the remote repository.

