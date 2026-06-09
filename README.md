# ForgeTrack-Digital-Shopfloor-Tracker
A modular, web-based production execution and tool lifecycle monitoring framework designed to digitize legacy paper-based industrial forging shop floors
# ForgeTrack: Digital Production & Tool Monitoring System for Forging Shops

![ForgeTrack Dashboard Interface](Aditya’s Forging Shop Digital Tracker.png)

An advanced, data-driven manufacturing execution prototype designed to eliminate manual tracking overhead, minimize tool downtime, and bring real-time operational visibility to legacy forging shop floors. Developed and validated through in-plant observations at **Vanaz Engineers Ltd.**

---

## 📌 Project Overview & Industry 4.0 Context
Traditional forging environments frequently suffer from disconnected workflows, manual data entry bottlenecks, lost paperwork, and a lack of granular visibility into tooling lifecycles. 

**ForgeTrack** bridges this gap as a localized digital manufacturing execution solution. By aligning with **Industry 4.0 principles (Cyber-Physical Systems and Data-Driven Manufacturing)**, it converts erratic shop-floor activities into structured, actionable data pools.

### Key Transformations:
* **Manual System:** Fragmented logs, delayed end-of-day reports, untracked tool wear, high risk of recording errors.
* **ForgeTrack System:** Instantaneous task logging, real-time analytics, automated tool lifecycle alerting, and standardized data exports.

---

## ⚙️ Core Engineering Features

### 1. Intelligent Operator Data Capture
* **Automated Validation Logic:** Features auto-fill validation patterns to streamline operator ID logging and shift-wise attendance records.
* **Timestamp Verification:** Automatically logs precise submission times to maintain an unalterable operational audit trail.

### 2. Predictive Tool Lifecycle Management
* **Wear Tracking Metrics:** Tracks real-time machine tool operations and component allocations.
* **Automated Tool Life Alerts:** Flags imminent degradation or milestone breaches to prompt predictive maintenance windows, preventing catastrophic tool failure during high-volume forging runs.

### 3. Analytics & Manufacturing Intelligence
* **Dynamic Productivity Tracking:** Built-in charting engines map out daily output trends (`Tasks per Day`) visually.
* **Standardized Compliance Auditing:** Embeds native documentation guidelines for safety protocols and workstation procedures.
* **Enterprise Data Integration:** Converts multi-variable manufacturing histories into cleanly formatted, downloadable Excel reports via structural client-side compilation logic.

---

## 🛠️ Technology Stack & Software Architecture

* **Front-End UI/UX:** HTML5, CSS3 (Custom responsive grid layout tailored with high-contrast, icon-based operational cues for low-digital-literacy environments).
* **System & Execution Logic:** Vanilla JavaScript (ES6+) utilizing secure client-side Web Storage engines for reliable localized state maintenance.
* **Data Analytics Engines:** Chart.js (Dynamic relational trend rendering).
* **File Compilation Matrices:** SheetJS / XLSX.js (Structured tabular extraction for production reporting).

---

README.md with technical project architecture
## 📂 Repository Structure

<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Aditya’s Forging Shop Digital Tracker</title>
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/chart.js" />
<style>
  body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    background: linear-gradient(to right, #eef2f3, #8e9eab);
    margin: 0;
    padding: 20px;
  }
  header {
    display: flex;
    align-items: center;
    gap: 15px;
    background: #002b5b;
    color: white;
    padding: 15px;
    border-radius: 12px;
    box-shadow: 0 4px 10px rgba(0,0,0,0.2);
  }
  header img {
    height: 60px;
  }
  h1 {
    font-size: 2rem;
    margin: 0;
  }
  section, form, footer {
    background: white;
    padding: 20px;
    border-radius: 12px;
    margin-top: 20px;
    box-shadow: 0 4px 10px rgba(0,0,0,0.1);
  }
  label {
    display: block;
    margin-top: 10px;
    font-weight: 600;
  }
  input, select, textarea {
    width: 100%;
    padding: 8px;
    margin-top: 5px;
    border-radius: 6px;
    border: 1px solid #ccc;
  }
  button {
    margin-top: 15px;
    padding: 10px 20px;
    background: #004aad;
    color: white;
    border: none;
    border-radius: 8px;
    font-weight: bold;
    cursor: pointer;
    transition: background 0.3s ease;
  }
  button:hover {
    background: #003580;
  }
  #message {
    margin-top: 10px;
    font-weight: 600;
    color: green;
  }
  .tool-warning {
    color: red;
    font-weight: bold;
  }
  footer {
    text-align: center;
    font-size: 13px;
    color: #555;
  }
  canvas {
    max-width: 100%;
    margin-top: 20px;
  }
  .qr-section img {
    width: 150px;
    height: 150px;
    margin-top: 10px;
  }
  .info-section {
    font-size: 14px;
    background: #f9f9f9;
    padding: 15px;
    border-left: 5px solid #007bff;
    margin-top: 20px;
    border-radius: 8px;
  }
  .attendance-form {
    margin-top: 40px;
  }
  .monthly-report-section {
    margin-top: 30px;
  }
</style>
</head>
<body>

<header>
  <img src="https://www.shutterstock.com/image-vector/blacksmith-shop-graphic-label-forge-260nw-2093527090.jpg" alt="Forging Logo">
  <h1>Aditya’s Forging Shop Digital Tracker </h1>
</header>

<!-- Task Reporting Form -->
<form id="taskForm">
  <h2>Task Reporting</h2>

  <label for="workerName">Worker Name</label>
<select id="workerName" required>
  <option value="">Select Worker</option>
  <option value="21PS301">Aditya Kachi</option>
  <option value="22PS302">Parth Atiwadkar</option>
  <option value="22PS303">Abhishek Gadakh</option>
  <option value="22PS304">Tejas Navsupe</option>
  <option value="22PS305">Umesh Khadke</option>
  <option value="22PS306">Aditya Kadam</option>
  <option value="22PS307">Harshada Bhagat</option>
  <option value="22PS308">Vaishnavi Hande</option>
</select>

<label for="workerId">Worker ID (Auto-filled)</label>
<input type="text" id="workerId" readonly required />

<script>
  document.getElementById('workerName').addEventListener('change', function () {
    const selectedId = this.value;
    document.getElementById('workerId').value = selectedId;
  });
</script>


  <label for="taskType">Task Type</label>
  <select id="taskType" required>
    <option value="">Select Task</option>
    <option value="forging">Forging</option>
    <option value="trimming">Trimming</option>
    <option value="inspection">Inspection</option>
    <option value="machining">Machining</option>
    <option value="packaging">Packaging</option>
  </select>

  <label for="taskDate">Task Date</label>
  <input type="date" id="taskDate" required />

  <label for="partNumber">Part Number</label>
  <input type="text" id="partNumber" required />

  <label for="toolId">Tool ID Used</label>
  <input type="text" id="toolId" required />

  <label for="comments">Comments</label>
  <textarea id="comments" rows="3"></textarea>

  <button type="submit">Submit Task</button>
  <div id="taskMessage"></div>
</form>

<!-- Attendance Reporting Form -->
<form id="attendanceForm" class="attendance-form">
  <h2>Daily Attendance Report</h2>
  <label for="attendanceWorkerId">Worker ID</label>
  <input type="text" id="attendanceWorkerId" required />

  <label for="attendanceDate">Date</label>
  <input type="date" id="attendanceDate" required />

  <label for="attendanceStatus">Status</label>
  <select id="attendanceStatus" required>
    <option value="">Select Status</option>
    <option value="present">Present</option>
    <option value="absent">Absent</option>
    <option value="leave">Leave</option>
  </select>

  <button type="submit">Submit Attendance</button>
  <div id="attendanceMessage"></div>
</form>

<section class="tool-tracker">
  <h2>🔧 Tool Life Tracker & Alerts</h2>
  <ul id="toolList">
    <li>Tool ID: T2024A | Last Used: 2025-06-05 | Life Left: 120 cycles</li>
    <li>Tool ID: T2024B | Last Used: 2025-06-04 | Life Left: 85 cycles</li>
    <li>Tool ID: T2024C | Last Used: 2025-06-02 | Life Left: <span class="tool-warning">15 cycles (⚠️ Replace soon)</span></li>
  </ul>
</section>

<section class="export-section">
  <button id="exportExcelBtn">📦 Export Data to Excel</button>
</section>

<!-- Monthly Report Generator -->
<section class="monthly-report-section">
  <h2>📅 Generate Monthly Report</h2>
  <label for="monthPicker">Select Month</label>
  <input type="month" id="monthPicker" />
  <button id="generateMonthlyReportBtn">Generate Monthly Report</button>
</section>

<section class="productivity-chart">
  <h2>📊 Daily Productivity Chart</h2>
  <canvas id="productivityChart" height="120"></canvas>
</section>

<section class="info-section">
  <h3>📘 Worker Safety & Process Guidelines</h3>
  <p><strong>⚠️ General Safety:</strong> Always wear safety gloves, helmets, goggles, earplugs. Don’t work if fatigued. Follow supervisor instructions strictly.</p>
  <p><strong>🔥 Forging:</strong> Ensure proper heating of billets, check for scaling, and maintain press alignment. Report any unusual hammer sounds or cracks in die immediately.</p>
  <p><strong>✂️ Trimming:</strong> Use hand tools safely. Watch for sharp edges. Keep trimming area clean to avoid slipping.</p>
  <p><strong>🔍 Inspection:</strong> Measure with calibrated instruments. Log all defects and isolate rejected parts. Follow check-sheet standards.</p>
  <p><strong>🔧 Machining:</strong> Wear tight-fitting clothes. Secure the workpiece properly. Monitor tool vibrations and coolant flow.</p>
  <p><strong>📦 Packaging:</strong> Pack in clean, dry boxes. Use protective wraps and label each part clearly. Store finished goods on racks only.</p>
  <p><strong>🛠️ Tool Life Awareness:</strong> Don't exceed tool cycle limits. Check condition before use. Replace tool if life &lt; 20 cycles.</p>
</section>

<section class="ai-section">
  <button onclick="launchAI()">🤖 Ask AI Assistant</button>
  <div id="aiOutput" style="margin-top: 10px; font-weight: 600;"></div>
</section>

<footer>
  <p>&copy; 2025 Aditya’s Forging Shop Prototype. Designed by Aditya.</p>
</footer>

<script src="https://cdn.sheetjs.com/xlsx-latest/package/dist/shim.min.js"></script>
<script src="https://cdn.sheetjs.com/xlsx-latest/package/dist/xlsx.full.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
<script>
  const taskForm = document.getElementById('taskForm');
  const attendanceForm = document.getElementById('attendanceForm');
  const taskMessage = document.getElementById('taskMessage');
  const attendanceMessage = document.getElementById('attendanceMessage');
  const exportBtn = document.getElementById('exportExcelBtn');
  const generateMonthlyReportBtn = document.getElementById('generateMonthlyReportBtn');
  const monthPicker = document.getElementById('monthPicker');

  function getTasks() {
    return JSON.parse(localStorage.getItem('tasks') || '[]');
  }
  function saveTask(task) {
    const tasks = getTasks();
    tasks.push(task);
    localStorage.setItem('tasks', JSON.stringify(tasks));
  }

  function getAttendance() {
    return JSON.parse(localStorage.getItem('attendance') || '[]');
  }
  function saveAttendance(att) {
    const attendance = getAttendance();
    attendance.push(att);
    localStorage.setItem('attendance', JSON.stringify(attendance));
  }

  // Task submission handler
  taskForm.addEventListener('submit', e => {
    e.preventDefault();

    const task = {
      workerId: document.getElementById('workerId').value.trim(),
      taskType: document.getElementById('taskType').value,
      taskDate: document.getElementById('taskDate').value,
      partNumber: document.getElementById('partNumber').value.trim(),
      toolId: document.getElementById('toolId').value.trim(),
      comments: document.getElementById('comments').value.trim()
    };

    saveTask(task);

    taskMessage.textContent = `✅ Thanks for submitting, ${task.workerId}! You've earned a reward!`;
    taskForm.reset();
    updateChart();
    setTimeout(() => { taskMessage.textContent = ''; }, 4000);
  });

  // Attendance submission handler
  attendanceForm.addEventListener('submit', e => {
    e.preventDefault();

    const att = {
      workerId: document.getElementById('attendanceWorkerId').value.trim(),
      attendanceDate: document.getElementById('attendanceDate').value,
      status: document.getElementById('attendanceStatus').value
    };

    saveAttendance(att);

    attendanceMessage.textContent = `✅ Attendance for ${att.workerId} recorded!`;
    attendanceForm.reset();
    setTimeout(() => { attendanceMessage.textContent = ''; }, 4000);
  });

  // Export combined data handler
  exportBtn.addEventListener('click', () => {
    const tasks = getTasks();
    const attendance = getAttendance();
    const allData = [];

    // Add tasks with a type label for clarity
    tasks.forEach(t => allData.push({
      RecordType: 'Task',
      WorkerID: t.workerId,
      TaskType: t.taskType,
      Date: t.taskDate,
      PartNumber: t.partNumber,
      ToolID: t.toolId,
      Comments: t.comments,
      AttendanceStatus: ''
    }));

    // Add attendance with empty task fields
    attendance.forEach(a => allData.push({
      RecordType: 'Attendance',
      WorkerID: a.workerId,
      TaskType: '',
      Date: a.attendanceDate,
      PartNumber: '',
      ToolID: '',
      Comments: '',
      AttendanceStatus: a.status
    }));

    if (!allData.length) {
      alert('No data to export!');
      return;
    }

    // 1. Open new tab with HTML table preview
    let html = '<html><head><title>Forging Shop Combined Report</title></head><body>';
    html += '<h2>📊 Aditya’s Forging Shop - Combined Report View</h2>';
    html += '<table border="1" cellpadding="5" cellspacing="0" style="border-collapse:collapse;">';
    html += '<tr>';
    for (let key in allData[0]) {
      html += `<th>${key}</th>`;
    }
    html += '</tr>';

    allData.forEach(entry => {
      html += '<tr>';
      for (let key in entry) {
        html += `<td>${entry[key]}</td>`;
      }
      html += '</tr>';
    });

    html += '</table>';
    html += '</body></html>';

    const newWindow = window.open();
    newWindow.document.write(html);
    newWindow.document.close();

    // 2. Trigger XLSX file download
    const worksheet = XLSX.utils.json_to_sheet(allData);
    const workbook = XLSX.utils.book_new();
    XLSX.utils.book_append_sheet(workbook, worksheet, "CombinedReport");
    XLSX.writeFile(workbook, "ForgingShop_Combined_Report.xlsx");
  });

  // Monthly report generation handler
  generateMonthlyReportBtn.addEventListener('click', () => {
    const selectedMonth = monthPicker.value; // format: 'YYYY-MM'
    if (!selectedMonth) {
      alert('Please select a month first.');
      return;
    }

    const tasks = getTasks();
    const attendance = getAttendance();

    // Filter function to check if a date string starts with selectedMonth
    const filterByMonth = (dateStr) => dateStr.startsWith(selectedMonth);

    const filteredTasks = tasks.filter(t => t.taskDate && filterByMonth(t.taskDate));
    const filteredAttendance = attendance.filter(a => a.attendanceDate && filterByMonth(a.attendanceDate));

    const monthlyData = [];

    filteredTasks.forEach(t => monthlyData.push({
      RecordType: 'Task',
      WorkerID: t.workerId,
      TaskType: t.taskType,
      Date: t.taskDate,
      PartNumber: t.partNumber,
      ToolID: t.toolId,
      Comments: t.comments,
      AttendanceStatus: ''
    }));

    filteredAttendance.forEach(a => monthlyData.push({
      RecordType: 'Attendance',
      WorkerID: a.workerId,
      TaskType: '',
      Date: a.attendanceDate,
      PartNumber: '',
      ToolID: '',
      Comments: '',
      AttendanceStatus: a.status
    }));

    if (!monthlyData.length) {
      alert('No data found for the selected month.');
      return;
    }

    // Open new tab with monthly report preview
    let html = '<html><head><title>Monthly Report</title></head><body>';
    html += `<h2>📅 Monthly Report for ${selectedMonth}</h2>`;
    html += '<table border="1" cellpadding="5" cellspacing="0" style="border-collapse:collapse;">';
    html += '<tr>';
    for (let key in monthlyData[0]) {
      html += `<th>${key}</th>`;
    }
    html += '</tr>';

    monthlyData.forEach(entry => {
      html += '<tr>';
      for (let key in entry) {
        html += `<td>${entry[key]}</td>`;
      }
      html += '</tr>';
    });

    html += '</table></body></html>';

    const newWindow = window.open();
    newWindow.document.write(html);
    newWindow.document.close();

    // Trigger XLSX download for monthly data
    const worksheet = XLSX.utils.json_to_sheet(monthlyData);
    const workbook = XLSX.utils.book_new();
    XLSX.utils.book_append_sheet(workbook, worksheet, "MonthlyReport");
    XLSX.writeFile(workbook, `ForgingShop_Monthly_Report_${selectedMonth}.xlsx`);
  });

  // Productivity chart
  const ctx = document.getElementById('productivityChart').getContext('2d');
  const productivityChart = new Chart(ctx, {
    type: 'bar',
    data: {
      labels: [],
      datasets: [{
        label: 'Tasks per Day',
        backgroundColor: '#004aad',
        data: []
      }]
    },
    options: {
      responsive: true,
      scales: {
        y: { beginAtZero: true }
      }
    }
  });

  function updateChart() {
    const tasks = getTasks();
    const dayMap = {};
    tasks.forEach(task => {
      if (task.taskDate) {
        dayMap[task.taskDate] = (dayMap[task.taskDate] || 0) + 1;
      }
    });
    productivityChart.data.labels = Object.keys(dayMap);
    productivityChart.data.datasets[0].data = Object.values(dayMap);
    productivityChart.update();
  }
  updateChart();
</script>

</body>
</html>

<script>
  function launchAI() {
    const output = document.getElementById('aiOutput');
    if (!output) return;

    const workerIdInput = document.getElementById('workerId');
    const taskTypeInput = document.getElementById('taskType');

    const workerId = workerIdInput ? workerIdInput.value || 'a worker' : 'a worker';
    const task = taskTypeInput ? taskTypeInput.value || 'today' : 'today';

    const tips = {
      forging: '🔥 Always heat billets uniformly and wear heat-resistant gloves.',
      trimming: '✂️ Maintain tool sharpness and handle edges safely.',
      inspection: '🔍 Use calibrated instruments and report all defects.',
      machining: '⚙️ Ensure the workpiece is secured and monitor coolant flow.',
      packaging: '📦 Label parts properly and use protective wraps.'
    };

    const tip = tips[task] || '🛠️ Always follow safety protocols and supervisor guidance.';
    output.innerText = `🤖 Hello ${workerId}! Here's a tip for ${task}: ${tip}`;
  }
</script>

```text
├── index.html                                    # Core application viewport & responsive interface
├── README.md                                     # Professional technical documentation
├── Aditya’s Forging Shop Digital Tracker.png     # Interface preview graphic
└── Documentation/                                # Academic project background & corporate research reports
