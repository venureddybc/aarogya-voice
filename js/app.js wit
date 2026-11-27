const languageSelect = document.getElementById("language");
const questionInput = document.getElementById("question");
const answerOutput = document.getElementById("answer");
const statusOutput = document.getElementById("status");

const replies = {
  "en-IN": {
    water: "Drink water regularly throughout the day. Needs vary with weather, activity and health. Ask a healthcare professional if you have a condition that limits fluids.",
    sleep: "Keep a regular sleep schedule, reduce screen use before bedtime and make your room comfortable. If sleep problems continue, speak with a healthcare professional.",
    pressure: "Blood pressure can only be assessed reliably with a suitable measurement. Follow your clinician's advice and do not start or stop medicine on your own.",
    emergency: "Chest pain can be an emergency. Call 112 in India or seek emergency medical care now. Do not drive yourself."
  },
  "kn-IN": {
    water: "ದಿನವಿಡೀ ನಿಯಮಿತವಾಗಿ ನೀರು ಕುಡಿಯಿರಿ. ನೀರಿನ ಅಗತ್ಯವು ಹವಾಮಾನ, ಚಟುವಟಿಕೆ ಮತ್ತು ಆರೋಗ್ಯದ ಮೇಲೆ ಅವಲಂಬಿತವಾಗಿರುತ್ತದೆ.",
    sleep: "ಪ್ರತಿದಿನ ಒಂದೇ ಸಮಯಕ್ಕೆ ಮಲಗಲು ಪ್ರಯತ್ನಿಸಿ. ಮಲಗುವ ಮೊದಲು ಮೊಬೈಲ್ ಬಳಕೆಯನ್ನು ಕಡಿಮೆ ಮಾಡಿ. ಸಮಸ್ಯೆ ಮುಂದುವರಿದರೆ ಆರೋಗ್ಯ ತಜ್ಞರನ್ನು ಸಂಪರ್ಕಿಸಿ.",
    pressure: "ರಕ್ತದೊತ್ತಡವನ್ನು ಸರಿಯಾದ ಸಾಧನದಿಂದ ಅಳೆಯಬೇಕು. ವೈದ್ಯರ ಸಲಹೆಯಿಲ್ಲದೆ ಔಷಧಿಯನ್ನು ಪ್ರಾರಂಭಿಸಬೇಡಿ ಅಥವಾ ನಿಲ್ಲಿಸಬೇಡಿ.",
    emergency: "ಎದೆನೋವು ತುರ್ತು ಪರಿಸ್ಥಿತಿಯಾಗಿರಬಹುದು. ಭಾರತದಲ್ಲಿ 112ಕ್ಕೆ ಕರೆ ಮಾಡಿ ಅಥವಾ ತಕ್ಷಣ ತುರ್ತು ವೈದ್ಯಕೀಯ ಸಹಾಯ ಪಡೆಯಿರಿ."
  },
  "te-IN": {
    water: "రోజంతా క్రమం తప్పకుండా నీరు తాగండి. నీటి అవసరం వాతావరణం, శారీరక శ్రమ మరియు ఆరోగ్యంపై ఆధారపడి ఉంటుంది.",
    sleep: "ప్రతిరోజూ ఒకే సమయానికి నిద్రపోవడానికి ప్రయత్నించండి. నిద్రకు ముందు ఫోన్ వాడకాన్ని తగ్గించండి. సమస్య కొనసాగితే వైద్య నిపుణులను సంప్రదించండి.",
    pressure: "రక్తపోటును సరైన పరికరంతో కొలవాలి. వైద్యుల సలహా లేకుండా మందులు ప్రారంభించకండి లేదా ఆపకండి.",
    emergency: "ఛాతి నొప్పి అత్యవసర పరిస్థితి కావచ్చు. భారతదేశంలో 112కు కాల్ చేయండి లేదా వెంటనే అత్యవసర వైద్య సహాయం పొందండి."
  },
  "hi-IN": {
    water: "दिनभर नियमित रूप से पानी पिएँ। पानी की ज़रूरत मौसम, गतिविधि और स्वास्थ्य पर निर्भर करती है।",
    sleep: "रोज़ एक ही समय पर सोने की कोशिश करें और सोने से पहले स्क्रीन का उपयोग कम करें। समस्या बनी रहे तो स्वास्थ्य विशेषज्ञ से बात करें।",
    pressure: "ब्लड प्रेशर सही उपकरण से मापना चाहिए। डॉक्टर की सलाह के बिना दवा शुरू या बंद न करें।",
    emergency: "सीने में दर्द आपात स्थिति हो सकती है। भारत में 112 पर कॉल करें या तुरंत आपातकालीन चिकित्सा सहायता लें।"
  },
  "ta-IN": {
    water: "நாள் முழுவதும் சீராக தண்ணீர் குடிக்கவும். தேவையான அளவு வானிலை, உடல் செயல்பாடு மற்றும் உடல்நிலையைப் பொறுத்தது.",
    sleep: "தினமும் ஒரே நேரத்தில் தூங்க முயற்சிக்கவும். தூங்குவதற்கு முன் திரை பயன்பாட்டைக் குறைக்கவும். பிரச்சினை தொடர்ந்தால் மருத்துவரை அணுகவும்.",
    pressure: "இரத்த அழுத்தத்தை சரியான கருவியால் அளவிட வேண்டும். மருத்துவரின் ஆலோசனை இல்லாமல் மருந்தைத் தொடங்கவோ நிறுத்தவோ வேண்டாம்.",
    emergency: "மார்பு வலி அவசரநிலையாக இருக்கலாம். இந்தியாவில் 112-ஐ அழைக்கவும் அல்லது உடனடியாக அவசர மருத்துவ உதவியைப் பெறவும்."
  }
};

function getTopic(text) {
  const q = text.toLowerCase();
  if (/chest pain|chest hurts|heart attack|ಎದೆನೋವು|ఛాతి నొప్పి|सीने में दर्द|மார்பு வலி/.test(q)) return "emergency";
  if (/water|hydration|drink|ನೀರು|నీరు|पानी|தண்ணீர்/.test(q)) return "water";
  if (/sleep|insomnia|ನಿದ್ರೆ|నిద్ర|नींद|தூக்கம்/.test(q)) return "sleep";
  if (/blood pressure|bp|ರಕ್ತದೊತ್ತಡ|రక్తపోటు|ब्लड प्रेशर|இரத்த அழுத்தம்/.test(q)) return "pressure";
  return "general";
}

function answerQuestion() {
  const lang = languageSelect.value;
  const question = questionInput.value.trim();
  if (!question) {
    statusOutput.textContent = "Please type a question or use the Speak button.";
    return;
  }
  const topic = getTopic(question);
  const general = {
    "en-IN": "I can share only general information in this demo. Try asking about water, sleep, blood pressure or chest pain. For personal medical advice, contact a qualified healthcare professional.",
    "kn-IN": "ಈ ಮಾದರಿಯಲ್ಲಿ ಸಾಮಾನ್ಯ ಆರೋಗ್ಯ ಮಾಹಿತಿಯನ್ನು ಮಾತ್ರ ನೀಡಬಹುದು. ನೀರು, ನಿದ್ರೆ ಅಥವಾ ರಕ್ತದೊತ್ತಡದ ಬಗ್ಗೆ ಕೇಳಿ. ವೈಯಕ್ತಿಕ ಸಲಹೆಗೆ ವೈದ್ಯರನ್ನು ಸಂಪರ್ಕಿಸಿ.",
    "te-IN": "ఈ నమూనాలో సాధారణ ఆరోగ్య సమాచారం మాత్రమే అందించగలను. నీరు, నిద్ర లేదా రక్తపోటు గురించి అడగండి. వ్యక్తిగత సలహా కోసం వైద్యుడిని సంప్రదించండి.",
    "hi-IN": "यह डेमो केवल सामान्य स्वास्थ्य जानकारी देता है। पानी, नींद या ब्लड प्रेशर के बारे में पूछें। व्यक्तिगत सलाह के लिए डॉक्टर से संपर्क करें।",
    "ta-IN": "இந்த மாதிரி பொதுவான சுகாதார தகவலை மட்டுமே வழங்கும். தண்ணீர், தூக்கம் அல்லது இரத்த அழுத்தம் பற்றி கேளுங்கள். தனிப்பட்ட ஆலோசனைக்கு மருத்துவரை அணுகவும்."
  };
  answerOutput.textContent = topic === "general" ? general[lang] : replies[lang][topic];
  statusOutput.textContent = "Demo response generated.";
}

document.getElementById("askBtn").addEventListener("click", answerQuestion);

document.getElementById("speakBtn").addEventListener("click", () => {
  if (!("speechSynthesis" in window)) {
    statusOutput.textContent = "Text-to-speech is not supported in this browser.";
    return;
  }
  window.speechSynthesis.cancel();
  const utterance = new SpeechSynthesisUtterance(answerOutput.textContent);
  utterance.lang = languageSelect.value;
  window.speechSynthesis.speak(utterance);
});

document.getElementById("micBtn").addEventListener("click", () => {
  const SpeechRecognition = window.SpeechRecognition || window.webkitSpeechRecognition;
  if (!SpeechRecognition) {
    statusOutput.textContent = "Speech recognition is not supported here. Try Chrome or type your question.";
    return;
  }
  const recognition = new SpeechRecognition();
  recognition.lang = languageSelect.value;
  recognition.interimResults = false;
  recognition.maxAlternatives = 1;
  statusOutput.textContent = "Listening…";
  recognition.onresult = event => {
    questionInput.value = event.results[0][0].transcript;
    statusOutput.textContent = "Speech captured. Getting your answer…";
    answerQuestion();
  };
  recognition.onerror = event => {
    statusOutput.textContent = "Microphone error: " + event.error + ". Check permission or type your question.";
  };
  recognition.onend = () => {
    if (statusOutput.textContent === "Listening…") statusOutput.textContent = "No speech detected. Please try again.";
  };
  recognition.start();
});
