# Discussion.md

## Solutions Considered
### 1. **Loading Entire File into Memory**
- **Approach:** Read the entire log file into memory and use string operations to filter logs.
### 2. **Line-by-Line Processing using Streams**
- **Approach:** Read the file **line-by-line** using file streaming (`readline` in Node.js).
- **Advantage:** Efficient memory usage since only one line is processed at a time.
- **Final Choice:** This method was chosen due to its **scalability and efficiency**.

### 3. **Indexing and Binary Search (Preprocessing Required)**
- **Approach:** Build an index mapping dates to file positions, allowing direct access to specific log sections.
- **Conclusion:** Suitable for frequent queries **.
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

1. Run the script with the name of your file, log file path and date:
   ```sh
   node solution.js /pathofyourlogfile YYYY-MM-DD
   ```
2. The extracted logs will be saved in:
   ```
   output/output_YYYY-MM-DD.txt
   ```
   ![image](https://github.com/user-attachments/assets/3c7f3fe9-c297-44ca-aaff-1398f2ba5c7b)


