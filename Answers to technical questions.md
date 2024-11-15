1. How long did you spend on the coding test?
Ans : Approximatly arount 8-10 hours.

2. What was the most useful feature that was added to the latest version of your chosen language? Please include a snippet of code that shows how you've used it.
Ans : Debounced search/filter functionality

This is particularly useful when you want to optimize performance for searching or filtering tasks, avoiding excessive renders or API calls as the user types.

//code
const [isModalOpen, setIsModalOpen] = useState(false);
  const [searchQuery, setSearchQuery] = useState('');
  const [selectedPriority, setSelectedPriority] = useState("All"); // Selected priority

//other code
        


useEffect(() => {
    // Filter tasks based on search query and priority
    const filteredTasks = tasks.filter((task) =>
      task.title.toLowerCase().includes(searchQuery.toLowerCase()) &&
      (selectedPriority === "All" || task.priority === selectedPriority)
    );

    // Group tasks by status
    setTodos(filteredTasks.filter((task) => task.status === 'Upcoming'));
    setInProgress(filteredTasks.filter((task) => task.status === 'Overdue'));
    setClosed(filteredTasks.filter((task) => task.status === 'Completed'));
  }, [tasks, searchQuery, selectedPriority]);



3. How would you track down a performance issue in production? Have you ever had to do this?
Ans : To track down performance issues in production, I use monitoring the codes, along with browser developer tools like Chrome's Performance tab to identify bottlenecks in rendering and network requests. Optimizing backend queries, caching, and improving frontend performance (e.g., lazy loading, code splitting) are key steps to resolve these issues.

4. If you had more time, what additional features or improvements would you consider adding to the task management application?
Ans : 
1. Advanced Task Features
*Allow users to set recurring tasks (e.g., daily, weekly, monthly).
*Include notifications or reminders for upcoming recurrences.
*Subtasks and Dependencies:
*Enable breaking tasks into smaller subtasks.

2. User Interface/Experience Enhancements

*Implement a toggle for dark and light themes to enhance usability in different lighting conditions. 

Add drag-and-drop functionality for reordering tasks or assigning priorities.
Offline Mode:


3. Collaborative Features

*Allow multiple users to share and manage tasks collaboratively.
*Enable users to add comments or upload attachments to tasks for better communication.

4. Integration with Third-Party Tools
*Sync tasks with Google Calendar, Outlook, or Apple Calendar.
*Notifications and Reminders:
*Push notifications for task deadlines using Firebase Cloud Messaging.
*Email reminders for overdue or high-priority tasks.
5. Data Visualization
*Progress Tracking:
*Visualize task completion rates with progress bars or pie charts.
*Analytics Dashboard:
*Provide insights on task trends, overdue items, or team productivity.
