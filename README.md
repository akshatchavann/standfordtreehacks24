Inspiration
What happens when you can’t be there for your grandparents during a medical crisis? Our team, all of whom have grandparents living in distant senior homes, face a dilemma. Though the declining health and isolation of these family members necessitates external care during emergencies, this need is not easily met due to the high cost and scarcity of full-time caregivers. Additionally, in the event you can’t be with your loved ones in an emergency, first responders may not have personal medical knowledge that could be the difference between life or death.

Because of this issue, we saw the need to build a platform that serves as a “caretaker” for senior citizens in times of medical emergencies. This problem has large implications – in the US, 27% of the population over 60 lives by themselves, which accounts for 29 million annual emergency department visits. We sought to build a solution that could provide senior citizens with medical instructions and communicate life-saving information to first respondents on the scene. By doing so, we hope to give families confidence and peace of mind no matter the distance separating them and their loved ones.

What it does
MediLife is an integrated platform that 1) monitors vital indicators of senior citizen health including head movement, heart rate, and facial positioning 2) releases an AI agent that provides medical directives immediately after detection of abnormal vital signs (ex. cardiac arrest, faints, falls) and 3) notifies first respondents and provides a summarized report of time of emergency, medical history, and current medications. MediLife aims to significantly improve efficiency of medical treatment within the first 20 minutes of a senior citizen emergency.

How we built it
We built MediLife using a suite of tools and technologies, split up into 3 components: the AI agent, the computer vision model, and the vitals monitoring. These individual components were then combined together cohesively in a front end providing a simple but effective user interface for both senior citizens and first responders.

The AI Agent was developed using OpenAI’s GPT-4 model. We implemented OpenAI’s text-to-speech voice and React’s built in speech-to-text to simulate a real conversation with an AI Nurse. We prompt engineered GPT to understand the data it is receiving from our CV and heart rate monitor to allow the nurse to have impactful medical questions and advice.

The computer vision model was built using pre-trained TensorFlow.js models that specialize in facial detection and body language. We calculated different ways to interpret danger like feints or seizures using the model’s data.

For vitals monitoring, we incorporated hardware into this aspect of our hack to track the heart rate of patients via a HW-827 pulse sensor, an arduino board, and other electrical components. The HW-827 pulse sensor attaches to the fingertip of the senior citizen, shines a green light onto the finger, measures the amount of reflected light with a photosensor, and finally obtains a heart-beat pulse reading. The live data coming from the sensor is then transmitted into arduino code and then through a serial port parser into the program's Node.JS backend.

The front-end of MediLife shows a camera facing the senior citizen as well as a live activity feed and vitals monitoring data. All of the components are connected using React.

Challenges we ran into
One of the primary challenges we ran into was measuring vitals of senior citizens and transmitting that live data into the back end server. Originally, our team wanted to use an Apple Watch to collect heart rate and blood oxygen data; however, this process required using Swift and a MacOS device which we did not have access to. We then tried to pivot to a myZone activity belt tracker in conjunction with Terra API; this required an Android device which we also did not have access to. We were then left with the final solution to incorporate a hardware sensor using a pulse reader which was not extremely accurate in its heart beat readings. In an ideal world, the senior citizen would have a piece of wearable technology that would transfer vital data.

Another challenge we faced was the prompt engineering of the AI agent to best address the medical information based on the medical information collected. We found difficulty in getting the AI agent to ask effective questions and provide accurate responses to the senior citizen indicating the best course of action to take. After a lot of fine-tuning and tweaking, we were able to improve the quality of the nurse’s questions, but there’s certainly more room for improvement.

Lastly, our team went through many iterations of an intuitive and effective conversation structure. Simulating a real human conversation with pauses, language, and user interactivity was difficult and took a lot of testing. It was also a challenge to feed the model enough relevant data about the medical conversation so that it could have enough knowledge to be helpful.

Accomplishments that we're proud of
We take particular pride in integrating advanced trigger detectors through the use of TensorFlow and pulse sensing technology. The development of an AI avatar that directly communicates with the patient also stands out as a highlight. Most significantly, our team has successfully developed a working MVP that promises to extend its benefits beyond our immediate families, potentially impacting the lives of millions of elderly individuals and their families across the globe.

What we learned
How to integrate a HW-287 pulse sensor into a full-stack project Prompt engineering scripts to yield an effective AI pilot Developing genuine conversation structures using OpenAI TensorFlow with Javascript to flag unusual head and face movements Web sockets and serial ports to integrate live arduino data

What's next for MediLive
Next steps for MediLive possibly include tracking more vital signs through both camera computer vision and body sensors including blood pressure and oxygen, respiratory rate, and body temperature. It will be important to strike a balance between using an abundance of tracking sensors and monitors and not impairing the movement of the senior citizen. We also believe there are opportunities to refine the AI agent in terms of medical advice it can provide to the senior citizens using historical data, medical information, and other analysis of the emergency. A more fleshed out version of our product could integrate with smart home devices like Google Home and Amazon Alexa, as well as be trained on an even more advanced LLM model which could have more functionality like telling a respondent step-by-step how to do a Heimlich Maneuver or CPR.
