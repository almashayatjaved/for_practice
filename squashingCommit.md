Here's how you can squash commits in Git:

1. **Start an Interactive Rebase**: First, open your terminal or command prompt and navigate to your Git repository. Use the following command to start an interactive rebase:

   ```bash
   git rebase -i HEAD~n
   ```

   Replace `n` with the number of commits you want to squash. For example, if you want to squash the last 3 commits, use `HEAD~3`.

2. **Edit the Rebase File**: Git will open a text editor displaying a list of commits and their actions. Each commit line will begin with the word "pick." To squash commits, change "pick" to "squash" (or simply "s" for short) for the commits you want to squash into the previous commit. Keep the first commit in the list as "pick."

   Before editing:
   ```plaintext
   pick abc123 First commit
   pick def456 Second commit
   pick 789ghi Third commit
   ```

   After editing (squashing the last two commits into the first):
   ```plaintext
   pick abc123 First commit
   squash def456 Second commit
   squash 789ghi Third commit
   ```

3. **Save and Close the Editor**: Save the changes and exit the text editor.

4. **Edit the Combined Commit Message**: Git will prompt you to edit the commit message for the combined commit. You'll see a text editor with the combined message of the squashed commits. Make any desired changes to the message, or keep it as is.

5. **Save and Close the Editor**: Save your changes and exit the text editor again.

6. **Finish the Rebase**: Git will complete the rebase process, squashing the selected commits into one. If you encounter any conflicts during this process, resolve them as prompted by Git.

7. **Force Push (Optional)**: If you've already pushed the original commits to a remote repository, you may need to force push the updated branch to the remote repository to reflect the squashed commits. Be cautious when force pushing, as it can rewrite history, which may affect collaborators. Use the following command:

   ```bash
   git push -f origin your-branch-name
   ```

Replace `your-branch-name` with the actual name of your branch.

Squashing commits can help keep your commit history clean and organized, making it easier for others to review your changes and for you to maintain a more structured project history. However, it's essential to communicate with your team and follow your organization's Git workflow guidelines when using such techniques.