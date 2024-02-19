```javascript
// 1. Initialize an array to store tasks for the week.
let weeklyTasks = new Array(7).fill(null);

// 2. Use a for loop to simulate each day of the week.
for (let day = 0; day < weeklyTasks.length; day++) {
    // 3. On Monday (day 0), you will start the JavaScript Course
    if (day === 0) {
        weeklyTasks[day] = "Start JavaScript Course";
    }
    // 4. Every alternate day, you revise the previous week's concepts.
    else if (day % 2 === 0) {
        weeklyTasks[day] = "Revise last week's concepts";
    }
    else{
        weeklyTasks[day] = "JavaScript course";
    }
}

// 5. Print the tasks for the week.
console.log("Weekly Tasks:");
weeklyTasks.forEach((task, index) => {
    let day;
    switch (index) {
        case 0:
            day = 'Monday';
            break;
        case 1:
            day = 'Tuesday';
            break;
        case 2:
            day = 'Wednesday';
            break;
        case 3:
            day = 'Thursday';
            break;
        case 4:
            day = 'Friday';
            break;
        case 5:
            day = 'Saturday';
            break;
        case 6:
            day = 'Sunday';
            break;
    }
    console.log(`${day}: ${task}`);
});
```