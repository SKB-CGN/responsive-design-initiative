# Developer Guide: Optimizing for Responsive Design

To ensure your adapter configuration looks great across various device screens, it’s helpful to quickly switch between different screen resolutions during development. By using the minimum width for each dimension range, you can ensure the layout fits well within the range until the next one starts.

Follow these steps to set up device presets and optimize your workflow:  
**Steps:**

    1. **Open the Configuration of your adapter.**
    2. **Open browser developer tools:**
        - Press F12 in Chrome or Firefox.
    3. **Enable Device Toolbar:**
        - Press Ctrl + Shift + M.
    4. **Edit Device Presets:**
        - Open the device dimension presets and click on "Edit".
    5. **Add the following entries to create the ioBroker presets:**
        - xs ioBroker: Width: 360, Height: 640
        - sm ioBroker: Width: 600, Height: 960
        - md ioBroker: Width: 900, Height: 960
        - lg ioBroker: Width: 1200, Height: 960
        - xl ioBroker: Width: 1536, Height: 960

Now you can easily switch between these profiles during development.

**Pro Tip:** Remove any unused profiles from the dropdown to keep your workflow clean and fast.
