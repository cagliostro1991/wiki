# Update/Upload git repository on server

## First upload

1. Login to Dev server

		ssh admin@104.236.107.55
		
		
2. Change directory to project folder

		cd /home/admin/web/example.com/public_html
		
		
3. Clone project files to `/public_html` 

		git clone git clone git://github.com/user/project.git .
		
	*Do not forget `.` at the end. It will copy the project files directly into the current directory without creating _project_ folder*

4. Checkout to enviroment brunch

		git checkout [branch name]	


## Update

After you have commit all the necessary changes to the git repo, login to the server and pull changes.

1. Login to Dev server

		ssh admin@104.236.107.55
		
2. Change directory to project folder

		cd /home/admin/web/example.1pls1.com/public_html

3. Forse pull changes 

		git pull
		
	If files have been modified, use the command to reset all changes

		git reset --hard origin/[your_branch]

