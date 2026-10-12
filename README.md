# Job Tracker

A personal tool to keep track of the jobs you have applied to: what you applied for, how you applied, where each application stands, and when your interviews are.

It started as a core Java console application and grew into a responsive web app. Both versions are in this repository.

**Live demo:** file:///C:/Users/bhara/Downloads/Job%20Tracker.html

<!-- Add screenshots to a screenshots/ folder, then remove the comment markers around the line below.
![Job Tracker web app](screenshots/app.png)
-->

## Two versions

| | Console app | Web app |
| --- | --- | --- |
| Built with | Core Java, OOP, Collections | HTML, CSS, JavaScript (no libraries) |
| Runs in | Eclipse or any Java setup | Any modern browser |
| Data is kept | In memory, lost when the program stops | In your browser, kept between visits |

## Console app (Java)

A menu-driven program with these options:

- Add an application
- View all applications
- Update the status of an application
- Delete an application
- Search by company
- Show a summary

**How it is designed**

- `JobApplication` is the base class. `Referral` and `Online` extend it, one for jobs you got through a referral and one for jobs you applied to online.
- A `HashMap` keyed by application ID stores the applications, so finding, updating and deleting one is quick.
- A `HashSet` keeps each company only once.

**To run it:** open the project in Eclipse, then run the class that contains the `main` method (right click, Run As, Java Application).

## Web app

Open `index.html` in a browser. There is nothing to install and no server to run.

**Features**

- Add, edit, and delete applications, as an Online or a Referral application
- Change the status of an application: Applied, Interviewing, Offer, or Rejected
- Search by company, filter by status, and sort by newest added, interview date, date applied, or company
- A summary at the top with total applications, number of companies, a status breakdown, applications in the last 7 days, how many reached the interview stage, and a chart of applications per week
- Set an interview date and time, with a live countdown and a "Next interview" bar
- Reminders 1 day and 1 hour before an interview, as a pop-up on the page and as a browser notification if you allow it
- Add an interview to your calendar, with a Google Calendar link or an `.ics` file that includes the same two reminders
- A job link and notes for each application
- Export your list to a backup file and import it again on another device
- Works on phones, and follows your device's light or dark theme

**How it relates to the Java project**

| Java console app | Web app |
| --- | --- |
| `HashMap` keyed by ID | Applications stored in an object keyed by ID |
| `HashSet` of companies | A `Set` used to count unique companies |
| `Referral` and `Online` subclasses | An Online or Referral type on each application |

Your data never leaves your device: there is no account and no server. The list is saved in your browser's local storage.

## Limitations

- The list stays on the device and browser where you made it. Use Export backup and Import backup to move it.
- Clearing your browser data deletes the list, so export a backup now and then.
- Reminders only work while the page is open in a browser tab. For reminders that work when the page is closed, add the interview to your calendar.
- Calendar events assume the interview lasts 1 hour.

## Planned: Spring Boot version

The next step is a full stack version with a Spring Boot backend:

- User accounts and login, so every device shows the same list
- A MySQL database using Spring Data JPA and Hibernate
- A REST API that the web page calls instead of browser storage
- Email reminders sent by the server, even when the page is closed

## Author

**Bharath Kumar Marrimanu**

- LinkedIn: https://www.linkedin.com/in/bharathkumarmarrimanu
- GitHub: https://github.com/bharathkumarmarimanu-source
