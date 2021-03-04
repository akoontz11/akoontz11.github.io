# Repository for personal website, using blogdown package.

The workflow for updating website using this repository is as follows:
1. Update relevant folders/files outside of the <code>public/</code> directory. To check updates, call <code>blogdown::serve_site()</code>.
2. Once all changes have been made, navigate to the uppermost directory (something like <code>website</code>) and call <code>build_site()</code>.
3. This will update the necessary files/folders in the <code>public/</code> directory. Navigate to that directory, check the changes with <code>git status</code>, and commit the changes as needed.
4. <code>push</code> the required changes. Remember that there may be a time lag between pushing changes up and seeing the changes on the webpage itself.
