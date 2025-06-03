**Data processing architectures** ช่วยแก้ปัญหาธุรกิจและสกัดข้อมูลเชิงลึกจากข้อมูลที่มีแบบ real-time.

---
# Lambda Architecture

**Lambda architecture** แบ่งการประมวลผลแบบ stream กับ batch ออกจากกัน ทำให้ scalable และ fault-tolerant แต่ซับซ้อนในการ setup และ maintain (มี processing logic ซ้ำ ๆ กัน)

![[Lambda-Architecture.png]]

### Pros
1. Robustness and Fault Tolerance: Batch layer can re-compute results from raw data to handle code bugs or corrupted results.
2. Accuracy + Low Latency: Batch layer ensures accurate, complete results; speed layer handles low-latency, real-time needs.
3. Historical + Real-Time Data: Supports combining long-term historical analytics with up-to-the-second insights.
4. Scalable and Flexible: Leverages scalable technologies like Hadoop (batch) and Storm or Spark Streaming (speed).
### Cons
1. Complexity: Maintains two separate codebases and processing pipelines for batch and stream—high development and maintenance overhead.
2. Data Consistency: Merging outputs from batch and speed layers can be tricky and error-prone.
3. Latency: Batch layer can be slow, delaying the availability of full data correctness.
4. Operational Overhead: More components to manage (e.g., Hadoop, Kafka, Storm), increasing DevOps complexity.

---
# Kappa Architecture

**Kappa architecture** ลดความซับซ้อนของ pipeline ลงโดยมอง data ทุกอย่างเป็น stream ทำให้ยืดหยุ่นในการสร้างและ maintain แต่ต้องมีประสบการณ์ด้าน stream processing กับ distributed systems


![[Kappa-Architecure.png]]

| Pros                   | Cons                         |
| ---------------------- | ---------------------------- |
| Simplicity             | **Reprocessing Complexity**: |
| Real-Time Focused      | Limited Use Cases            |
| Unified Architecture   | Accuracy Trade-offs          |
| Lower Operational Cost | Tooling Limitations          |

---
# Summary

| Feature                      | Lambda Architecture                                                        | Kappa Architecture                                                          |
| ---------------------------- | -------------------------------------------------------------------------- | --------------------------------------------------------------------------- |
| Design Complexity            | High                                                                       | Low                                                                         |
| Real-time Processing         | Yes (via speed layer)                                                      | Yes                                                                         |
| Batch Processing             | Yes (via batch layer)                                                      | No                                                                          |
| Fault Tolerance              | Strong (via recomputation)                                                 | Depends on stream system                                                    |
| Code Maintenance             | Two code paths                                                             | Single code path                                                            |
| Operational Overhead         | High                                                                       | Lower                                                                       |
| Reprocessing Historical Data | Easy (re-run batch jobs)                                                   | Possible via log replay                                                     |
| Use-cases                    | - real-time analytics<br>- multiple batch processing tasks<br>- data lakes | - continuous data pipelines<br>- real-time data processing<br>- IoT systems |

