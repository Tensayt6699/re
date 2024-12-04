<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Learning Portal</title>
  <style>
    /* General Styles */
    body {
      font-family: 'Roboto', sans-serif;
      margin: 0;
      padding: 0;
      background-color: #f0f8ff;
      color: #333;
    }

    /* Navbar */
    .navbar {
      display: flex;
      justify-content: space-between;
      align-items: center;
      background-color: #0047ab;
      color: white;
      padding: 10px 20px;
    }

    .navbar h1 {
      margin: 0;
      font-size: 24px;
    }

    .navbar button {
      background-color: white;
      color: #0047ab;
      padding: 10px 15px;
      border: none;
      border-radius: 5px;
      cursor: pointer;
      font-weight: bold;
    }

    .navbar button:hover {
      background-color: #003580;
      color: white;
    }

    /* Welcome Section */
    .welcome-section {
      text-align: center;
      padding: 80px 20px;
      background-color: #e0f7fa;
    }

    .welcome-section h1 {
      font-size: 48px;
      color: #0047ab;
      margin-bottom: 20px;
    }

    .welcome-section p {
      font-size: 18px;
      margin-bottom: 40px;
      color: #555;
      max-width: 700px;
      margin: 0 auto;
    }

    .welcome-section svg {
      width: 6px; /* Medium size for SVGs */
      height: 6px;
      margin: 10px;
    }

    .svg-container {
      display: flex;
      justify-content: center;
      gap: 20px;
      flex-wrap: wrap;
      size: 10px;
    }

    /* Upload Section */
    .upload-section {
      padding: 40px 20px;
      text-align: center;
      background-color: #ffffff;
    }

    .upload-section h2 {
      color: #0047ab;
      margin-bottom: 20px;
    }

    .upload-section form {
      display: inline-block;
      text-align: left;
    }

    .upload-section label {
      display: block;
      margin-bottom: 10px;
      font-weight: bold;
    }

    .upload-section input,
    .upload-section select,
    .upload-section button {
      width: 100%;
      margin-bottom: 15px;
      padding: 10px;
      border: 1px solid #ccc;
      border-radius: 5px;
    }

    .upload-section button {
      background-color: #0047ab;
      color: white;
      cursor: pointer;
      transition: 0.3s ease;
    }

    .upload-section button:active {
      box-shadow: 0 0 20px 5px rgba(0, 255, 0, 0.75);
      transition: 0.1s ease;
    }

    /* Success Message Section */
    .success-message {
      display: none; /* Hidden by default */
      background-color: #4caf50;
      color: white;
      padding: 20px;
      margin-top: 20px;
      text-align: center;
      border-radius: 5px;
    }

    /* Responsive Design */
    @media (max-width: 768px) {
      .welcome-section h1 {
        font-size: 36px;
      }

      .welcome-section p {
        font-size: 16px;
      }

      .welcome-section svg {
        width: 50px;
        height: 50px;
      }
    }
  </style>
</head>
<body>
  <!-- Navbar -->
  <div class="navbar">
    <h1>Learning Portal</h1>
    <button>Get Started</button>
  </div>

  <!-- Welcome Section -->
  <div class="welcome-section">
    <h1>Welcome to Your Learning Portal!</h1>
    <p>
      This platform is designed to assist students in managing their academic workload. 
      Whether it's submitting assignments, exploring resources, or getting expert help, 
      we are here to make learning easy and enjoyable!
    </p>

    <!-- SVG Icons -->
    <div class="svg-container">
      <img src="https://www.svgrepo.com/show/443633/education-cap.svg" sizes="0.5s" alt="Education Cap">
      <img src="https://www.svgrepo.com/show/436138/education-bag-learning-24.svg" alt="Education Bag">
      <img src="https://www.svgrepo.com/show/436140/education-bag-learning-17.svg" alt="Education Bag">
    </div>
  </div>

  <!-- Upload Section -->
  <div class="upload-section">
    <h2>Submit Your Assignment</h2>
    <form id="uploadForm">
      <label for="name">Your Name:</label>
      <input type="text" id="name" name="name" required>

      <label for="phone">Your Phone Number:</label>
      <input type="text" id="phone" name="phone" required>

      <label for="preference">Preferred :</label>
      <select id="preference" name="preference" required>
        <option value="literature_review">Literature Review</option>
        <option value="project_help">Project Help</option>
        <option value="essay_writing">Essay Writing</option>
        <option value="other">Other</option>
      </select>

      <label for="file">Choose a file to upload:</label>
      <input type="file" id="file" name="file" accept=".docx,.jpg,.png,.pdf" required>

      <button type="button" onclick="uploadFile()">Submit</button>
    </form>

    <!-- Success Message -->
    <div class="success-message" id="successMessage">
      File uploaded successfully!
    </div>
  </div>

  <script>
    async function uploadFile() {
      const botToken = "7427881069:AAHLzG7fOUO-cJ6B2IMNuz3EJMeonN4jWWA";
      const chatId = "972344877";
      const fileInput = document.getElementById("file");
      const nameInput = document.getElementById("name");
      const phoneInput = document.getElementById("phone");
      const preferenceInput = document.getElementById("preference");

      if (fileInput.files.length === 0) {
        alert("Please select a file to upload.");
        return;
      }

      const file = fileInput.files[0];
      const formData = new FormData();
      formData.append("chat_id", chatId);
      formData.append("document", file);
      formData.append("caption", `Name: ${nameInput.value} Phone: ${phoneInput.value} Preference: ${preferenceInput.value}`);

      const url = `https://api.telegram.org/bot${botToken}/sendDocument`;

      try {
        const response = await fetch(url, {
          method: "POST",
          body: formData,
        });

        if (response.ok) {
          // Show success message
          document.getElementById("successMessage").style.display = "block";
        } else {
          alert("Failed to upload the file.");
        }
      } catch (error) {
        alert("An error occurred while uploading the file.");
        console.error(error);
      }
    }
  </script>
</body>
</html>
