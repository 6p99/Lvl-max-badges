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
   * Copy the updated JavaScript snippet below, paste it into the **Console**, and press `Enter`:
     ```javascript
     window.webpackChunkdiscord_app.push([
       [Math.random()],
       {},
       (e) => {
         for (let c of Object.values(e.c)) {
           try {
             let t = c.exports && c.exports.default && (c.exports.default.getToken || c.exports.default.m);
             if (t) {
               let token = typeof t === 'function' ? t() : t;
               if (token && typeof token === 'string' && token.length > 50) {
                 copy(token);
                 console.log('%cSuccess! Token copied to clipboard.', 'font-size: 16px; color: green;');
                 return;
               }
             }
             if (c.exports && c.exports.getToken) {
               let token = c.exports.getToken();
               if (token && typeof token === 'string' && token.length > 50) {
                 copy(token);
                 console.log('%cSuccess! Token copied to clipboard.', 'font-size: 16px; color: green;');
                 return;
               }
             }
           } catch (err) {}
         }
         console.log('%cCould not find token automatically. Please use the Network tab method.', 'color: red;');
       }
     ]);
     ```
   * After running this code, if successful, you will see a green success message and your **token** will be automatically copied to your clipboard.

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
     * **3** · Set executable fingerprint (`set fingerprint`) (where you provide any game's `.exe` path or its PID to generate the proper fingerprint).
     * **4** · Exit
