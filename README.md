MediLife is an integrated platform that 1) monitors vital indicators of senior citizen health including head movement, heart rate, and facial positioning 2) releases an AI agent that provides medical directives immediately after detection of abnormal vital signs (ex. cardiac arrest, faints, falls) and 3) notifies first respondents and provides a summarized report of time of emergency, medical history, and current medications. MediLife aims to significantly improve efficiency of medical treatment within the first 20 minutes of a senior citizen emergency.



We built MediLife using a suite of tools and technologies, split up into 3 components: the AI agent, the computer vision model, and the vitals monitoring. These individual components were then combined together cohesively in a front end providing a simple but effective user interface for both senior citizens and first responders.

The AI Agent was developed using OpenAI’s GPT-4 model. We implemented OpenAI’s text-to-speech voice and React’s built in speech-to-text to simulate a real conversation with an AI Nurse. We prompt engineered GPT to understand the data it is receiving from our CV and heart rate monitor to allow the nurse to have impactful medical questions and advice.

The computer vision model was built using pre-trained TensorFlow.js models that specialize in facial detection and body language. We calculated different ways to interpret danger like feints or seizures using the model’s data.

For vitals monitoring, we incorporated hardware into this aspect of our hack to track the heart rate of patients via a HW-827 pulse sensor, an arduino board, and other electrical components. The HW-827 pulse sensor attaches to the fingertip of the senior citizen, shines a green light onto the finger, measures the amount of reflected light with a photosensor, and finally obtains a heart-beat pulse reading. The live data coming from the sensor is then transmitted into arduino code and then through a serial port parser into the program's Node.JS backend.

The front-end of MediLife shows a camera facing the senior citizen as well as a live activity feed and vitals monitoring data. All of the components are connected using React.
