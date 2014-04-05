A cli for Kanbanize, so I don't have to go use the web UI for frequent operations.

# Install

	sudo npm install -g kanbanize-cli

# Set up

`k set key [api key]`  The API key you can get from the web ui, from the top-right menu dropdown under "API"

`k set domain [domain name]`  The domain name where you visit Kanbanize.  Could be company-specific, may just be kanbanize.com

`k set board [board id]`  The board you want to interact with.  You can get this from the dashboard, by mousing-over the right side of the list of boards, or you can just grab it from the url when you open up the board.

`k set user [username]`  Your username.  Case sensitive.  This is used to filter down tasks so that you'll just see the ones that are assigned to you.  If you want to see all jobs, set to "all".

`k set columns [column names]`  A comma-separated list of column names from the board.  Case sensitive.  Only tasks in these columns will be displayed.  If you want to try to fit all the columns in your terminal, set to "all".

If you want to check the current value of any of the settings above, you can see it by typing `k get [setting name]`.

# Usage

## View your tasks

`k tasks`

## Add a task

`k task [template name] [task title]`

New tasks go into the backlog.  The template name is case sensitive.

## Select a task

`k work [task id]`

See whatever task id you previously selected by typing `k current`, or just look for the blue task id when viewing the task list.

## View subtasks

`k subtasks [OPTIONAL task id]`

If you don't type in the task id, subtasks will be shown for whatever task you said you were working.

## Add a subtask

`k add subtask [subtask title]`

## Mark a subtask as completed

`k complete [subtask id]`

## Move a task to a different column

`k move [left|right] [OPTIONAL taskid]`

## Run arbitrary functions against the API

`k api [api function] [header1 value1 [header2 value2 ...]]`

Run any of the [Kanbanize API functions](https://kanbanize.com/ctrl_integration) you like and view the resulting JSON.  Your API key and the current board id will be automatically passed in to every call.