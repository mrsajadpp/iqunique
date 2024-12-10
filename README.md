
# Geckodriver Installation Guide for Ubuntu 18.04.2 LTS

This documentation will guide you through the process of installing Geckodriver for Selenium on **Ubuntu 18.04.2 LTS**. Geckodriver is required to automate Firefox with Selenium WebDriver.

## Prerequisites

- **Ubuntu 18.04.2 LTS**
- **Firefox** (Pre-installed)
- **Python** (if using Selenium with Python)

### Step 1: Install Firefox
Ensure that Firefox is installed on your system:

```bash
sudo apt update
sudo apt install firefox
```

### Step 2: Download Geckodriver

1. **Navigate to the Geckodriver Releases Page**  
   Go to the official [Geckodriver releases page](https://github.com/mozilla/geckodriver/releases) to find the latest version. Alternatively, you can use the terminal to download the latest release directly:

   ```bash
   wget https://github.com/mozilla/geckodriver/releases/latest/download/geckodriver-v0.33.0-linux64.tar.gz
   ```

   Replace `v0.33.0` with the latest version number if needed.

2. **Extract the Geckodriver Archive**  
   Extract the downloaded archive:

   ```bash
   tar -xvzf geckodriver-v0.33.0-linux64.tar.gz
   ```

3. **Move Geckodriver to a System Path**  
   To make Geckodriver available globally, move it to `/usr/local/bin`:

   ```bash
   sudo mv geckodriver /usr/local/bin/
   ```

### Step 3: Verify Installation

To verify that Geckodriver is correctly installed, run the following command:

```bash
geckodriver --version
```

This command should output the installed version number.

### Step 4: Using Geckodriver with Selenium and other packages

If you're using Selenium with Python, ensure the `selenium` library is installed:

```bash
pip3 install selenium Faker playwright
```

Here’s a basic Python script to test Geckodriver with Selenium:

```python
from selenium import webdriver

driver = webdriver.Firefox()
driver.get("https://www.mozilla.org")
print(driver.title)
driver.quit()
```

This script opens the Mozilla website using Firefox with Selenium. If everything is set up correctly, it will print the page title and then close the browser.

## Additional Notes

- **Permissions**: If you encounter permission issues when running Geckodriver, make sure it’s executable by the current user:

  ```bash
  chmod +x /usr/local/bin/geckodriver
  ```

- **Updating Geckodriver**: To update Geckodriver, visit the Geckodriver releases page, download the latest version, extract it, and replace the existing `geckodriver` binary at `/usr/local/bin`.
