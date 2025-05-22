**Data processing architectures** ช่วยแก้ปัญหาธุรกิจและสกัดข้อมูลเชิงลึกจากข้อมูลที่มีแบบ real-time.

---
# Lambda Architecture

**Lambda architecture** แบ่งการประมวลผลแบบ stream กับ batch ออกจากกัน ทำให้ scalable และ fault-tolerant แต่ซับซ้อนในการ setup และ maintain (มี processing logic ซ้ำ ๆ กัน)

![[Lambda-Architecture.png]]

| Pros                           | Cons                 |
| ------------------------------ | -------------------- |
| Robustness and Fault Tolerance | Complexity           |
| Accuracy + Low Latency         | Data Consistency     |
| Historical + Real-Time Data    | Latency              |
| Scalable and Flexible          | Operational Overhead |

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
| Usecases                     | - real-time analytics<br>- multiple batch processing tasks<br>- data lakes | - continuous data pipelines<br>- real-time data processing<br>- IoT systems |
