# Indexing Notes

## Candidate Indexes

### Find employees of a department

```sql
Employee.department_id
```

### Find who manages a department (and who is any employee's manager)
```
Department.manager_employee_id
```

### Projects that are almost due

Assumption: this list is shown in the dashboard.

Composite index candidate:

```sql
Project.status
Project.end_date
```

### Find invoice of a project (default sort by newest)

```sql
Invoice.project_id
Invoice.invoice_date
```

### Find timesheet of an employee (queriable by date range)

```sql
Timesheet.employee_id
Timesheet.work_date
```

### Find how much a project cost in terms of workforce (all-time and in a day), and what can be billed to the client

```sql
Timesheet.project_id
Timesheet.work_date
Timesheet.billable_flag
```

### Find projects of a client
```sql
Project.client_id
```

### Find how many employees are working on a project on a given day

```sql
Employee_Project.project_id
Employee_Project.assignment_start_date
Employee_Project.assignment_end_date
```