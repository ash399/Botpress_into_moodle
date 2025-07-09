# ✨ Botpress Chatbot Integration with Moodle ✨

This guide provides comprehensive, step-by-step instructions on how to seamlessly integrate your [Botpress](https://botpress.com/) chatbot into your [Moodle](https://moodle.org/) learning management system using its shareable link and embed code. Enhance your Moodle site with interactive AI!

---

## 📚 Table of Contents

* [Prerequisites](#-prerequisites)
* [Integration Steps](#-integration-steps)

  * [Step 1: Access Moodle's Additional HTML Settings](#step-1-access-moodles-additional-html-settings)
  * [Step 2: Embed the Botpress Webchat Code](#step-2-embed-the-botpress-webchat-code)
  * [Step 3: Customize Webchat Placement with CSS](#step-3-customize-webchat-placement-with-css)
  * [Step 4: Purge Moodle Cache](#step-4-purge-moodle-cache)
  * [Step 5: Test the Integration](#step-5-test-the-integration)
* [🖥️ Optional: Full-Screen Chatbot](#️-optional-full-screen-chatbot)
* [💡 Why Integrate a Chatbot?](#-why-integrate-a-chatbot)
* [🛠️ Troubleshooting](#️-troubleshooting)
* [✅ Summary of Key Actions](#-summary-of-key-actions)

---

## 📋 Prerequisites

Before you begin, ensure you have:

* ✅ Administrator access to your Moodle site.
* ✅ Your Botpress chatbot's shareable link and embed code (available in your Botpress cloud dashboard).

---

## 🚀 Integration Steps

### Step 1: Access Moodle's Additional HTML Settings

1. Log in to Moodle as an **Administrator**.
2. Navigate to:
   `Site Administration > Appearance > Themes > [Your Active Theme] > Additional HTML`
   Replace `[Your Active Theme]` with the actual name of your Moodle theme (e.g., `Boost`, `Classic`).

---

### Step 2: Embed the Botpress Webchat Code

Paste the following code in the **"Before BODY is closed"** section of the Additional HTML settings:

```html
<script src="https://cdn.botpress.cloud/webchat/v2.2/inject.js"></script>
<script src="https://files.bpcontent.cloud/2025/01/08/09/20250108090115-LGV0EJSE.js"></script>
```

> ⚠️ **Note**: The second script tag contains your **specific chatbot ID**. Make sure it matches the code provided in your Botpress dashboard.

Click **Save Changes**.

---

### Step 3: Customize Webchat Placement with CSS

To position the chatbot (e.g., bottom-right), add this CSS:

1. Navigate to:
   `Site Administration > Appearance > Themes > [Your Active Theme] > Advanced Settings`

2. Add the following CSS to the **"Raw SCSS"** or **"Custom CSS"** area:

```css
.bp-webchat {
    position: fixed;
    bottom: 20px;
    right: 20px;
    z-index: 9999;
    height: 600px;
    width: 400px;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
    border-radius: 15px;
    overflow: hidden;
}

.bp-webchat iframe {
    height: 100%;
    width: 100%;
    border: none;
    border-radius: 10px;
}
```

Click **Save Changes**.

---

### Step 4: Purge Moodle Cache

To apply the changes immediately:

1. Go to:
   `Site Administration > Development > Purge All Caches`

2. Click **Purge Caches** when prompted.

---

### Step 5: Test the Integration

1. Open your Moodle site in a new browser window.
2. The Botpress chatbot icon or window should now appear (default: bottom-right).
3. Interact with the chatbot to confirm it's working as expected.

---

## 🖥️ Optional: Full-Screen Chatbot

If you prefer a full-screen chatbot experience, replace the CSS in Step 3 with the following:

```css
.bp-webchat {
    position: fixed;
    top: 0;
    left: 0;
    height: 100vh;
    width: 100vw;
    z-index: 9999;
    border-radius: 0;
    box-shadow: none;
}
```

---

## 💡 Why Integrate a Chatbot?

* 🤖 **Instant Support**: 24/7 help for FAQs, navigation, and course guidance.
* 🎓 **Enhanced Engagement**: Deliver interactive learning and quizzes.
* 🧠 **Automation**: Resource suggestions, deadline reminders, and request handling.
* ⏳ **Reduced Admin Load**: Less repetitive work for teachers/admins.

---

## 🛠️ Troubleshooting

If something doesn’t work:

* **Check Console Errors**: Use developer tools (F12) → Console tab.
* **Verify Script Tags**: Confirm both `<script>` tags are correctly added.
* **Check CSS**: Look for typos or missing braces. Try default layout first.
* **Purge Again**: Sometimes Moodle needs another cache purge.
* **Inspect Elements**: Check if `.bp-webchat` is in the HTML structure.
* **Botpress Dashboard**: Ensure your bot is **published and active**.

---

## ✅ Summary of Key Actions

* ✔️ Add Botpress Webchat Code to Moodle
* ✔️ Customize Chatbot Position with CSS
* ✔️ Purge Moodle Cache
* ✔️ Test and Interact with the Bot

---

> 📬 For further customizations or help with advanced features like NLP integrations, database connections, or Moodle plugin development, feel free to open an issue or contact the maintainer.

---

Happy Chatbotting! 💬✨
