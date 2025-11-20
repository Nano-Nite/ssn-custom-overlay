# Project Summary & README

## Overview

This README summarizes all the fixes, improvements, and steps we've worked on regarding your chat UI, including message rendering, avatar alignment, rapid message limiting, font changes, and UI issues.

## Features Implemented

### 1. **Message Rendering Logic**

* Messages are displayed on left/right depending on whether the sender is user or bot.
* Avatars now correctly switch based on sender instead of only shifting position.
* Layout uses flexbox to align messages cleanly.

### 2. **Avatar Fixes**

* Ensured avatar image `src` changes dynamically based on `message.isUser`.
* Prevented issue where avatar only shifted position without changing images.

### 3. **Font Customization**

* Added support for custom fonts via CSS.
* Ensured both message bubble and entire chat area inherit the new font.

### 4. **Rapid Message Limit Fix**

* Fixed bug where rapid messages still exceeded the max allowed.
* Implemented a proper cooldown or queue mechanism.
* Ensured next message appears correctly after limit cooldown.

### 5. **Message Flow Fixes**

* Addressed issue where next message failed to appear after sending a rapid sequence.
* Added stable rendering logic so messages are pushed reliably to UI.

## Example Message Component

```jsx
<img
  className="avatar"
  src={message.isUser ? userAvatar : botAvatar}
  alt="avatar"
/>
```

## Example CSS

```css
.chat-container {
  font-family: 'YourCustomFont', sans-serif;
}

.message {
  display: flex;
  gap: 8px;
  margin-bottom: 10px;
}

.message.user {
  flex-direction: row-reverse;
}

.avatar {
  width: 32px;
  height: 32px;
  border-radius: 50%;
}
```

## Notes

* All layout bugs relating to avatar shift and message alignment should now be resolved.
* All message flow issues after rapid-fire sending have been addressed.
* Font customization is global and stable.

## Next Steps

If needed, we can:

* Add message status (sent, delivered, read).
* Animate message bubbles.
* Add typing indicator.

---

If you want this README auto-filled with your actual filenames, structure, or specific code blocks, just upload the files or paste the components here.
