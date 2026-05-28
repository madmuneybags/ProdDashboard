# ProdDashboard
A production dashboard that can filter and track jobs.

## Overview
This Dashboard is a fullstack internal web application designed to help manufacturing operators and supervisors monitor, organize, and track active production jobs in real time.

The system aggregates live production data, provides customizable filtered views, supports collaborative job notes, helps operators prioritize work across departments, and provides communication between multiple levels of management. 

This project began as a lightweight local HTML/Javascript tool and evolved into a centralized Flask + Vue application deployed internally across multiple production workstations with over 160 unique users. The webapp implements a SQL database to provide central information for all users. 

The dashboard became a central tool used by operators and management to monitor production flow, track work orders, and coordinate tasks more efficiently. This project provided hands-on experience building and maintaining a production-grade internal application used in a real manufacturing environment.

## Key Features

### Custom Job views

Users can create personalized views using advanced filtering and sorting logic. 

Features include:
- Mutli-condition filtering
- Department Grouping
- Mutli-column sorting
- Saved/importable views

### Real-Time Shared Notes

Operators and supervisors can attach persistent notes to jobs that are visible to all users. A note can be made permenant or temporary, which will be erased when the job moves departments.

Features include:
- Auther-based edit permissions
- Department aware note visibility
- Batched Nnote loading for perfomance
- Timestamp tracking and update history

### List/Job Notifications

Supervisors can send job lists. These lists will alert on all operators views allowing for easy communication of high priority jobs. These lists can be updated to reflect new or changed priorities. 

### Rework Status Tracking

Supervisors and operators can tag jobs that need reworked and update rework status as the job goes through the rework process. Integrates with an already existing system to provide better functionality and visibility than the default system. 

## Technical Challenges Solved

### Performance Optimization

Thousands of active jobs are within the shop at all times, leading to bottlenecks in the frontend and database accesses.
To improve resposiveness, I implemented:
- Cached job hydration
- Batched database reads
- Debounced note saves
- Reduced redundant API requests

These changes significantly reduced dashboard load times and improved responsiveness across production workstations.

### Shared Data Synchronization

One major challenge was allowing multiple users to collaboratively interact with shared job notes while preventing conflicting edits

To solve this, I implemented:
- Author ownership rules
- Timestamp tracking
- Shared database synchronization logic
- Department-aware note filtering

### Enterprise Authentication Integration

The application needed to function entirely inside a Windows enterprise environment using Active Directory authentication.

## Technologies Uused

#### Frontend
- Vue.js
- JavaScript
- HTML/CSS

#### Backend
- Python
- Flask

#### Database
- SQLite



