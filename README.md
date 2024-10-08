# PalmPet: A Handheld Ultrasonic Haptic Accessory to Enhance Mobile AR Experiences

<img width="962" alt="image" src="https://github.com/user-attachments/assets/3d0c566e-6200-48f1-94a9-5700731e331b">


The PalmPet system is an innovative handheld ultrasonic haptic accessory designed to enhance mobile AR experiences. It offers two distinct interaction scenarios: Cloud Anchor Mode for placing and feeling virtual pets on the palm, and Depth Recognition Mode for perceiving real-world objects through the smartphone screen. Both modes utilize an 8x8 phased array of ultrasonic transducers mounted on the back of the smartphone to generate focused ultrasound waves, creating mid-air tactile sensations corresponding to virtual pets or detected objects. The Cloud Anchor Mode also enables users to summon previously placed pets from the cloud, allowing for persistent and shared AR experiences across multiple sessions or devices. This unique blend of visual and tactile feedback, coupled with cloud-based persistence, significantly enhances the immersion and interactivity of mobile AR applications.

## GIF Demo
- PalmPet App
![351a357416636f1b1ce11b3509de6766-ezgif com-optimize](https://github.com/user-attachments/assets/ff79bdf3-6ee2-46ed-8131-b67241f66f50)

- Windows .exe
![Screen-Recording-2024-09-10T10_20_33 680Z-ezgif com-speed](https://github.com/user-attachments/assets/17e30add-f93c-404d-bde0-68d1f7570888)



## Acknowledgements

- The mini PAT board was developed by Dr. Ryuji Hirayama and Ben Kazemi.
- The acoustic phase retrieval algorithm GS-PAT was developed by Diego Martinez, Ryuji Hirayama, Roberto A. Montano-Murillo, and Sriram Subramanian. 2020. GS-PAT: high-speed multi-point sound-fields for phased arrays of transducers. ACM Transactions on Graphics 39, 4 (2020), 138. https://doi.org/10.1145/3386569.3392492
- I acknowledge the use of Claude 3.5 Sonnet (Anthropic) to summarize initial notes and literature reviews and to solve bugs during development.
- I used [LouisFoucard/DepthMap_dataset](https://github.com/LouisFoucard/DepthMap_dataset) when evaluating the system latency and clustering algorithms. This Python Blender script generates random scenes, depth maps, and corresponding stereo images for machine learning.
- Many thanks to my supervisor Ryuji for providing the mini PAT, project idea, and acoustic haptic modulation methods.

## Research Context
The swift advancement of mobile AR technologies has profoundly influenced how individuals engage with digital content, catalyzing a heightened demand for novel accessories that improve these interactions. Mobile haptics, which entails the integration of haptic technology into mobile devices, enables users to experience tactile feedback while navigating virtual spaces, enriching their overall engagement. Recent advancements in haptic feedback technology underscore the importance of sophisticated tactile responses and adaptive algorithms in boosting user engagement.

## Research Problem
The research problem centers on understanding how various factors influence the effectiveness of multimodal feedback in a mobile handheld ultrasonic mid-air haptic device that is integrated with cloud services. Specifically, this study investigates the impact of depth confidence levels, clustering accuracy, and latency on the performance of haptic interactions. Challenges include inadequate Quality of Service in existing networks, the need for ultra-low latency, and insufficient computing power limiting the implementation of advanced rendering algorithms.

## Solution
PalmPet is an innovative solution designed to enhance mobile AR experiences by integrating sophisticated mid-air haptic feedback systems. The system utilizes an 8x8 phased array of ultrasonic transducers mounted on the back of a smartphone, effectively bridging the gap in mobile AR applications while maintaining portability. PalmPet features two scenarios: interacting with virtual pets on the palm and perceiving real-world objects through the smartphone screen. The operational framework includes a Mini PAT board for initial haptic processing, with data transmitted to a laptop for further computation via the GS-PAT solver.

## Results
The PalmPet system demonstrates the potential of integrating ultrasonic haptic feedback with mobile augmented reality applications. Latency measurements revealed that the GSPATComputation stage in the C++ application was the primary bottleneck, accounting for 81.3% of the total latency. In the Android app, the sendDepthBoxVertices operation had the highest average latency at 22.5 ms. The custom clustering algorithm implemented in the PalmPet application showed a balance between computational efficiency and real-time performance, crucial for mobile AR applications. The depth confidence value played a crucial role in both system latency and clustering accuracy. Environmental factors such as lighting conditions, object distance, and surface properties significantly impacted clustering accuracy in depth image analysis. 

## Contribution

The PalmPet system makes several significant contributions to the field of mobile augmented reality and haptic feedback. By demonstrating a novel integration of ultrasonic mid-air haptic feedback with mobile AR, this research provides a valuable framework for future developments in this area. The comparative study of custom, DBSCAN, and K-means clustering algorithms offers crucial insights into the trade-offs between clustering quality and computational efficiency in real-time AR applications. Through detailed analysis of latency across different system components, this study establishes a benchmark for future optimizations, particularly highlighting the importance of efficient acoustic field computations. The research elucidates the critical role of depth confidence in balancing system responsiveness and haptic feedback accuracy, offering guidance for future depth-sensing AR applications. By identifying and analyzing environmental factors affecting depth sensing and clustering accuracy, this study contributes to a better understanding of the practical challenges in deploying AR haptic systems in diverse settings. The development and evaluation of two distinct interaction modes (Cloud Anchor and Depth Recognition) expand the potential use cases for haptic-enhanced AR applications. These contributions collectively advance the state-of-the-art in mobile AR haptics, providing a solid foundation for future research and development in this emerging field.

## Limitations

The PalmPet system, while innovative, faces several limitations that warrant consideration. The computational demands of real-time haptic rendering pose significant challenges for mobile devices with limited processing power. This constraint affects the system's ability to deliver consistent, high-quality haptic feedback, especially in complex AR scenarios. The accuracy of depth sensing and object recognition is heavily influenced by environmental factors such as lighting conditions, object distances, and surface properties. Reflective, transparent, or very dark surfaces can lead to inaccurate or missing depth data, complicating the clustering process and potentially resulting in fragmented or inaccurate object representations. The system's performance is also affected by rapid movements, which can introduce motion blur and impact depth accuracy. The integration of haptic feedback with visual and auditory components in dynamic AR environments presents substantial synchronization challenges, often leading to inconsistencies in user experience. Additionally, the current implementation may not be fully accessible to users with disabilities, limiting its potential user base. The reliance on specialized hardware and complex configurations could impede the broad adoption of this haptic technology in mobile AR applications. These limitations highlight the need for further research and development to enhance the robustness, accuracy, and accessibility of mobile AR haptic systems.

## Future Work

Looking ahead, several promising avenues for future work emerge from this research. The Palmpet AR App can be further developed into an more compledted AR game with a more diverse range of haptic feedback, for example, there could be different types of haptic feedback patterns for different pets summoned and different magic spells. On the other hand, optimizing the GSPAT solver implementation could significantly reduce latency in haptic feedback generation, addressing one of the primary performance bottlenecks identified in this study. Enhancing depth sensing technologies and developing more sophisticated clustering algorithms could lead to more accurate object detection and interaction in AR environments, improving the overall user experience. Future iterations of the system could explore ways to perform more haptic computations on-device, reducing reliance on external processing and potentially decreasing overall system latency. Investigating advanced haptic rendering techniques could expand the range and realism of tactile sensations, further enhancing the immersive quality of AR experiences. Conducting comprehensive user studies would provide valuable insights into the perceptual aspects of mid-air haptic feedback in mobile AR contexts, guiding future refinements. As mobile hardware capabilities c
