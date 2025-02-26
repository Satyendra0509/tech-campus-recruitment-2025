# Discussion.md

## Solutions Considered
### 1. **Loading Entire File into Memory**
- **Approach:** Read the entire log file into memory and use string operations to filter logs.
- **Issue:** Not feasible for large files (~1TB), as it would consume excessive memory and slow down processing.

### 2. **Line-by-Line Processing using Streams**
- **Approach:** Read the file **line-by-line** using file streaming (`readline` in Node.js).
- **Advantage:** Efficient memory usage since only one line is processed at a time.
- **Final Choice:** This method was chosen due to its **scalability and efficiency**.

### 3. **Indexing and Binary Search (Preprocessing Required)**
- **Approach:** Build an index mapping dates to file positions, allowing direct access to specific log sections.
- **Issue:** Indexing a 1TB file is complex and requires additional storage.
- **Conclusion:** Suitable for frequent queries but **not ideal for single-run execution**.

---
## Final Solution Summary
We selected the **line-by-line processing method** because:
- It efficiently handles **large files (1TB)** without high memory usage.
- It requires **no preprocessing** and works on **raw logs directly**.
- It is **scalable** and can process logs for any date dynamically.

---
## Steps to Run
### **Node.js Implementation**
#### **Prerequisites:**
- Install **Node.js** (if not already installed)
- Ensure the log file is available on the system

#### **Execution Steps:**
1. Clone or download the script:
   ```sh
   git clone <repository-link>
   cd <repository-folder>
   ```
2. Run the script with the log file path and date:
   ```sh
   node extract_logs.js /path/to/logfile.txt YYYY-MM-DD
   ```
3. The extracted logs will be saved in:
   ```
   output/output_YYYY-MM-DD.txt
   ```

---
This approach ensures **fast, memory-efficient log retrieval** for large-scale log files while being easy to execute.

