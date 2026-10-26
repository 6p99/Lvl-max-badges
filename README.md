# Guide to Running the Discord Game and Playtime Spoofer

---

### **Prerequisites:**
1. You must have **Python** installed on your system.
2. The spoofer script files (including `script.py`) must be set up in your working directory.

---

### **Step-by-Step Instructions:**

1. **Open Discord Developer Tools:**
   * Open the Discord desktop app or use Discord in your web browser.
   * Open the **Developer Tools / Console** by pressing `Ctrl + Shift + I` and navigating to the **Console** tab.

2. **Get Your Cookie:**
   * Copy the following snippet, paste it into the **Console**, and press `Enter` to copy your cookie directly to your clipboard:
     ```javascript
     copy(document.cookie)
     ```

3. **Get Your Token:**
   * Copy the JavaScript snippet below, paste it into the **Console**, and press `Enter`:
     ```javascript
     window.webpackChunkdiscord_app.push([
       [Math.random()],
       {},
       req => {
         if (!req.c) return;
         for (const m of Object.keys(req.c)
           .map(x => req.c[x].exports)
           .filter(x => x)) {
           if (m.default && m.default.getToken !== undefined) {
             return copy(m.default.getToken());
           }
           if (m.getToken !== undefined) {
             return copy(m.getToken());
           }
         }
       },
     ]);
     console.log('%cWorked!', 'font-size: 50px');
     console.log(`%cYou now have your token in the clipboard!`, 'font-size: 16px');
     ```
   * After running this code, your **token** will be automatically copied to your clipboard.

4. **Run the Script via Python:**
   * Open your command line (`CMD` or `PowerShell`) inside the script's folder.
   * Run the script using the following command:
     ```bash
     python script.py
     ```
   * When prompted upon startup, paste your **Token** and then your **Cookie** that you copied in the previous steps.

5. **Using the Menu:**
   * Once your credentials are verified and games are loaded, the main menu will appear with the following options:
     * **1** · Claim games (`claim games`)
     * **2** · Refresh authentication (`refresh auth`)
     * **3** · Set executable fingerprint (`set fingerprint`)
     * **4** · Exit
