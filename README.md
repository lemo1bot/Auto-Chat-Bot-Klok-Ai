# Auto-Chat-Bot-Klok-Ai

// Function to display a "Follow on Twitter" pop-up warning bar
function displayTwitterFollowWarning() {
    const warningBar = document.createElement('div');
    
    // Styling the warning bar to be fixed at the top of the window
    warningBar.style.position = 'fixed';
    warningBar.style.top = '0';
    warningBar.style.left = '0';
    warningBar.style.width = '100%';
    warningBar.style.backgroundColor = '#ffcc00';
    warningBar.style.color = '#000';
    warningBar.style.textAlign = 'center';
    warningBar.style.padding = '10px';
    warningBar.style.zIndex = '10000'; // Ensure it's above all other elements

    // Adding text and the "Follow" button
    warningBar.innerHTML = `
        <span style="font-size: 16px; font-weight: bold;">Follow @ROSLA_AHEMED on Twitter!</span>
        <a href="https://twitter.com/ROSLA_AHEMED" target="_blank" style="background-color: #1DA1F2; color: white; padding: 10px 20px; border: none; border-radius: 5px; cursor: pointer; margin-left: 20px; text-decoration: none;">
            Follow Now
        </a>
        <button id="closeWarningBar" style="margin-left: 20px; padding: 5px 10px; background-color: red; color: white; border: none; border-radius: 3px; cursor: pointer;">Close</button>
    `;

    // Append the warning bar to the document body
    document.body.appendChild(warningBar);

    // Close button functionality
    document.getElementById('closeWarningBar').addEventListener('click', function() {
        warningBar.style.display = 'none'; // Hide the warning bar when closed
    });
}

// Function to automatically send chat messages
(function() {
    const questions = [
        "How do I create an account?",
        "What are the pricing plans for KlokApp?",
        "Can I use KlokApp for team collaboration?",
        "How do I connect KlokApp to my calendar?",
        "What security measures does KlokApp have?",
        "How do I enable notifications?",
        "Can I sync KlokApp with Google Drive?",
        "What are the best practices for using KlokApp efficiently?",
        "How do I retrieve deleted data?",
        "Does KlokApp support integrations with third-party tools?",
        "Is there a mobile app available for KlokApp?",
        "How can I track my productivity using KlokApp?",
        "Are there keyboard shortcuts available?",
        "Can I generate reports in KlokApp?",
        "How does KlokApp handle offline mode?",
        "Where can I find user documentation?",
        "Does KlokApp offer dark mode?",
        "How do I set up automated reminders?",
        "Can I manage multiple projects in KlokApp?",
        "What happens if I exceed my plan’s limit?",
        "How do I transfer ownership of an account?",
        "Does KlokApp offer data backups?",
        "How do I personalize my dashboard?",
        "Is there a community forum for KlokApp users?",
        "How do I change the theme in KlokApp?",
        "What are some tips for maximizing productivity with KlokApp?",
        "Can I export my task list?",
        "Is KlokApp available in multiple languages?",
        "How do I recover my account if I get locked out?",
        "Can I set goals inside KlokApp?",
        "How does KlokApp handle customer feedback?",
        "What is the difference between free and premium plans?",
        "Does KlokApp support two-factor authentication?",
        "How do I enable AI-powered features in KlokApp?",
        "Can I share my KlokApp tasks with others?",
        "How do I troubleshoot login issues?",
        "Does KlokApp offer customer support 24/7?",
        "How do I access my KlokApp analytics?",
        "Can I create recurring tasks in KlokApp?",
        "What happens if my subscription expires?",
        "Does KlokApp support time tracking?",
        "How do I add tags to my tasks?",
        "Can I import tasks from another app?",
        "What are some common issues users face?",
        "How do I update my profile settings?",
        "Can I set different priorities for tasks?",
        "Does KlokApp have a referral program?",
        "How do I contact the support team?",
        "Can I integrate KlokApp with Trello or Asana?",
        "Where can I find video tutorials on KlokApp?",
        "Does KlokApp allow for guest access?",
        "What are the upcoming features for KlokApp?"
    ];

    let questionIndex = 0;

    // Function to send a message
    function sendMessage(question) {
        const textarea = document.querySelector('textarea[placeholder="Ask me anything "]');
        const sendButton = document.querySelector('button[type="submit"]');
        
        if (textarea && sendButton) {
            textarea.value = question;
            textarea.dispatchEvent(new Event('input', { bubbles: true }));
            sendButton.click();
        } else {
            console.log('Chat input field or send button not found.');
        }
    }

    // Function to ask the next question with a 30-second delay
    function askNextQuestion() {
        if (questionIndex < questions.length) {
            sendMessage(questions[questionIndex]);
            questionIndex++;
            setTimeout(askNextQuestion, 30000); // Wait 30 seconds between questions
        }
    }

    // Start asking questions
    askNextQuestion();

    // Show Twitter follow pop-up after 30 seconds
    setTimeout(displayTwitterFollowWarning, 30000);

})();
