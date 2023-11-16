## Question 1

- **webbrowser:** Provides a high-level interface to allow displaying web-based documents to users. It's typically used for opening a web browser to a specific page.

- **requests:** A library for making HTTP requests. It allows sending HTTP requests and receiving responses, making it easy to interact with web services and APIs.

- **bs4 (Beautiful Soup):** A library for pulling data out of HTML and XML files. It provides Pythonic idioms for iterating, searching, and modifying the parse tree.

- **selenium:** A web testing library that allows automating browser actions. It is often used for web scraping and testing web applications.

## Question 2

- The object returned by `requests.get()` is a Response object.
- To access the downloaded content as a string value, you can use the `.text` attribute of the Response object.

## Question 3

- The `requests` method that checks if the download worked is `raise_for_status()`. It raises an HTTPError for bad responses (e.g., 404 or 500).

## Question 4

- You can get the HTTP status code of a requests response using the `.status_code` attribute.

## Question 5

- To save a requests response to a file, you can use the following code:
  ```python
  with open('filename.extension', 'wb') as file:
      file.write(response.content)


## Question 6

- The keyboard shortcut for opening a browser’s developer tools is typically `Ctrl+Shift+I` for Windows/Linux or `Cmd+Opt+I` for Mac.

## Question 7

- To view the HTML of a specific element in the developer tools, you can right-click on the element on the webpage and select "Inspect" or "Inspect Element."

## Question 8

- The CSS selector string to find the element with an id attribute of main is `#main`.

## Question 9

- The CSS selector string to find elements with a CSS class of highlight is `.highlight`.

## Question 10

- The CSS selector string to find all `<div>` elements inside another `<div>` element is `div > div`.

## Question 11

- The CSS selector string to find the `<button>` element with a value attribute set to favorite is `button[value='favorite']`.

## Question 12

- If you have a Beautiful Soup Tag object stored in the variable `spam`, you can get the string 'Hello, world!' using `spam.text`.

## Question 13

- To store all the attributes of a Beautiful Soup Tag object in a variable named `linkElem`, you can use `linkElem.attrs`.

## Question 14

- The correct way to import the selenium module is:
  ```python
  from selenium import webdriver


## Question 15

- The `find_element_*` methods in Selenium return the first matching element, while the `find_elements_*` methods return a list of all matching elements.

## Question 16

- Selenium's WebElement objects have `click()`, `send_keys()`, and other methods for simulating mouse clicks and keyboard keys.

## Question 17

- An easier way to submit a form with Selenium is to use the `.submit()` method on the form element or the form's submit button.

## Question 18

- To simulate clicking a browser’s Forward, Back, and Refresh buttons with Selenium, you can use:
  ```python
  driver.forward()
  driver.back()
  driver.refresh()

## Practice Projects

### Command Line Emailer

```python
import sys
import time
from selenium import webdriver
from selenium.webdriver.common.keys import Keys

recipient = sys.argv[1]
subject = sys.argv[2]
message = sys.argv[3]

browser = webdriver.Firefox()
browser.get('https://accounts.google.com/signin/v2/identifier?service=mail')
id_elem = browser.find_element_by_name('identifier')
id_elem.send_keys('example@gmail.com')
id_elem.send_keys(Keys.ENTER)
time.sleep(3)

pass_elem = browser.find_element_by_name('password')
pass_elem.send_keys('123456')
pass_elem.send_keys(Keys.ENTER)
time.sleep(5)

compose_elem = browser.find_element_by_class_name('z0')
compose_elem.click()
time.sleep(5)

to_elem = browser.find_element_by_name('to')
to_elem.send_keys(recipient)

subject_elem = browser.find_element_by_name('subjectbox')
subject_elem.send_keys(subject)

subject_elem.send_keys(Keys.TAB + message + Keys.TAB + Keys.ENTER)
time.sleep(5)

browser.quit()
```

### Image Site Downloader

```python
import os
import requests
import bs4

def image_downloader(extension):
    """Search for and download all images of the argument type from Imgur."""
    url = 'http://imgur.com/search?q=' + search + ' ext:' + extension
    os.makedirs('/home/Kunal/Downloads/auto', exist_ok=True)

    res = requests.get(url)
    res.raise_for_status()

    soup = bs4.BeautifulSoup(res.text, 'html.parser')
    image_elem = soup.select('.post > .image-list-link img')

    for i, image in enumerate(image_elem):
        image_url_s = 'https:' + image_elem[i].get('src')
        image_url = image_url_s[: -5] + '.' + extension

        print('Downloading image .....{}'.format(image_url))
        res = requests.get(image_url)
        res.raise_for_status()
        image_file = open(os.path.join('/home/Kunal/Downloads/auto',
                                        os.path.basename(image_url)), 'wb')
        for chunk in res.iter_content(1000000):
            image_file.write(chunk)
        image_file.close()

    return len(image_elem)


search = input('Enter a term for searching: ')
downloaded = image_downloader('jpg') + image_downloader('png')

if downloaded == 0:
    print('No images were found.')

else:
    print('All ' + str(downloaded) + ' files successfully downloaded.')
```

### 2048

```python
from selenium import webdriver
from selenium.webdriver.common.keys import Keys

browser = webdriver.Firefox()
browser.get('https://gabrielecirulli.github.io/2048/')
html_elem = browser.find_element_by_tag_name('html')

while True:
    html_elem.send_keys(Keys.UP)
    html_elem.send_keys(Keys.RIGHT)
    html_elem.send_keys(Keys.DOWN)
    html_elem.send_keys(Keys.LEFT)
```

### Link Verification

```python
import requests
import bs4

url = input('Enter the URL: ')
res = requests.get(url)
res.raise_for_status()

soup = bs4.BeautifulSoup(res.text, 'html.parser')
links = soup.select('a')
fof = []

for link in links:
    try:
        unmade_url = link['href']
        if unmade_url.startswith('http'):
            to_check = unmade_url

        elif unmade_url.startswith('//'):
            to_check = 'https:' + unmade_url

        elif unmade_url.startswith('#'):
            to_check = url + unmade_url

        result = requests.get(to_check)

        if result.status_code == 404:
            fof.append(to_check)

    except:
        pass

print('These ' + str(len(fof)) + ' returned error 404:')
print('\n'.join(fof))
```