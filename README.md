# timetable-page

Timetable page generator

![screenshot](screenshot.png)

## Getting Started

Enter your timetable information into timetable.js, the information will be automatically reflected in index.html!

### First step

**IMPORTANT**: Firstly, rename `timetable-example.js` to `timetable.js`. It will not work without this operation.

### timetable.js

```javascript
const page_title = 'Timetable';
const time = ['9:00 - 10:30', '10:40 - 12:10', '13:00 - 14:30', '14:40 - 16:10', '16:15 - 17:45'];
const day_of_weeks = ['Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday'];
```
- **page_title**: Page title displayed on the header
- **time**: Time when the n-th period lecture will be held
- **day_of_week**: Name of the day of the week to be displayed

```javascript
const timetable = [
    {
        "name": "Lecture name",
        "teacher": "Teacher Name",
        "day_of_week": "mon", // You can use [mon, tue, wed, thu, fri]
        "time": 2,
        "lect_length": 1,
        "type": "Realtime",
        "google_classroom": "https://trpfrog.net",
        "link": "https://trpfrog.net",
        "zoom": "https://trpfrog.net",
        "color": "#90e200",
    },
    // the same continues below...
]
```
- **name**: Name of lecture
- **teacher**: Name of teacher
- **day_of_week**: Day of week this lecture held
    - You *must* use `mon`, `tue`, `wed`, `thu`, or `fri`
- **time**: n-th period of this lecture
- **lect_length**: The length of the lecture
- **type**: Form of lecture
    - Example: realtime, on-demand, face-to-face
- **google_classroom**: Google classroom URL
    - If left blank (`""`), it will be ignored.
- **link**: Homepage URL
    - If left blank, it will be ignored.
- **zoom**: Video meetings URL
    - If left blank, it will be ignored.
- **color**: Background color of this lecture
    - You can use CSS style color including color code (#90e200) and rgba function.
    - If left blank, used default color

Now that timetable.js is complete, let's open index.html. **You can see the timetable generated.** It is convenient to set this as your browser's home page.

### color.css (Optional)

You can customize the appearance of the timetable using `color.css`.


### Dockerfile (Optional)

You can host web server using nginx with docker.

```sh
# Build Dockerfile
$ docker build -t timetable .
# Start
$ docker run -d -p 80:80 --name timetable timetable
```

Open `localhost` with your web browser, timetable will be shown.

## Caution

If you put **important information** (such as video meeting URL) in timetable.js, you **MUST NEVER** publish that information on the Internet!

I will not be held responsible for any damage caused by the disclosure of links or other information.



## License

These fonts used in this repository are licensed under [Open Font License](https://scripts.sil.org/OFL).

- [Noto Sans Japanese](https://fonts.google.com/noto/specimen/Noto+Sans+JP/about) by Google
- [M PLUS Rounded 1c](https://fonts.google.com/specimen/M+PLUS+Rounded+1c?subset=japanese) by Coji Morishita, M+ Fonts Project
- [Font Awesome Free](https://fontawesome.com/) by Font Awesome
