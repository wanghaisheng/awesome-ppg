### Guidelines for Building a PPG Dataset


Creating a high-quality PPG (Photoplethysmogram) dataset requires careful attention to data acquisition settings, sensor configuration, and comprehensive documentation. Below are detailed guidelines to ensure that your dataset is useful for further research, especially in signal processing and algorithm development.

---

### 1. **Use PPG Sensors that Record Raw or Slightly Filtered Signals**
   - **Why:** Raw PPG signals contain the most information, enabling more flexibility in processing and algorithm design. Slight filtering (e.g., bandpass filters) may be acceptable if it doesn’t distort critical signal features.
   - **Recommendation:** Ensure that your sensor can capture the full range of the PPG signal (i.e., from DC to the highest frequencies of interest). Avoid excessive filtering or fusion of signals during acquisition, as it may limit the potential for later analysis and algorithmic development.

---

### 2. **Record Synchronized Reference Signals (e.g., ECG, RSP)**
   - **Why:** Synchronizing additional physiological signals (such as ECG for heart rate or RSP for respiration) helps contextualize the PPG data and enhances the robustness of algorithmic models.
   - **Recommendation:** Always attempt to capture at least one reference signal (e.g., ECG) to align with the PPG data. This will improve the reliability of signal interpretation, especially when studying cardiovascular or respiratory correlations.

---

### 3. **Maximize Sampling Rate Within Practical Limits**
   - **Why:** The sampling rate determines the resolution of the captured signal. Higher sampling rates provide more detailed data, especially for capturing rapid physiological changes.
   - **Recommendation:** Choose the highest sampling rate that balances data quality with the limitations of your hardware, power consumption, and memory. Ideally, the rate should be at least 100 Hz, but higher rates (e.g., 250 Hz or 500 Hz) are often preferred for capturing fine details of the PPG waveform.

---

### 4. **Save Unfused Raw Data from All Measurement Channels, Including Ambient Light Intensity (if Available)**
   - **Why:** Unfused, raw data offers maximum flexibility for future research. Saving additional sensor readings, such as ambient light intensity, can be useful for post-processing or correcting for noise.
   - **Recommendation:** Record all raw sensor data without fusion, including PPG signals from multiple channels (e.g., red, green, and infrared LEDs), ECG, RSP, and environmental factors like ambient light. This allows for more comprehensive analysis later.

---

### 5. **Enable Timestamp Recording for Each Sample**
   - **Why:** Timestamps are critical for aligning data across multiple sensors and ensuring temporal accuracy. This is especially important when synchronizing PPG with other signals (e.g., ECG or motion data).
   - **Recommendation:** Ensure that each sample from every sensor is timestamped with a precise clock reference. This enables accurate temporal synchronization and can facilitate later analyses, such as event detection or multi-modal signal fusion.

---

### 6. **Provide Detailed Technical Information About the Sensing Device and Configuration**
   - **Why:** Understanding the technical setup is essential for interpreting the data correctly, particularly for replicating experiments or adapting methods to different hardware setups.
   - **Recommendation:** Document all relevant technical specifications, including:
     - **Sensor components:** Names and details of LEDs (e.g., light wavelength, drive current) and photodetectors (e.g., peak sensitivity).
     - **Sampling details:** Sampling rate, number of channels, and the applied sampling scheme (e.g., continuous, event-triggered).
     - **Device setup:** Include information about the model, firmware, and software configurations used.
   - This information helps others assess the quality and comparability of your data and is essential for reproducibility.

---

### 7. **Describe the Sensor Setup, Attachment, and Measurement Location**
   - **Why:** The sensor’s location on the body affects the quality of the PPG signal due to variations in blood flow, movement artifacts, and skin characteristics. Clear documentation of sensor placement is necessary for evaluating the dataset’s relevance to specific use cases.
   - **Recommendation:** 
     - Provide precise descriptions of sensor placement. For example, if the sensor is worn on the wrist, specify whether it is on the volar (palm) side or dorsal (back) side.
     - Include whether the sensor is fixed to the skin or worn on top of clothing (e.g., wristband, clip-on).
     - If applicable, specify any motion or environmental constraints during the measurement (e.g., physical activity, lighting conditions).

---

### 8. **Provide Detailed Documentation of Research Domain and Questions**
   - **Why:** Clear documentation of the research context helps users of the dataset understand its relevance and potential applications. This can assist in determining whether your dataset is compatible with other datasets or research projects.
   - **Recommendation:** Include a brief description of the research goals, the physiological phenomena you are investigating, and the specific hypotheses or questions your dataset aims to address. This will guide future researchers in utilizing your dataset effectively, especially for signal processing or machine learning tasks.

---

### 9. **Prioritize Unprocessed, Raw Data for Signal Processing and Algorithm Development**
   - **Why:** Unprocessed, raw measurements provide maximum flexibility for future research, especially in signal processing and the development of algorithms for wearable PPG sensing.
   - **Recommendation:** Avoid any unnecessary preprocessing or data fusion during acquisition. This preserves the integrity of the original signal and allows for a variety of processing techniques to be applied later. Raw data allows others to apply their own filtering, noise reduction, and feature extraction methods.

---

### Balancing Trade-offs: Memory and Power Consumption
- **Considerations:** High-quality data acquisition (high sampling rates, multiple sensor channels, and long sample durations) will consume significant amounts of memory and power. For long-term monitoring or large datasets, it may be necessary to balance these factors.
   - **Recommendation:** For extended monitoring, use a more efficient sampling scheme, such as event-triggered sampling or reducing the sampling rate during periods of inactivity. Carefully monitor energy usage and memory storage, and consider compressing or downsampling data where appropriate.

---

By following these guidelines, you can ensure that your PPG dataset is robust, flexible, and suitable for a wide range of research applications, from signal processing to machine learning and wearable health monitoring.




### Guidelines for Building a PPG Dataset (with Detailed Metrics)

To ensure the creation of a comprehensive and high-quality PPG dataset, detailed technical specifications and metrics are essential for reproducibility, analysis, and future research. Below are the enhanced guidelines with specific metrics for each component.

---

### 1. **Use PPG Sensors that Record Raw or Slightly Filtered Signals**
   - **Why:** Raw PPG signals preserve the inherent characteristics of the data, offering maximum flexibility for later analysis.
   - **Metrics:**
     - **Sampling Rate:** Preferably at least **100 Hz**, but ideally **250 Hz - 500 Hz** or higher for fine-grained analysis.
     - **Signal Integrity:** Ensure that the raw signal is unaltered by excessive low-pass or high-pass filtering during acquisition.
     - **Signal-to-Noise Ratio (SNR):** Aim for a minimum **SNR > 40 dB** to ensure clean signal acquisition. Higher SNR values (e.g., **50 dB** or more) are preferable for high-quality data.
     - **Dynamic Range:** The sensor should capture a **wide dynamic range**, typically between **0.5 to 2 V** to account for small variations in light absorption.

---

### 2. **Record Synchronized Reference Signals (e.g., ECG, RSP)**
   - **Why:** Synchronized reference signals like ECG and respiration (RSP) are vital for interpreting the PPG signal in context.
   - **Metrics:**
     - **Synchronization Accuracy:** Ensure that timestamps are synchronized with an accuracy of **±1 ms** for all sensors.
     - **Signal Alignment:** Use **cross-correlation** to measure temporal alignment between PPG and reference signals (ideal cross-correlation peaks should be above **0.9**).
     - **Sampling Rate:** The reference signals (e.g., ECG) should be sampled at **500 Hz - 1000 Hz** to capture sufficient detail.
     - **ECG Signal Quality:** For ECG, target **R-R interval accuracy** to within **±2 ms** compared to manual annotation.

---

### 3. **Maximize Sampling Rate Within Practical Limits**
   - **Why:** The sampling rate directly impacts data resolution. Higher rates capture finer temporal details but increase memory and power usage.
   - **Metrics:**
     - **Sampling Rate:** 
       - For **standard applications**, **100 Hz - 250 Hz** is often sufficient.
       - For **high-resolution studies** (e.g., arrhythmia detection), target **500 Hz - 1000 Hz**.
     - **Power Consumption:** The sampling rate should be balanced with **battery life**. For wearable devices, consider **power consumption < 50 mW** per sensor at higher sampling rates.
     - **Data Throughput:** Ensure the device can handle the throughput (e.g., for **500 Hz** sampling on a 3-channel PPG device, expect **1.5 KB/s** per second).

---

### 4. **Save Unfused Raw Data from All Measurement Channels, Including Ambient Light Intensity**
   - **Why:** Unfused data allows for maximum flexibility in post-processing and mitigates loss of important features during sensor fusion.
   - **Metrics:**
     - **Measurement Channels:** Record from at least **3 channels**: typically **red, green, and infrared** wavelengths.
     - **Ambient Light Measurement:** If available, record **ambient light intensity** in **lux** (ideal range: **0 - 100,000 lux** for natural daylight environments).
     - **Signal Resolution:** Ensure each channel's data is recorded with **12-bit or 16-bit resolution** for adequate precision.
     - **Data Storage:** Unfused data results in larger datasets; aim for a **data compression rate** of **≤ 2x** (where applicable) to minimize storage needs without losing significant quality.

---

### 5. **Enable Timestamp Recording for Each Sample**
   - **Why:** Timestamps ensure that data from multiple sensors (e.g., PPG and ECG) can be accurately synchronized for meaningful analysis.
   - **Metrics:**
     - **Timestamp Accuracy:** Timestamps should be accurate to within **±1 ms** across all measurement channels.
     - **Timestamp Resolution:** Use at least **1 ms** resolution for timestamps to ensure fine-grained synchronization.
     - **Global Clock Synchronization:** For multi-sensor setups, ensure that all sensors share a **common clock** with drift of **< 1 ms/hour** to maintain long-term alignment.

---

### 6. **Provide Detailed Technical Information About the Sensing Device and Configuration**
   - **Why:** Detailed technical documentation is essential for understanding the sensor's capabilities, limitations, and how the data was collected.
   - **Metrics:**
     - **Sensor Specifications:** 
       - **LED Wavelengths:** For example, **red LED** at **660 nm**, **infrared LED** at **850 nm**.
       - **Photodetector Sensitivity:** The photodetector’s peak sensitivity should typically be **> 0.6 A/W** in the relevant wavelength range.
     - **Sampling Scheme:** Specify if sampling is **continuous**, **event-triggered**, or **adaptive**.
     - **LED Drive Current:** The current for each LED should be specified (e.g., **20 mA** for typical wearables).
     - **Device Firmware Version:** Include the **firmware version** or **model number** to help researchers replicate the setup.

---

### 7. **Describe the Sensor Setup, Attachment, and Measurement Location**
   - **Why:** Detailed descriptions of sensor setup and placement allow for reproducibility and the ability to assess data relevance based on sensor location.
   - **Metrics:**
     - **Location Accuracy:** Define the sensor location to within **1 cm**. For example, on the wrist: specify **volar** or **dorsal** sides.
     - **Sensor Attachment Method:** Indicate if the sensor is attached using a **wristband**, **adhesive**, or **clip**, and specify the **pressure** applied (e.g., **< 2 N**).
     - **Environmental Context:** Document environmental factors such as **ambient temperature** (**20°C - 25°C**), **humidity levels** (ideally **40% - 60%**), and **motion artifacts** (e.g., stationary vs. walking).

---

### 8. **Provide Detailed Documentation of Research Domain and Questions**
   - **Why:** Clear context helps others understand the purpose of the dataset, assess its relevance, and utilize it effectively for their own research.
   - **Metrics:**
     - **Research Domain:** Describe the **objective** of the study (e.g., heart rate variability, motion artifact reduction) and the **intended use** of the dataset (e.g., training machine learning algorithms, signal processing validation).
     - **Sample Size and Diversity:** Specify the **number of participants** (e.g., **n = 30**). Include details on demographic diversity such as **age range**, **gender distribution**, and **health status**.
     - **Sampling Conditions:** Note any special conditions during data collection, such as **resting** vs. **exercise** states, **sleep** vs. **wakefulness**, or **postural changes**.

---

### 9. **Prioritize Unprocessed, Raw Data for Signal Processing and Algorithm Development**
   - **Why:** Raw data preserves the original signal characteristics, allowing maximum flexibility for signal processing and algorithmic experimentation.
   - **Metrics:**
     - **Raw Data Preservation:** Ensure that all raw data (e.g., from **PPG**, **ECG**, and **ambient light sensors**) is saved without any fusion or heavy preprocessing.
     - **Feature Extraction Flexibility:** Leave out feature extraction or signal conditioning unless necessary for baseline comparisons. This allows for testing a wide range of filtering and feature-extraction techniques (e.g., **wavelet transform**, **Fourier analysis**).
     - **Data Format:** Save the raw data in **standard formats** like **CSV**, **HDF5**, or **MATLAB** to allow easy access and compatibility with common processing libraries.

---

### Balancing Trade-offs: Memory and Power Consumption
   - **Considerations:** High-quality data acquisition can result in larger datasets and higher power consumption, so it's essential to manage these trade-offs.
   - **Metrics:**
     - **Data Storage Efficiency:** Plan for **2-5 MB per minute** of data at moderate sampling rates (e.g., **250 Hz** with **3 channels**).
     - **Battery Life:** For wearable devices, ensure that battery life is **> 6 hours** at higher sampling rates. Use energy-efficient sampling schemes when longer monitoring is needed (e.g., **sample only when motion is detected**).
     - **Data Compression:** If needed, compress data in real-time with a **compression ratio** of **2x - 5x**, ensuring minimal loss of signal quality.

---

By adhering to these detailed guidelines and metrics, you will ensure that your PPG dataset is high-quality, flexible, and suitable for a wide range of applications in signal processing, machine learning, and wearable health monitoring.



### 构建PPG数据集的指南（附详细指标）

为了确保创建一个高质量且全面的PPG（光电容积脉搏波）数据集，详细的技术规格和指标对于重现性、分析以及后续研究至关重要。以下是每个组件的详细指南，包含具体的技术指标。

---

### 1. **使用记录原始或略微滤波信号的PPG传感器**
   - **原因：** 原始PPG信号保留了信号的固有特性，为后续分析提供最大的灵活性。
   - **指标：**
     - **采样率：** 最好至少为 **100 Hz**，但理想情况下为 **250 Hz - 500 Hz** 或更高，以便捕捉更细微的波形特征。
     - **信号完整性：** 确保原始信号在采集过程中没有被过度低通或高通滤波。
     - **信噪比（SNR）：** 目标信噪比至少为 **40 dB**，最好能达到 **50 dB** 或更高，以保证信号的清晰度。
     - **动态范围：** 传感器应具有 **0.5 到 2 V** 的动态范围，以适应血液吸光度的微小变化。

---

### 2. **记录同步参考信号（例如ECG、RSP）**
   - **原因：** 同步的参考信号（如ECG和呼吸信号RSP）对于理解和解释PPG信号至关重要。
   - **指标：**
     - **同步精度：** 确保所有传感器的时间戳同步误差小于 **±1 ms**。
     - **信号对齐：** 使用 **互相关** 方法验证PPG与参考信号的对齐情况，理想的互相关峰值应高于 **0.9**。
     - **采样率：** 参考信号（如ECG）应采样于 **500 Hz - 1000 Hz**，以捕捉足够的细节。
     - **ECG信号质量：** 对于ECG，RR间期的误差应控制在 **±2 ms** 以内，以便与手动标注数据对比。

---

### 3. **在实际限制内最大化采样率**
   - **原因：** 采样率直接影响数据的分辨率。较高的采样率能够捕捉更细致的生理变化，但会增加内存和电池消耗。
   - **指标：**
     - **采样率：** 
       - 对于 **标准应用**，通常 **100 Hz - 250 Hz** 足够。
       - 对于 **高分辨率研究**（例如心律失常检测），目标采样率为 **500 Hz - 1000 Hz**。
     - **功耗：** 采样率应与 **电池续航** 平衡。对于可穿戴设备，功耗应低于 **50 mW**。
     - **数据吞吐量：** 如果使用 **500 Hz** 采样频率，3通道PPG设备每秒钟的吞吐量大约为 **1.5 KB**。

---

### 4. **保存所有测量通道的未融合原始数据，包括环境光强度（如有）**
   - **原因：** 未融合的原始数据为后续处理提供最大灵活性，避免因信号融合而丢失重要信息。
   - **指标：**
     - **测量通道：** 至少记录 **3个通道**，通常包括 **红色、绿色和红外光** 波长。
     - **环境光强度：** 如传感器支持，记录 **环境光强度**（单位：lux），理想范围为 **0 - 100,000 lux**（自然光环境）。
     - **信号分辨率：** 确保每个通道的数据采集分辨率为 **12位** 或 **16位**。
     - **数据存储：** 未融合数据会生成较大的数据集，可以考虑使用 **≤ 2倍** 的数据压缩比（如有）来减少存储需求，但不丢失重要数据质量。

---

### 5. **为每个样本启用时间戳记录**
   - **原因：** 时间戳保证了多个传感器（例如PPG与ECG）之间的数据能够精确对齐，确保时序的准确性。
   - **指标：**
     - **时间戳精度：** 确保所有测量通道的时间戳误差小于 **±1 ms**。
     - **时间戳分辨率：** 至少使用 **1 ms** 的时间戳分辨率，以保证精确的时序同步。
     - **全局时钟同步：** 对于多传感器系统，确保所有传感器共享一个 **公用时钟**，其漂移应小于 **1 ms/小时**。

---

### 6. **提供传感器设备和配置的详细技术信息**
   - **原因：** 详细的技术文档对于理解传感器的能力、限制以及数据采集方式至关重要，便于后续的重现实验或调整设置。
   - **指标：**
     - **传感器规格：** 
       - **LED波长：** 例如，**红光LED**（660 nm），**红外LED**（850 nm）。
       - **光电探测器灵敏度：** 目标探测器的峰值灵敏度应大于 **0.6 A/W**，适应所用波长。
     - **采样方案：** 说明使用的是 **连续采样**、**事件触发采样**，还是 **自适应采样**。
     - **LED驱动电流：** 每个LED的电流应在**20 mA** 左右，适合大多数可穿戴设备。
     - **设备固件版本：** 包括 **固件版本号** 或 **设备型号**，以帮助其他研究者重现设置。

---

### 7. **描述传感器设置、附件和测量位置**
   - **原因：** 传感器的放置位置会影响PPG信号的质量，明确的设置描述有助于评估数据的适用性和可重现性。
   - **指标：**
     - **位置精度：** 将传感器的位置描述精确到 **1 cm**，例如，腕部传感器应标明是 **掌侧** 还是 **背侧**。
     - **传感器附件方式：** 说明传感器的固定方式（例如，**腕带**、**粘贴** 或 **夹式**），并注明施加的 **压力**（例如，**< 2 N**）。
     - **环境因素：** 记录环境因素，如 **环境温度**（理想范围：**20°C - 25°C**）、**湿度**（理想范围：**40% - 60%**）以及 **运动伪影**（例如，静态 vs 步态）。

---

### 8. **提供研究领域和问题的详细文档**
   - **原因：** 清晰的研究背景文档帮助其他研究者理解数据的用途，评估数据的相关性并有效利用数据。
   - **指标：**
     - **研究领域：** 描述研究的 **目标**（例如，心率变异性、运动伪影去除）和数据集的 **预期用途**（例如，训练机器学习算法、验证信号处理方法）。
     - **样本大小与多样性：** 说明参与者的 **数量**（例如，**n = 30**）及其 **人口学特征**（如年龄范围、性别比例、健康状态等）。
     - **采样条件：** 说明采集过程中是否有 **特殊条件**，如 **静息** vs **运动**、**睡眠** vs **清醒** 或 **体位变化**。

---

### 9. **优先保存未经处理的原始数据，以便后续信号处理和算法开发**
   - **原因：** 原始数据保留了信号的所有信息，提供了最大灵活性，便于后续的信号处理和算法开发。
   - **指标：**
     - **原始数据保存：** 确保所有原始数据（例如 **PPG**、**ECG** 和 **环境光传感器** 的数据）没有被融合或过度预处理。
     - **特征提取灵活性：** 在数据收集时尽量避免特征提取或信号调理，除非是必要的基准对比。这样其他研究人员可以使用多种 **滤波方法**、**特征提取技术**（例如 **小波变换**、**傅里叶变换**）进行分析。
     - **数据格式：** 保存原始数据时使用 **标准格式**（如 **CSV**、**
    

"[The Quest for Raw Signals: A Quality Review of Publicly Available Photoplethysmography Datasets](https://ubicomp.eti.uni-siegen.de/home/datasets/data20/index.html.en)", <a href="https://ubicomp.eti.uni-siegen.de/home/team/fwolling.html.en" target="_blank">Florian Wolling</a> and <a href="https://ubicomp.eti.uni-siegen.de/home/team/kristof.html.en" target="_blank">Kristof Van Laerhoven</a>. In *DATA'20: Proceedings of the 3rd Workshop on Data Acquisition To Analysis, DATA 2020, Virtual Event, Japan, November 2020*, ACM, 2020. <a href="https://doi.org/10.1145/3419016.3431485" target="_blank">https://doi.org/10.1145/3419016.3431485</a>
