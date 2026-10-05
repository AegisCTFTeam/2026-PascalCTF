
- solved by @cooku222
  
28개 단어 전부를 오라클로 암호화해서 `hex→word` 코드북 만들고, 마지막 Ciphertext 5개 블록을 역매핑해서 그대로 게싱하는 문제
```
Give me 4 words to encrypt or don't write anything to quit (max 16 chars): 
Word 1: biocompatibility 
Word 2: biodegradability 
Word 3: characterization 
Word 4: contraindication 
Encrypted words: 610a736a02ae4ed99255250dc6913806 
96e93b54a16e0e1f406604fb8995496d 
98796a749e87d4b81fd997e330e72f0b 
054530424826e4735453d81abb1ecda8
```
서버에 접속하면 제공받은 코드 위주로 라운드 1을 입력해준다. 
마찬가지로 라운드 7까지 반복해준다.

라운드 2 

counterbalancing

counterintuitive

decentralization

disproportionate

라운드 3

electrochemistry

electromagnetism

environmentalist

internationality

라운드 4

internationalism

institutionalize

microlithography

microphotography

라운드 5

misappropriation

mischaracterized

miscommunication

misunderstanding

라운드 6

photolithography

phonocardiograph

psychophysiology

rationalizations

라운드 7 

representational

responsibilities

transcontinental

unconstitutional

6c9ae1ba52aaa2863a282c5d183d0587 → responsibilities

96e93b54a16e0e1f406604fb8995496d → biodegradability

caef6a02eaa41b11f05bf75025b94665 → misunderstanding

caef6a02eaa41b11f05bf75025b94665 → misunderstanding 

9cfc87ef4f5791483f52fac9598121cf → internationality

마지막 프롬프트에서 게싱하라는 프롬프트가 나오고 위의 값을 순서대로 입력해주면 맞았다면서 플래그를 준다
