# Web Crawler in Java

## Overview
This project is a basic web crawler implemented in Java using the **Jsoup** library. It performs depth-first search (DFS) to crawl web pages starting from a given URL, extracts hyperlinks, and saves the results to a file. The crawler avoids revisiting URLs and respects a maximum depth to limit recursion.

---

## Features
- **Depth Limitation**: Limits crawling to a maximum specified depth to prevent excessive crawling.
- **Duplicate Handling**: Keeps track of visited URLs to avoid revisiting.
- **Output File**: Saves the crawl results to a structured file.
- **Readable Output**: Prints detailed crawl information to the console and the output file.

---

## Prerequisites
1. **Java Development Kit (JDK)**: Version 8 or later.
2. **Jsoup Library**: Download or include the Jsoup dependency in your project.

---

## How to Use

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/web-crawler-java.git
cd web-crawler-java
```

### 2. Set Up Dependencies
- Add the Jsoup library to your project.
  If you're using Maven, add this dependency to your `pom.xml`:
  ```xml
  <dependency>
      <groupId>org.jsoup</groupId>
      <artifactId>jsoup</artifactId>
      <version>1.15.4</version>
  </dependency>
  ```

### 3. Modify Parameters
- Open the `webcrawler.java` file.
- Update the following:
  - `startUrl`: Replace with the URL you want to crawl.
  - `MAX_DEPTH`: Set the desired depth for crawling.
  - `outputFilePath`: Specify the file path where results will be saved.

### 4. Compile and Run
```bash
javac webcrawler.java
java webcrawler
```

---

## Output Format
The crawler saves the results in a text file with the following structure:

### Example Output
```
Starting crawl at: https://example.com

=== Page Title: Example Domain ===
Page URL: https://example.com

Links:
    - title: More Information | URL: https://www.iana.org/domains/example

--- End of Page ---
```

---

## Code Structure

### **Main Method**
- Initializes the crawl parameters.
- Writes the starting point to the output file.
- Calls the `crawl` method to begin the process.

### **crawl Method**
- **Base Cases**: Stops crawling when the maximum depth is reached or if a URL has already been visited.
- **HTML Parsing**: Fetches the page content and extracts hyperlinks using Jsoup.
- **Recursion**: Crawls each unvisited link, incrementing the depth.
- **Error Handling**: Logs errors for inaccessible pages.

---

## Improvements
Suggestions for future enhancements:
- **Multithreading**: Parallelize the crawling process to improve performance.
- **Error Handling**: Implement retries for failed connections and handle HTTP status codes.
- **Dynamic Inputs**: Accept `startUrl` and `MAX_DEPTH` as command-line arguments.
- **Advanced Extraction**: Extract additional content like images, meta tags, etc.

---

## License
This project is licensed under the MIT License. See the `LICENSE` file for details.

---

## Contributing
Contributions are welcome! Feel free to open issues or submit pull requests to enhance this project.

