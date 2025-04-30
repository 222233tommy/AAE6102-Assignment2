# Project name

    This is a repository for AAE6102 assignment 2 (Satellite Navigation). 

    Author: Baoshan Song.

    NetID: 23093571R


# Task 1

    Model: ChatGPT 4o
    Prompt: If you are an expert in GNSS navigation. Compare the pros and cons of the following GNSS techniques for smartphone navigation:Differential GNSS (DGNSS), Real-Time Kinematic (RTK), Precise Point Positioning (PPP), PPP-RTK.

    Comment: 
    (1) Correctness: most of the review from ChatGPT is constructive, but some of it may be wrong, e.g. ChatGPT considers dual-frequency is necessary for RTK in smartphones.
    (2) Exactness: the keyword smartphone is not mentioned all over the analysis and the methods designed for smartphones are not the latest.

    Chatroom Link (if any): https://chatgpt.com/share/680efc0d-008c-8000-bc38-d1e5433d681f

Summary: Pros and Cons of DGNSS, RTK, PPP, and PPP-RTK for Smartphone Navigation

As GNSS technology evolves, multiple techniques have been developed to improve positioning accuracy beyond the basic 10–30 meters achievable with standalone GNSS. Among these, Differential GNSS (DGNSS), Real-Time Kinematic (RTK), Precise Point Positioning (PPP), and PPP-RTK are the most influential methods. Each method follows a logical progression toward reducing errors while balancing infrastructure requirements, accuracy, convergence speed, and practicality — especially important for smartphones. Below, we summarize the major advantages and limitations of each.

***

### Differential GNSS (DGNSS)

**Pros:**

*   **Simplicity and robustness**: DGNSS is easy to implement. It only requires correction signals from a nearby reference station. Many existing services (like WAAS, EGNOS, and MSAS) broadcast these corrections freely.
*   **Moderate improvement**: It significantly reduces ionospheric delay, satellite clock errors, and other biases, improving raw smartphone GNSS from tens of meters to around 1–3 meters in open areas.
*   **Low bandwidth needs**: DGNSS corrections are small and slow, so even basic mobile networks can handle the data easily.
*   **Wide coverage**: Public augmentation systems cover entire continents, ensuring most users can access at least some corrections without special subscriptions.

**Cons:**

*   **Limited accuracy**: While much better than uncorrected GNSS, DGNSS cannot reach sub-meter or centimeter precision. For applications like autonomous driving or surveying, it's insufficient.
*   **Regional dependence**: DGNSS performance depends on how close the user is to a correction station. Errors increase with distance from the station.
*   **Not resilient to urban environments**: In dense cities where multipath effects dominate, DGNSS improvements are limited.

***

### Real-Time Kinematic (RTK)

**Pros:**

*   **Centimeter-level precision**: RTK offers outstanding accuracy, typically 1–5 centimeters under good conditions. It is achieved by resolving carrier phase ambiguities with a nearby base station.
*   **Fast convergence**: With strong signal conditions and a close base station, RTK can provide high-accuracy positions within seconds to a few minutes.
*   **Expanding infrastructure**: Continuous Operating Reference Stations (CORS) networks are expanding worldwide, making RTK access more feasible.

**Cons:**

*   **Demanding hardware requirements**: Smartphones must support raw GNSS measurements reception and maintain low-noise carrier phase measurements — capabilities that are only present in a few high-end models.
*   **Sensitivity to environment**: RTK performs poorly under trees, indoors, or near tall buildings because it depends heavily on strong and clean GNSS signals.
*   **Short base station range**: Accuracy drops quickly if the user moves more than 10–20 kilometers away from the reference station.
*   **Constant high-bandwidth connection**: Correction data must be streamed continuously, which can drain smartphone batteries and require stable mobile internet connections.

***

## Precise Point Positioning (PPP)

**Pros:**

*   **No local infrastructure needed**: Unlike RTK and DGNSS, PPP relies only on precise satellite orbit and clock products. Users can achieve better positioning accuracy globally, even in remote areas.
*   **Single-receiver operation**: No need for nearby base stations, making PPP ideal for maritime, aviation, and remote-field applications.
*   **Decent accuracy**: PPP can achieve accuracies around 30 centimeters to 1 meter, depending on satellite corrections and user hardware.
*   **Improving accessibility**: More commercial PPP services and fast convergence techniques are becoming available.

**Cons:**

*   **Slow convergence**: Traditional PPP can take 10–30 minutes to reach its best accuracy, which is impractical for many smartphone navigation applications that expect instant results.
*   **Challenging for smartphones**: Consumer-grade GNSS antennas introduce noise and multipath errors that degrade PPP performance significantly.
*   **Less effective in dynamic conditions**: For moving platforms like cars or pedestrians, constant changes in satellite visibility reset convergence, reducing effectiveness.

***

## PPP-RTK

**Pros:**

*   **Combines strengths of PPP and RTK**: PPP-RTK uses global corrections for satellite orbits and clocks (like PPP) and local corrections for atmospheric delays and biases (like RTK), achieving fast, precise positioning.
*   **Fast convergence**: Typical convergence times are within a few seconds to a few minutes, comparable to RTK but with greater flexibility.
*   **High accuracy**: Under good conditions, PPP-RTK can deliver 2–10 centimeter accuracy, making it suitable for high-end applications like lane-level navigation or augmented reality.
*   **Resilience to outages**: PPP-RTK is more robust than pure RTK because it can fall back to PPP corrections if local data is temporarily lost.

**Cons:**

*   **High demands on device capability**: Like RTK, PPP-RTK requires low-noise carrier phase tracking, and strong satellite visibility — challenging for most current smartphones.
*   **Service cost and complexity**: Many PPP-RTK services are subscription-based and require complex backend support for corrections and authentication.
*   **Emerging ecosystem**: While promising, PPP-RTK is still maturing for mass-market smartphones, with standards, availability, and service models not fully stabilized yet.

***

# GNSS Techniques: Characteristics Comparison

| Characteristic                  | DGNSS                                              | RTK                                         | PPP                                                | PPP-RTK                                            |
| ------------------------------- | -------------------------------------------------- | ------------------------------------------- | -------------------------------------------------- | -------------------------------------------------- |
| **Accuracy**                    | 1–3 meters                                         | 1–5 centimeters                             | 30 cm – 1 meter                                    | 2–10 centimeters                                   |
| **Convergence Time**            | Instant (seconds)                                  | Seconds to a few minutes                    | 10–30 minutes                                      | Seconds to a few minutes                           |
| **Infrastructure Required**     | Ground-based reference station (single or network) | Local base station (within \~20 km)         | None (global corrections)                          | Global corrections + local atmospheric corrections |
| **Dependency on Distance**      | High (degrades with distance)                      | Very high (short baseline needed)           | Low (no baseline needed)                           | Moderate (short-to-medium distance corrections)    |
| **Coverage**                    | Regional                                           | Local (10–20 km around base)                | Global                                             | Global + Local enhancements                        |
| **Sensitivity to Environment**  | Medium (somewhat affected by urban canyon, trees)  | High (needs open sky view)                  | Medium (multipath and blockage affect convergence) | High (needs good signal quality)                   |
| **Measurement Requirements**    | pseudu-range                                       | pseudo-range and carrier-phase              | pseudo-range and carrier-phase                     | pseudo-range and carrier-phase                     |
| **Data Link Requirement**       | Low bandwidth                                      | Continuous, low-latency link                | Occasional updates needed                          | Continuous, low-latency link                       |
| **Cost**                        | Low (often free services)                          | Medium to High (base station, network fees) | Medium (commercial services)                       | High (subscription services)                       |
| **Suitability for Smartphones** | High (widely supported)                            | Low to Medium (only high-end phones)        | Medium (somewhat possible)                         | Low to Medium (future potential)                   |

## Final Reflection

In the smartphone context, **DGNSS** remains the most widely usable today due to its simplicity and minimal infrastructure needs, albeit with limited accuracy. **RTK** offers outstanding precision but struggles with the hardware and connectivity demands of smartphones. **PPP** provides global coverage but suffers from slow convergence, making it less attractive for dynamic applications. **PPP-RTK** represents the future of high-precision GNSS navigation, combining accuracy and speed, but it is currently suitable only for specialized applications on premium devices.

As smartphone hardware improves, particularly with wider adoption of dual-frequency GNSS chips and better antennas, the practical use of PPP-RTK could expand dramatically, enabling centimeter-level positioning for everyday navigation, smart mobility, and augmented reality.

# Task 2: GNSS in Urban area



Urban areas present significant challenges to GNSS positioning due to signal blockage, multipath effects, and poor satellite visibility. In this task, a **skymask** file is provided, which indicates the elevation angle representing potential satellite visibility blockage for each corresponding azimuth angle. With this file, NLOS detection is employed to adjust the weighting of pseudo-range outliers. We check the visibility by using the mask and the process is shown as below.



In the open-sky experiment, the positioning performance is shown as below.

&#x20;



# Task 3: GPS RAIM

RAIM is a critical technique for detecting and excluding faulty GPS measurements. In this task, the key insight and open-sky experimental results shown be shown in a Stanford chart.

Basically, the weighted least squares (WLS) can be formulate as

```math
X=(H^TWH)^{-1}H^TWZ
```

Then, the WSSE can be written as

```math
WSSE=\sqrt{Z^TW(I-P)Z}
```

where P is the weighted projection function

```math
P=H(H^TWH)^{-1}H^TW
```

To detect outlier, the threshold T is given as:

```math
T(N,P_{FA})=\sqrt{Q_{\chi^2,N-4 }(1-P_{FA})}

```

where Q is the quantile function of Chi-square distribution with degree of freedom of N-4. Then the protection level can be calculated by:

```math
PL=max[P_{slope}]T(N,P_{FA})+k(P_{MD})\sigma
```

where P\_slope is the residual slope related to the outlier:

```math
P_{slope} =\frac{\sqrt{K^2_{1,i}+K^2_{2,i}+K^2_{3,i}}}{\sqrt{W_{ii}(1-P_{ii})}}
```

In this task, the mentioned classic weighted RAIM algorithm is applied to the open-sky dataset with the parameters: 1). 10^-2^ of probability of false alarm (P-fa), and 2) 10^-7^ of probability of missed detection (P\_md). The GPS pseudo-range measurement sigma (σ) is 3m. (Bonus) Evaluate the GNSS integrity monitoring performance using a Stanford Chart analysis, given that the 3D alarm limit (AL) is 50 meters. Hint 1: Calculate the only solution so that the minimum degree of freedom is 4 (meaning you can use the same equations given in the lecture notes). In the other words, a threshold set at 5.33 σ, the probability that random Gaussian noise causes a value to exceed that threshold is only 1 in 10 million (10^-7)

The result is illustrated in a Stanford chart. According to the result, all the PL is within AL, but the PE of some results is larger than PL. The possible reason is that we have not detected the outliers by Chi-Square test, which belongs to missed detection.&#x20;


![stanford](https://github.com/user-attachments/assets/6a259411-96ef-43f9-89ec-044e130aed9f)


# Task 4 LEO satellites

    Model: ChatGPT 4o
    Prompt: You are an expert in GNSS and LEO navigation. Write the pros and challenges in LEO satellites in 500-1000 words: e.g. pros: rapid geometric change, high signal power, free SOP, mega-constellation; challenges: complex signal structure, lack high precision ephemerides, receiver clock synchronization.

    Comment: 
    (1) Correctness: most of the review from ChatGPT is constructive, 
    (2) Exactness: the keyword smartphone is not mentioned all over the analysis and the methods designed for smartphones are not the latest.

    Chatroom Link (if any): https://chatgpt.com/share/680efc0d-008c-8000-bc38-d1e5433d681f

## Opportunities and Challenges of Using LEO Communication Satellites for GNSS Navigation

Low Earth Orbit (LEO) satellites, originally designed for communication, Earth observation, and remote sensing, are increasingly being explored for their potential to support or enhance Global Navigation Satellite Systems (GNSS). With the rise of mega-constellations such as Starlink, OneWeb, and Kuiper, thousands of LEO satellites are being deployed, offering unprecedented global coverage and signal availability. While this presents exciting opportunities for Positioning, Navigation, and Timing (PNT) services, it also introduces a host of technical challenges that must be addressed for reliable and accurate navigation performance.

## Advantages of LEO Satellites for Navigation

### 1. Rapid Geometric Change

One of the most significant advantages of LEO satellites is their rapid orbital motion. Traveling at approximately 7.5 km/s, LEO satellites complete an orbit around the Earth in roughly 90 to 120 minutes. This results in rapid geometric change relative to the user, which in turn improves the **positioning geometry**. The fast-changing satellite-receiver angles reduce **Dilution of Precision (DOP)**, particularly **vertical DOP**, allowing for more accurate position estimates over short time intervals.

### 2. High Signal Power

Due to their low orbital altitude (typically 300–1,200 km), LEO satellites are much closer to Earth than traditional MEO GNSS satellites, which orbit at approximately 20,200 km. This proximity means that LEO signals experience less path loss and arrive at the user receiver with much **higher signal power**. The stronger signal makes it easier to acquire and track even in harsh environments such as urban canyons, dense foliage, or indoors—scenarios where conventional GNSS signals often fail.

### 3. Free Signals of Opportunity (SOP)

LEO satellites primarily serve communication functions, but their existing downlink signals can be repurposed as **signals of opportunity (SOP)** for navigation. This reuse avoids the need to launch dedicated navigation payloads, reducing cost and enabling rapid deployment. Although these signals are not specifically designed for navigation, they often carry features such as timing markers or identifiable signal structures that can be exploited for pseudorange, Doppler, or carrier-phase measurements.

### 4. Mega-constellations and High Satellite Density

The large number of satellites in LEO mega-constellations ensures **high spatio-temporal availability**. At any given time, tens to hundreds of LEO satellites may be visible from a point on Earth, especially when using a wide beamwidth or all-sky receiver. This dense constellation improves **redundancy**, **robustness to outages**, and **fault detection**, which are critical in safety-of-life or mission-critical applications such as autonomous driving, aviation, or disaster response.

### 5. Low Latency and High Update Rates

LEO satellites offer **low latency** due to shorter signal travel times and **high update rates** due to their fast movement. This is particularly beneficial for time-sensitive applications such as real-time kinematics (RTK), autonomous navigation, or augmented reality, where frequent position updates are required.

## Challenges of LEO Satellites for Navigation

Despite these promising features, using LEO communication satellites for navigation introduces several technical obstacles that differentiate them from traditional GNSS systems.

### 1. Complex Signal Structure

LEO satellites often use **proprietary, encrypted, or non-standard signal modulations** optimized for data throughput, not for navigation. These may include frequency-hopping, beamforming, or time division multiplexing mechanisms that make it difficult for a generic GNSS receiver to decode and track them. Moreover, these signals may not be continuous or omnidirectional, as is the case with GNSS, limiting consistent observability across regions.

### 2. Lack of High-Precision Ephemerides

In GNSS, satellites continuously broadcast their precise orbital parameters (ephemerides) and clock corrections, enabling users to calculate accurate satellite positions in real time. In contrast, LEO communication satellites generally do not carry **high-precision clocks** or provide **real-time broadcast ephemeris** to users. Their positions are typically determined through ground-based tracking and uploaded periodically. This **lack of onboard real-time orbit and clock data** significantly reduces the accuracy of pseudorange-based positioning.

### 3. Receiver Clock Synchronization

Unlike GNSS receivers that rely on the high timing stability of onboard atomic clocks, LEO-based navigation often depends on **external time references**. This creates a synchronization problem: the receiver needs accurate time to estimate position from pseudoranges, but the time itself depends on knowing the position. This coupling can lead to **time-position ambiguity**, especially when using SOPs without any timing guarantees. Solutions such as two-way time transfer or integration with external time sources (e.g., GNSS, NTP, or atomic clocks) may be required, adding to system complexity.

### 4. Short Visibility Duration

Due to their high orbital velocity, a single LEO satellite remains visible to a ground user for only a few minutes. This short **dwell time** leads to **frequent handovers** between satellites, requiring fast signal reacquisition and robust satellite tracking. For continuous navigation, receivers must be able to quickly adapt to a changing set of satellites, increasing both hardware and software complexity.

### 5. Rapid Doppler Shift

The high relative velocity of LEO satellites induces large and fast-varying **Doppler shifts**, often several kHz. While Doppler can be used as a navigation observable, it also requires **high-bandwidth tracking loops**, **fast acquisition algorithms**, and **accurate receiver oscillator calibration** to maintain lock. Conventional GNSS receivers may not be capable of handling such fast-changing Doppler dynamics without redesign.

### 6. Interoperability and Standardization

There is currently no universal standard for using LEO communication signals for navigation. Each constellation may use different frequencies, modulations, and signal structures. This fragmentation hinders the development of **interoperable receivers** and requires **multi-protocol processing capabilities**, which adds cost, power consumption, and design complexity.

## Conclusion

LEO communication satellites hold immense promise for the future of navigation, offering high signal power, dense global coverage, and improved geometric diversity. They have the potential to augment or even replace parts of traditional GNSS in applications requiring low latency and high availability. However, to unlock their full potential, significant challenges must be addressed, including signal standardization, real-time ephemeris availability, clock synchronization, and receiver design.

A hybrid PNT approach—integrating LEO SOPs with GNSS, inertial systems, and terrestrial signals—will likely provide the most robust and accurate navigation solution in the near future. Ultimately, co-designing LEO constellations with navigation functionality in mind will be the key to overcoming current limitations and enabling a new generation of resilient navigation services.



# Task 5

    Model: ChatGPT 4o
    Prompt: You are an expert in GNSS Remote sensing. GNSS is not only used for positioning and navigation but also has significant applications in remote sensing. Write a short essay (500–1000 words) discussing the impact of GNSS in remote sensing. Please select one of the following topics covered in the lecture to discuss:

    GNSS Reflectometry (GNSS-R)
    GNSS Interferometric Reflectometry (GNSS-IR)
    GNSS Radio Occultation (GNSS-RO)
    Ionosphere mapping based GNSS ground station
    GNSS seismology

    Comment: 
    (1) Correctness: most of the review from ChatGPT is constructive, 
    (2) Exactness: the keyword smartphone is not mentioned all over the analysis and the methods designed for smartphones are not the latest.

    Chatroom Link (if any): https://chatgpt.com/share/680efc0d-008c-8000-bc38-d1e5433d681f

# GNSS Reflectometry (GNSS-R): A New Paradigm in Remote Sensing

Global Navigation Satellite Systems (GNSS), such as GPS, Galileo, and BeiDou, are traditionally associated with positioning, navigation, and timing (PNT) services. However, recent advancements have revealed their immense value in the domain of **remote sensing**. One particularly promising application is **GNSS Reflectometry (GNSS-R)**, an innovative technique that leverages GNSS signals reflected from the Earth's surface to extract environmental information. GNSS-R is a passive, bistatic radar system that turns existing GNSS constellations into Earth-observing sensors. It has proven effective for monitoring ocean winds, sea surface heights, soil moisture, snow depth, and even ice coverage.

## Principles of GNSS Reflectometry

GNSS-R relies on the reflection of GNSS signals—originally intended for navigation—off the Earth's surface, which are then captured by specialized receivers. The technique typically employs a **bistatic geometry**: the GNSS satellite acts as a transmitter, and the receiver on a satellite, aircraft, drone, or ground station captures both the **direct signal** and the **reflected signal**.

The key observables in GNSS-R include:

*   **Delay** between the direct and reflected signals, related to surface elevation and roughness.
*   **Signal power** and coherence, which provide insight into surface type and roughness.
*   **Doppler shift**, which can help determine relative motion between the surface and the receiver.
*   **Delay-Doppler Maps (DDMs)**, which are 2D representations of reflected signal characteristics and the core data product in GNSS-R.

Unlike active radar systems, GNSS-R does not require a dedicated transmitter, which makes it **cost-effective**, **power-efficient**, and suitable for **small satellite constellations**.

## Applications of GNSS-R in Remote Sensing

### 1. Ocean Surface Wind and Altimetry

One of the earliest and most mature applications of GNSS-R is in **ocean remote sensing**. The roughness of the ocean surface affects the strength and spread of the reflected GNSS signal. From the shape of the DDM, one can infer the **wind speed and direction** at the sea surface. Additionally, by measuring the signal delay between the direct and reflected paths, **sea surface height** (SSH) can be estimated, providing a low-cost alternative to traditional radar altimeters.

The **CYGNSS (Cyclone Global Navigation Satellite System)** mission by NASA is a pioneering GNSS-R satellite constellation that uses this principle to monitor **hurricane intensity** by retrieving ocean surface wind speeds even under heavy clouds or rain.

### 2. Soil Moisture and Land Surface Monitoring

On land, GNSS-R has been applied to measure **soil moisture**, an important parameter for hydrology, agriculture, and climate modeling. Moist soil reflects GNSS signals differently than dry soil due to changes in **dielectric properties**. By analyzing the reflected signal strength and delay, researchers can derive **soil moisture content** over broad areas, including regions not well-covered by traditional remote sensing satellites.

Similarly, **snow depth and snow water equivalent** can be estimated using GNSS-R, as snow modifies the signal delay and attenuation properties. This is useful in mountainous or polar regions where conventional sensors struggle due to terrain or cloud cover.

### 3. Ice and Cryosphere Monitoring

The cryosphere is another promising application area. Ice sheets and sea ice surfaces cause strong specular reflections, allowing GNSS-R to detect **ice coverage**, **melt events**, and **ice-water boundaries**. This data supports climate monitoring and polar research.

### 4. Inland Water Monitoring

GNSS-R is capable of identifying and monitoring **inland water bodies** such as lakes and rivers. These surfaces produce sharp, coherent reflections, enabling not only detection of water presence but also estimation of **water levels** through signal delays.

## Advantages of GNSS-R

GNSS-R offers several compelling advantages over traditional remote sensing methods:

*   **Passive and Non-Invasive**: GNSS-R uses existing signals from navigation satellites, avoiding the need for active transmitters and minimizing power usage.
*   **All-Weather Capability**: GNSS L-band signals penetrate clouds, rain, and vegetation, making GNSS-R effective under nearly all weather conditions.
*   **High Temporal Resolution**: With thousands of GNSS satellites continuously transmitting, GNSS-R systems benefit from high revisit rates and temporal coverage.
*   **Cost-Effectiveness**: GNSS-R receivers are compact and low-cost, suitable for deployment on **CubeSats**, **drones**, or **ground-based sensors**.
*   **Global Coverage**: Thanks to global GNSS constellations, GNSS-R observations can be made nearly anywhere on Earth.

## Challenges and Limitations

Despite its potential, GNSS-R faces several challenges:

*   **Weak Reflected Signals**: Reflected GNSS signals are typically 20–30 dB weaker than direct signals, requiring sensitive antennas and signal processing algorithms.
*   **Complex Inversion Models**: Translating GNSS-R observables (e.g., DDMs) into physical parameters like soil moisture or sea state requires sophisticated modeling and calibration.
*   **Multipath and Interference**: In ground-based or urban settings, distinguishing between useful reflections and multipath can be difficult.
*   **Limited Vertical Resolution**: While GNSS-R provides wide coverage, it typically offers coarser resolution compared to active sensors like LiDAR or synthetic aperture radar (SAR).

## Future Outlook

GNSS-R continues to gain traction in both scientific and operational remote sensing. Future GNSS-R missions may benefit from improved antenna designs, onboard signal processing, and integration with other data sources (e.g., SAR, optical). With the growth of **low-cost small satellites** and the increasing density of GNSS constellations, GNSS-R is positioned to become a key component in the **next generation of Earth observation systems**.

The integration of GNSS-R data into operational climate models, disaster response frameworks, and environmental monitoring networks will further establish its role as a **disruptive technology in passive remote sensing**.

## Conclusion

GNSS Reflectometry is a novel and transformative approach to remote sensing, offering unique advantages in terms of cost, coverage, and resilience. By repurposing navigation signals for environmental observation, GNSS-R opens new avenues for studying Earth’s surface and atmosphere in a sustainable and scalable manner. From ocean winds to soil moisture, and from cryosphere monitoring to inland water detection, the applications of GNSS-R are vast and growing. As technology continues to mature, GNSS-R is likely to play a critical role in the future of Earth science and environmental monitoring.

