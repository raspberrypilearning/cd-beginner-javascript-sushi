## खेल रीसेट करें

फिलहाल, आपको हर बार नया राउंड खेलना चाहते हुए पृष्ठ को फिर से लोड करना होगा। एक **रीसेट गेम**वेब पृष्ठपर बटन है, लेकिन बटन पर क्लिक करने से कोई प्रभाव नहीं पड़ता है।

बटन को काम करने के लिए, आप इसे एक इवेंट श्रोता से कनेक्ट करने जा रहे हैं और कॉल करने के लिए उस श्रोता के लिए एक फ़ंक्शन में अपना गेम कोड रैप करें।

--- task ---

गेम को रीसेट करने के लिए आवश्यक गेम कोड वह कोड होता है जो `answerButton` वेरिएबल और `for` लूप सेट करता है। अपने कोड के उन टुकड़ों को लें और उन्हें `startGame` नामक फ़ंक्शन में रखें ।

```JavaScript
function startGame() {

  var answerButton = Math.round(Math.random() * (buttons.length - 1));

  for (var i = 0; i < buttons.length; i++) {

    var red = makeColourValue();
    var green = makeColourValue();
    var blue = makeColourValue();

    setButtonColour(buttons[i], red, green, blue);

    if (i === answerButton) {
      heading.innerHTML = `(${red}, ${green}, ${blue})`;
    }

    buttons[i].addEventListener('click', function(){
        if (this === buttons[answerButton]) {
            answerMessage.innerHTML = "Correct!";
        } else {
            answerMessage.innerHTML = "Wrong answer! Guess again!";
        }
    });

  }

}
```

--- /task ---

यदि आप अभी वेब पेज को पुनः लोड करते हैं, तो कुछ भी काम नहीं करता है! ऐसा इसलिए, क्योंकि आपके कार्यक्रम के अन्य सभी कार्यों की तरह, आपको `startGame` **call** करने की आवश्यकता है, अन्यथा आपका खेल शुरू नहीं होता है।

--- task ---

`startGame` फंक्शन को कॉल करने के लिए अपने प्रोग्राम के __अंत में एक__ पंक्ति जोड़ें ।

```JavaScript
startGame();
```

--- /task ---

`startGame` फ़ंक्शन को वेब पृष्ठ के`answerMessage`तत्व को भी साफ़ करना होगा, ताकि खेल का एक नया दौर शुरू होने पर कोई संदेश न हो।

--- task ---

तत्व को साफ़ करने के लिए, `startGame` फंक्शन के शुरुआत में निम्न पंक्ति **को जोड़ें** ।

```JavaScript
answerMessage.innerHTML = "";
```

--- /task ---

**रीसेट गेम** बटन पर क्लिक करना अभी भी कुछ नहीं करता है। ऐसा इसलिए है क्योंकि बटन को एक इवेंट श्रोता की आवश्यकता है जो कॉल करता है `startGame` । आप पहले से ही जानते हैं कि बटनों पर क्लिक करने के लिए इवेंट श्रोताओं को कैसे जोड़ना है, इसलिए यदि आप चाहते हैं, तो आप निर्देशों को देखने से पहले खुद से ऐसा करने की कोशिश कर सकते हैं!

--- task ---

**गेम रीसेट** बटन के काम में दो चरण शामिल हैं:
 - इसके `id` का उपयोग करके बटन का चयन करें, जो `resetButton` है
 - बटन क्लिक करने पर `startGame` फंक्शन को कॉल करने के लिए एक श्रोता को बटन पर जोड़ें

ऐसा करने के लिए अपने कार्यक्रम के अंत में इस पंक्ति को जोड़ें:

```JavaScript
document.getElementById('resetButton').addEventListener('click', startGame);
```

क्या आप देखते हैं कि श्रोता सीधे यहां बटन में जुड़ जाता है, बिना बटन पहले एक वेरिएबल में संग्रहीत किया जा रहा है?

मैंने इसे इस तरह कोड करने का फैसला किया क्योंकि गेम कोड को **रीसेट गेम**बटन की किसी अन्य स्थान पर की आवश्यकता नहीं है, इसलिए मैं वेरिएबल को संग्रहीत करने के लिए आवश्यक मेमोरी को बचा सकता हूं।

पहले एक वेरिएबल में बटन को संग्रहीत करने की दूसरी विधि और फिर एक श्रोता को जोड़ना भी ठीक काम करता है।

--- /task ---

अब अपने खेल की कोशिश करो! जब आपको सही उत्तर मिल जाए, तो **रीसेट गेम** बटन पर क्लिक करें और सब कुछ सही तरह काम कर रहा है यह चेक करें।