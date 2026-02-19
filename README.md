<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <!--<title>Colonist.io Drawing Tablet Fix</title>-->
</head>
<body style="font-family: Arial, sans-serif; line-height: 1.6; max-width: 800px; margin: 0 auto; padding: 20px;">

  <h1 align="center">🎲 Colonist.io Drawing Tablet Fix 🖊️</h1>

  <p>
      A lightweight <strong>Tampermonkey Userscript</strong> designed to restore full playability on 
      <a href="https://colonist.io" target="_blank">Colonist.io</a> for users playing with a drawing tablet 
      (e.g., Ugee, Wacom, Huion).
  </p>

  <hr>

  <h2>🔴 The Problem</h2>
  <p>
      When entering a match in Colonist, the game renders the board inside an HTML5 <code>&lt;canvas&gt;</code> element. 
      While standard UI buttons recognize pen taps, the game canvas often ignores them because drawing tablet drivers 
      (via Windows Ink) send <code>PointerEvents</code> instead of standard <code>MouseEvents</code>. This results in 
      being able to move the cursor, but being completely unable to click or interact with the board.
  </p>

  <h2>🟢 The Solution</h2>
  <p>
      This script acts as a middleware. It listens for interactions from a pen (<code>pointerdown</code>, <code>pointerup</code>) 
      and dynamically translates them into synthetic <code>mousedown</code> and <code>mouseup</code> events, fooling the 
      game engine into thinking a standard mouse is being used.
  </p>

  <h2>🛠️ Installation Instructions</h2>
  <ol>
      <li>Install a userscript manager browser extension like 
          <a href="https://www.tampermonkey.net/" target="_blank">Tampermonkey</a> or Violentmonkey.
      </li>
      <li>Create a new script in the extension dashboard.</li>
      <li>Copy and paste the entire content of <code>colonist-tablet-fix.user.js</code> from this repository.</li>
      <li>Save the script (Ctrl+S or Cmd+S).</li>
      <li>Refresh your Colonist.io page and enjoy playing with your tablet!</li>
  </ol>

  <h2>🤝 Contributing</h2>
  <p>
      Feel free to open an issue or submit a pull request if you notice bugs, especially regarding drag-and-drop actions 
      which might require further event mapping.
  </p>

</body>
</html>
