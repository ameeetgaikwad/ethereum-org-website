---
title: एथेरियम बूटनोड्स का परिचय
description: बूटनोड्स को समझने के लिए आवश्यक बुनियादी जानकारी
lang: hi
---

जब कोई नया नोड एथेरियम नेटवर्क में शामिल होता है, तो उसे नए साथियों की खोज करने के लिए पहले से ही नेटवर्क पर मौजूद नोड्स से कनेक्ट करने की आवश्यकता होती है। एथेरियम नेटवर्क में इन प्रवेश बिंदुओं को बूटनोड्स कहा जाता है। क्लाइंट के पास आमतौर पर बूटनोड्स की एक सूची होती है जो उनमें हार्डकोड की जाती है। ये बूटनोड आमतौर पर Ethereum फाउंडेशन की डेवऑप्स टीम या क्लाइंट टीमों द्वारा स्वयं चलाए जाते हैं। ध्यान दें कि बूटनोड स्टेटिक नोड्स के समान नहीं हैं। स्टेटिक नोड्स को बार-बार बुलाया जाता है, जबकि बूटनोड्स को केवल तभी बुलाया जाता है जब कनेक्ट करने के लिए पर्याप्त सहकर्मी नहीं होते हैं और नोड को कुछ नए कनेक्शन बूटस्ट्रैप करने की आवश्यकता होती है।

## बूटनोड से कनेक्ट करें {#connect-to-a-bootnode}

अधिकांश क्लाइंट के पास बूटनोड्स की एक सूची होती है, लेकिन आप अपना स्वयं का बूटनोड भी चलाना चाह सकते हैं, या क्लाइंट की हार्डकोडेड सूची का हिस्सा नहीं होने वाले का उपयोग कर सकते हैं। इस मामले में, आप अपने क्लाइंट को शुरू करते समय उन्हें निर्दिष्ट कर सकते हैं, जैसा कि निम्नानुसार है (उदाहरण Geth के लिए है, कृपया अपने ग्राहक का प्रलेखन देखें):

```
geth --bootnodes "enode://<node ID>@<IP address>:<port>"
```

## बूटनोड चलाएँ {#run-a-bootnode}

बूटनोड्स पूर्ण नोड्स हैं जो NAT ([नेटवर्क एड्रेस ट्रांसलेशन](https://www.geeksforgeeks.org/network-address-translation-nat/)) के पीछे नहीं होते हैं। प्रत्येक पूर्ण नोड बूटनोड के रूप में कार्य कर सकता है जब तक कि यह सार्वजनिक रूप से उपलब्ध हो।

जब आप एक नोड शुरू करते हैं तो उसे आपके [ईनोड](/developers/docs/networking-layer/network-addresses/#enode) को लॉग करना चाहिए, जो एक सार्वजनिक पहचानकर्ता है जिसका उपयोग अन्य आपके नोड से कनेक्ट करने के लिए कर सकते हैं।

ईनोड आमतौर पर प्रत्येक पुनरारंभ पर पुनः उत्पन्न होता है, इसलिए अपने बूटनोड के लिए लगातार ईनोड उत्पन्न करने के तरीके पर अपने क्लाइंट के प्रलेखन को देखना सुनिश्चित करें।

एक अच्छा बूटनोड होने के लिए, साथियों की अधिकतम संख्या बढ़ाना एक अच्छा विचार है जो इससे जुड़ सकते हैं। कई साथियों के साथ बूटनोड चलाने से बैंडविड्थ की आवश्यकता में काफी वृद्धि होगी।

## उपलब्ध बूटनोड {#available-bootnodes}

गो-एथेरियम के भीतर बिल्टिन बूटनोड्स की एक सूची [यहां](https://github.com/ethereum/go-ethereum/blob/master/params/bootnodes.go#L23) पाई जा सकती है। इन बूटनोड्स का रखरखाव Ethereum फाउंडेशन और गो-एथेरियम टीम द्वारा किया जाता है।

स्वयंसेवकों द्वारा बनाए गए बूटनोड्स की अन्य सूचियां उपलब्ध हैं। कृपया हमेशा कम से कम एक आधिकारिक बूटनोड शामिल करना सुनिश्चित करें, अन्यथा आप पर ग्रहण का हमला किया जा सकता है।
