<!DOCTYPE html>
<html>
<head>
  <title>Job Portal UI</title>
  <style>
    body {
      font-family: Arial;
      padding: 20px;
      background: #f4f4f4;
    }

    h1 {
      color: #333;
    }

    #jobs {
      display: flex;
      flex-wrap: wrap;
      gap: 10px;
    }

    .card {
      background: white;
      padding: 15px;
      border-radius: 8px;
      width: 200px;
      box-shadow: 0 0 5px rgba(0,0,0,0.2);
    }

    input, button {
      margin: 5px;
      padding: 8px;
    }

    button {
      cursor: pointer;
      background: #007bff;
      color: white;
      border: none;
    }

    button:hover {
      background: #0056b3;
    }
  </style>
</head>
<body>

<h1>Job Portal</h1>

<input type="text" id="search" placeholder="Search jobs...">

<div id="jobs"></div>

<h2>Apply for Job</h2>
<form id="applyForm">
  <input type="text" id="name" placeholder="Your Name" required>
  <input type="number" id="jobId" placeholder="Job ID" required>
  <button type="submit">Apply</button>
</form>

<p id="message"></p>

<script>
  // "Server" data (simulated)
  let jobs = [
    { id: 1, title: "Frontend Developer", company: "ABC Tech" },
    { id: 2, title: "Backend Developer", company: "XYZ Solutions" },
    { id: 3, title: "UI Designer", company: "Creative Studio" }
  ];

  const jobsDiv = document.getElementById("jobs");
  const searchInput = document.getElementById("search");

  // Display jobs
  function displayJobs(jobList) {
    jobsDiv.innerHTML = "";
    jobList.forEach(job => {
      const div = document.createElement("div");
      div.className = "card";
      div.innerHTML = `
        <h3>${job.title}</h3>
        <p>${job.company}</p>
        <p><b>ID:</b> ${job.id}</p>
      `;
      jobsDiv.appendChild(div);
    });
  }

  // Initial load
  displayJobs(jobs);

  // Search filter
  searchInput.addEventListener("input", () => {
    const text = searchInput.value.toLowerCase();

    const filtered = jobs.filter(job =>
      job.title.toLowerCase().includes(text)
    );

    displayJobs(filtered);
  });

  // Apply form (simulated server response)
  document.getElementById("applyForm").addEventListener("submit", function(e) {
    e.preventDefault();

    const name = document.getElementById("name").value;
    const jobId = document.getElementById("jobId").value;

    if (!name || !jobId) {
      document.getElementById("message").innerText = "Fill all fields!";
      return;
    }

    const jobExists = jobs.find(j => j.id == jobId);

    if (!jobExists) {
      document.getElementById("message").innerText = "Invalid Job ID!";
      return;
    }

    // Simulated response
    document.getElementById("message").innerText =
      `Application submitted successfully for ${jobExists.title}`;
  });
</script>

</body>
</html>
