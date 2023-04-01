# df-mod3-sdm



Excercise 1

I began by running the Get-WinEvent -ListLog * command and sending it to the logs.txt file.

I used Get-WinEvent -LogName Security -MaxEvents 20 > security20.txt. 

I used the Get-Content logs.txt | Select-String -Pattern "PowerShell" > GetContentLog.txt command to get content in the logs.txt that used the word PowerShell and put it in a text file.

I Get-WinEvent -LogName Security -MaxEvents 20 | Where-Object {$_.Id -like '5379'} > WhereObject.txt  to find items with the ID of 5379 and put them in a text file.

I used the command Get-Content logs.txt | Select-String -Pattern "Windows" | Export-Csv -Path .\CSVoutput.csv to select strings containing Windows from the logs.txt file and exported those results to a CSV file.



Excercise 2

I used the mkdir Directory1 command to mak a directory called Directory 1.

Then I created a file called copyme and used the Copy-Item -Path .\copyme.txt -Destination .\Directory1 to copy the file to Directory 1.

I used the command Get-Acl -Path .\logs.txt | Export-Csv -Path \.CSVGetACL.csv to get the ACL of the logs file and export it as a CSV.


Excercise 3

I created a file called evidence.txt and put it in a folder called evidence. I then encrypted evidence.txt and put it in a new file using Get-Content evidence.txt | ConvertTo-SecureString -AsPlainText -Force | ConvertFrom-SecureString | Out-File .\encryptedEvidence.txt -NoNewline.

I then used the command Get-Acl -Path .\evidence\evidence.txt > .\evidence\evidenceACL.txt to get the ACL of evidence.txt and placed it in a new file.

I changed the encrypted evidence permission using icacls .\EncryptedEvidence /setintegritylevel h.

I then ran the command Get-Acl -Path .\EncryptedEvidence\encryptedEvidence.txt > .\EncryptedEvidence\encryptedevidenceACL.txt to get the acl of the encrypted file and plae it in a new file.



Finally, I created some new directories and moved files into the directories for a logical display.

