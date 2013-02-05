# TESTING PROTOCOL

## Test compatibility and download new version
1. Test Accept HIT with random ID and save ID and group name for later
2. Download ZIP from https://github.com/gideongoldin/TurkGate (not from TurkGate download page)
3. Overwrite files on server with files from ZIP. DON'T delete files that aren't in ZIP, including config.php
4. Test Accept HIT again with same ID and group name. Verify that access is denied.
5. Test Accept HIT with new random ID. Verify that access is given.


## Clean install of new version
1. Uninstall old version
	1. Verify config file and database table are removed
2. Navigate to admin page. 
	1. Verify message that TurkGate is not installed.
3. Install new version
	1. Verify config file and database table are added
4. Return to admin page.
	1. Verify that TurkGate is installed.
	
## Test access control
1. Test Preview HIT with random ID (make sure to copy this), test group, and test URL for Web Interface HIT.
	1. Verify that you get appropriate message: "You have not done any surveys in the test group group. Once you accept the HIT, you will be able to access the survey.".
	2. Go back, and try again with same information. Verify that you get the same message as above.
	3. Go back, and Test Accept HIT with the same information. Verify that you are let through to the testDestination.php page.
	4. Go back, and Test Accept HIT again with the same information. Verify that you get the message: "If you completed the survey for this HIT, enter the completion code in the HIT page on Mechanical Turk. Otherwise, you may have already completed another survey in this group and cannot complete this one. Please return the HIT."
	5. Go back, and Test Preview HIT again with the same information. Verify that you get: "You have already accessed a survey in the test group group. Do NOT accept the HIT, because you will NOT be able to access the survey."
2. Repeat all of step (1) above using the Command Line Tools HIT and a new random ID, as shown below:
	1. Verify that you get appropriate message: "You have not done any surveys in the test group group. Once you accept the HIT, you will be able to access the survey.".
	2. Go back, and try again with same information. Verify that you get the same message as above.
	3. Go back, and Test Accept HIT with the same information. Verify that you are provided a link to open the study, and fields for completion code and comments, and a Submit button. Verify that link opens testDestination.php in a new tab.
	4. Go back, and Test Accept HIT again with the same information. Verify that you don't get a link to open the study, but do get a box for completion code and comments, as well as a Submit button.
	5. Go back, and Test Preview HIT again with the same information. Verify that you get: "You have already accessed a survey in the test group group. Do NOT accept the HIT, because you will NOT be able to access the survey."

## Test completion codes
1. Test Accept HIT with Web Interface HIT with a new random ID. Save the ID and group name to compare.
2. Enter a name and value and click Go To Completion Code.
3. Verify completion code contains correct ID, group name and name/value pair.
4. Copy completion code
5. Future plans: Test completion code verification here.

## Test HIT Creation
1. Create a HIT in survey site (e.g. Qualtrics), and copy link to survey.
2. On TurkGate Generate a HIT page, choose Survey Site, paste survey link and create a group name. 
3. Test Web Interface HIT
	1. Choose HIT Type Web Interface and click Generate HIT
	2. Copy completion code URL and set as exit URL in survey.
	3. Create a HIT in Mechanical Turk sandbox using web interface (Don't forget to allow non-Masters).
	4. Copy HTML from TurkGate page to Mechanical Turk Edit HTML Source window. HTML should automatically be selected when clicking with textbox.
	5. Publish HIT.
	6. Repeat steps 1,3,4,5 to create a second HIT with the same group name. Edit the project, because simply clicking New Batch will add assignments to the same HIT.
	7. In worker sandbox, accept one of the HITs.
	8. Click "check eligibility". Verify that you are eligible.
	9. Accept the HIT and click to open the study.
	10. Complete the study and copy the completion code. Completion code should automatically be selected when clicking anywhere on it.
	11. Submit the HIT with the copied completion code.
	12. Accept the other HIT.
	
	
	
	