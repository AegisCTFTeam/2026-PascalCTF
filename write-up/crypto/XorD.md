
- solved by @cooku222

해당 문제코드는 `random.seed(1337)`로 고정된 PRNG 바이트 스트림을 만들고, 그걸 플래그 각 바이트랑 XOR해서 `output.txt`에 hex로 저장하고 있습니다.
복호화를 위해 대칭인 `seed(1337)`를 생성하고 같은 난수 키를 다시 생성한 뒤, `plaintext_byte = ciphertext_byte ^ random_key` 를 해주면 플래그를 얻을 수 있습니다.
- Flag: pascalCTF{1ts_4lw4ys_4b0ut_x0r1ng_4nd_s33d1ng}
