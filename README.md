# Google Images Scraper 🖼️

A Python-based web scraper that automatically downloads images from Google Images using Selenium WebDriver.

## 🚀 Features

- Automated Google Images searching
- Dynamic page scrolling
- Duplicate image detection
- Automatic image downloading
- Custom file naming
- Error handling for failed downloads
- Configurable download limits

## 🛠️ Requirements

- Python 3.x
- Selenium WebDriver
- Chrome WebDriver
- Pillow (PIL)
- Requests

## 📦 Installation

1. Install required Python packages:
```bash
pip install selenium pillow requests
```

2. Download ChromeDriver:
   - Visit [ChromeDriver Downloads](https://sites.google.com/chromium.org/driver/)
   - Download the version matching your Chrome browser
   - Place the executable in your project directory

3. Clone the repository:
```bash
git clone https://github.com/yourusername/google-images-scraper.git
cd google-images-scraper
```

## 🔧 Configuration

Update the `PATH` variable in the script to point to your ChromeDriver location:
```python
PATH = "path/to/your/chromedriver.exe"
```

## 💻 Usage

```python
# Initialize the WebDriver
wd = webdriver.Chrome(PATH)

# Get image URLs (parameters: webdriver, delay in seconds, max images)
urls = get_images_from_google(wd, 1, 6)

# Download images
for i, url in enumerate(urls):
    download_image("imgs/", url, str(i) + ".jpg")
```

## 🔍 Main Functions

### `get_images_from_google()`
```python
def get_images_from_google(wd, delay, max_images):
    """
    Scrapes Google Images for image URLs
    
    Parameters:
    wd (WebDriver): Selenium WebDriver instance
    delay (int): Time to wait between actions
    max_images (int): Maximum number of images to scrape
    
    Returns:
    set: Collection of unique image URLs
    """
```

### `download_image()`
```python
def download_image(download_path, url, file_name):
    """
    Downloads an image from a URL
    
    Parameters:
    download_path (str): Directory to save images
    url (str): Image URL
    file_name (str): Name for saved file
    """
```

## ⚠️ Important Notes

1. **Rate Limiting**: Add appropriate delays to avoid being blocked
2. **Terms of Service**: Ensure compliance with Google's ToS
3. **Error Handling**: Script includes basic error handling for failed downloads
4. **File Management**: Creates 'imgs' directory if it doesn't exist
5. **Browser Sessions**: Properly closes browser session after completion

## 🔒 Legal Considerations

- Respect website terms of service
- Consider rate limiting and robot policies
- Be mindful of image copyright and usage rights
- Use responsibly and ethically

## 🐛 Troubleshooting

1. **ChromeDriver Issues**:
   - Ensure ChromeDriver version matches Chrome browser
   - Verify PATH is correctly set
   - Check executable permissions

2. **Download Failures**:
   - Check internet connection
   - Verify write permissions in download directory
   - Review error messages in console

3. **Selenium Errors**:
   - Update Selenium to latest version
   - Check for stale elements
   - Increase delay between actions

## 🔄 Future Enhancements

- Add support for other browsers
- Implement custom search queries
- Add image size filtering
- Include batch processing
- Add proxy support
- Implement concurrent downloads

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📜 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## ⚡ Performance Tips

1. Adjust delay values based on connection speed
2. Use appropriate max_images value to avoid timeouts
3. Consider implementing parallel downloads
4. Monitor memory usage with large image sets

## 📧 Support

For issues and feature requests, please create an issue in the GitHub repository.

---
Made with ❤️ using Python and Selenium
