# Onboarding-filtering-UiPath-Project
Based on a given set of rules, categorize new employees into different onboarding streams and move them to specific processing queues for the steps that follow, i.e. password reset, order device(mobile phone/tablet) for employee, send onboarding document for the given team they'll be a part of.
		
| Step | Description | Action | Next Step Condition |
|------|-------------|--------|---------------------|
| 1.   | The robot receives an email in the configured inbox and checks for attachments. | Receive email, check attachment. | If no attachment or not Excel, stop and inform team. Else, go to next step. |
| 2.   | The robot reads information from UiPath Data Service and determines the onboarding operation. | Read data, determine action. | Depending on "Action" value: Add, Order, Delete, or Send. |
| 3.   | If adding a new employee, the robot will create a new entry with the employee's details and send a welcome message. | Create entry, send welcome email. | Go to step 4 if operation is "Order". |
| 4.   | For ordering a new device, the robot adds a new device in the Data Service and informs the IT team. | Add device, notify IT. | If no more employees, end process. Else, go to next step. |
| 5.   | If deleting an employee, the robot deletes the entry and sends a goodbye email. | Delete entry, send goodbye email. | If no more employees, end process. Else, go to next step. |
| 6.   | Sending onboarding documents involves emailing the PDF to the employee and cc'ing the coordinator. | Send onboarding documents. | If no more employees, end process. |


