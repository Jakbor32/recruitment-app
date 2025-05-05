# Recruitment-app

User-friendly recruitment platform designed to streamline the hiring process, built with PowerApps, Power Automate (Flow), and SharePoint. It helps HR teams efficiently manage candidate applications, track progress, and automate workflows.

---

## Plan outline

### 1. Application Description

This application is a comprehensive HR solution designed to facilitate the secure recruitment of new employees. It focuses on ensuring that sensitive data, such as personal information and job applications, remains confidential and inaccessible to unauthorized users within the system.

The system was developed using a combination of powerful Microsoft technologies, including SharePoint, Power Automate, PowerApps Canvas App - modern controls and themes. By leveraging PowerApps, we provide a seamless user interface for HR professionals to manage the recruitment process. Teams Approvals and Outlook notifications are integrated for streamlined communication and decision-making. Additionally, the application automatically generates PDF documents for recruitment-related forms, improving efficiency and reducing manual paperwork.

![recruitment app](https://github.com/Jakbor32/recruitment-app/blob/main/media/app/photos/add_request_screen.JPG)

### 2. Application Features

#### PowerApps:

- **Submit, Edit, or Delete Requests**: Users can submit new requests, edit existing ones, or delete them directly from the application interface.
- **Authorized Access**: Access to the application is based on security groups, with two levels of access: regular access and restricted access.
- **HR Request List**: HR personnel have access to a complete list of all requests, with full visibility and management rights. Regular users do not have access to this list.
- **My Requests**: Regular users can view and manage only their own requests.
- **Request Preview**: Users can preview the details of a selected request, including all relevant information.
- **Request Browser in PDF Format**: HR personnel can view and download request forms in PDF format. Access to these PDFs is restricted to HR users only.

#### Power Automate:

- **Request Approval via Teams Approval**: The application integrates with Microsoft Teams to facilitate the approval process for requests.
- **Email Notifications**: Users receive email notifications upon the acceptance or rejection of their request.
- **Comment Tracking**: Comments added during the approval process are saved and visible to subsequent approvers, ensuring that feedback is easily accessible and traceable.
- **Request Status Updates**: The status of requests changes dynamically throughout the approval or rejection process. A built-in registry tracks the progress of each request, with SharePoint being used to view the approval history and status updates.
- **PDF Document Generation**: Requests are automatically generated as PDF documents, ensuring consistent and professional documentation.
- **Correction Module for Rejected Requests**: If a request is rejected, the applicant receives a unique link to directly access the application and make corrections to the specific request that was rejected.

#### SharePoint:

- **Centralized Data Storage**: SharePoint is used to store and manage all data related to requests, ensuring secure and organized data management.
- **Audit Trails**: SharePoint tracks all actions performed on requests, providing a clear audit trail for compliance and transparency.
- **Restricted Access**: Only HR personnel have full access to the SharePoint data. Other users have no access.
- **Data Security**: To ensure data security, users cannot submit or modify requests directly through SharePoint. All request-related activities must be handled within the PowerApps application, ensuring that only authorized personnel can make changes to sensitive data.

### 3. How the Process Works

### 4. Technologies

- **Microsoft PowerApps**
- **Microsoft Power Automate**
- **SharePoint**
- **OneDrive for Business**
- **Microsoft Teams**
- **Outlook**
- **Microsoft 365 Groups**

### 5. System Requirements

- **Microsoft PowerApps** - PowerApps Per User, PowerApps Per App
- **Microsoft Power Automate** - Power Automate Per User, Power Automate Per Flow
- **SharePoint** - SharePoint Online Plan 1, SharePoint Online Plan 2
- **OneDrive for Business** - OneDrive for Business Plan 1, OneDrive for Business Plan 2
- **Microsoft Teams** - Microsoft 365 Business Standard, Business Premium, Enterprise E3, Enterprise E5
- **Outlook** - Exchange Online Plan 1, Exchange Online Plan 2

### 6. Installation and Configuration

#### 1. SharePoint:

- [Link to configure list and columns](https://github.com/Jakbor32/recruitment-app/blob/main/media/sharepoint/lists/README.md)
- [Link to configure sharepoint list security and groups](https://github.com/Jakbor32/recruitment-app/blob/main/media/sharepoint/security/README.md)
- [Link to configure sharepoint views](https://github.com/Jakbor32/recruitment-app/blob/main/media/sharepoint/views/README.md)

#### 2. PowerApps:

- [Link to configuration](https://github.com/Jakbor32/recruitment-app/blob/main/powerapps/README.md)

#### 3. Power Automate:

- [Link to configuration](https://github.com/Jakbor32/recruitment-app/blob/main/power-automate/README.md)

### 7. Using the Application

![powerapps flowchart](https://github.com/Jakbor32/recruitment-app/blob/main/media/app/photos/powerapps_flowchart.png)

### 8. Troubleshooting

- **PowerApps**  
  If a submitted request does not appear in the connected data source (e.g., SharePoint), the issue could be related to client-side validation, network interruptions, or a failure in the data connection. To improve reliability and visibility, wrap the `SubmitForm()` function in an `IfError()` block and surface any errors using `Notify()`. This approach allows you to provide meaningful feedback to users while capturing the reason for submission failure. Additionally, use the built-in **Monitor** tool in PowerApps Studio to inspect app behavior in real time — including API calls, connector responses, and failed operations. This helps track why a form might not have been saved properly or whether there was an issue with the SharePoint integration.

- **SharePoint**  
  When dealing with unexpected changes or missing data in lists or document libraries, the **Version History** feature is the first place to investigate. SharePoint automatically tracks edits to list items and documents, allowing you to review, compare, or restore previous versions. This is especially useful in workflows involving PowerApps or Power Automate, where automated changes might overwrite user input. You can access an item’s version history via the context menu to audit modifications and restore previous states if needed.  
  Additionally, it is important to verify **user permissions** on the target SharePoint list or document library. If the user or service account running a flow or submitting data from PowerApps lacks sufficient permissions (e.g., Contribute or Edit rights), the submission will silently fail or return an access denied error. Ensuring correct list-level or item-level permissions is critical for successful data operations, especially in apps that are widely used across departments or organizations.

- **Power Automate**  
  If a flow fails to execute or produces unexpected results, the **Run History** within Power Automate provides detailed diagnostics. Navigate to the specific flow in the Power Automate portal, then review each execution instance, paying close attention to any failed steps. Expanding a run reveals input/output values and error messages for every action, helping you identify whether the issue stems from permissions, broken expressions, unmet trigger conditions, or null data. Ensuring that flows handle exceptions gracefully (using `Configure run after` or condition branches) also helps prevent partial failures in production environments.

### 9. Future Development and Roadmap

This recruitment platform was designed with extensibility in mind. To ensure long-term value and adaptability to evolving HR needs, the following roadmap outlines planned features, enhancements, and areas for improvement:

- **Mobile Responsiveness & Offline Mode**  
  Optimize the PowerApps Canvas App for mobile devices with responsive layouts and offline capabilities, allowing HR teams to work efficiently on the go or in low-connectivity environments.

- **Interview Scheduling Integration**  
  Integrate calendar features and Microsoft Bookings to streamline the scheduling of interviews, with automated invitations sent to candidates and interviewers.

- **Analytics Dashboard**  
  Implement a Power BI-based analytics dashboard to give HR managers insights into recruitment metrics, such as time-to-hire, rejection rates, and bottlenecks in the approval process.

- **Multi-language Support**  
  Add localization support to enable use of the application in multiple languages, depending on the organization’s needs.

- **Security Hardening**  
  Conduct a formal security review of data access rules, roles, and sharing configurations to ensure continued compliance with internal and external data privacy regulations.

- **Automated Deletion & Retention Policies**  
  Implement automated retention policies for archiving or deleting old recruitment requests in SharePoint after a defined period, in accordance with GDPR and internal HR policies.

- **User Feedback Loop**  
  Add an in-app feedback module to collect user suggestions and identify usability pain points directly from end users.
