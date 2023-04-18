# Attendance Management System

As a Human Resource manager i want to to have complete database of employees who are working in this organization, which can be used to apply leaves , show leave balances, approve and cancel applied leaves , post announcement and give feedback to employees.

You need to create two contracts using cosmwasm:

- Data Store Contract :
  - For storing employee details , leave balances , and feedback given to the employee.
  - Query details of all employee if caller is from HR department(i.e admin).
  - User should only see his personal details when queried.
  - User can update the personal details and should be approved by HR team to get reflected.
- Approval Contract :
  - For Leave approval based on the employee leave request , Give feedback to employees.
  - Only Admin can approve leaves and provide feedback
  - Non Admin should not have any access to the approval and feedback data.
  - Admin can only post the announcement which can be viewed by any of the employees.

# Note

Approval contract can be made to approve all the request automatically based on the leave request and employee id.
Approval contract should keep track of leave request ids to avoid redundant leave request.
Once leave request raised employee leave balance should be decreased based on the approval status.

Flow Example

- If user A wants to update their personal details , First they should call the `update personal details' method from Data Store Contract which is sent to Approval contract for approval.Once approval is done leave will be approved and status should reflect on Data Store Contract based on the leave request and employee.
