- solved by @cooku222

해당 문제는 타원곡선암호를 활용한 문제이다.
곡선 수식 : y^2 = x^3 + 1

⁨```

cooku222@cooku222s-MacBook-Air  ~  nc curve.ctf.pascalctf.it 5004 
Curve Ball y^2 = x^3 + 1 (mod 1844669347765474229) 
n = 1844669347765474230 
G = (27, 728430165157041631) 
Q = (1753528433016782337, 1162935768517290687) 
1. Guess secret 
2. Compute k * P 
3. Exit

⁩```

필요한 값은 주어지니까 위 n, g, q로 n을 인수분해 한 후 secret 값을 구한 뒤
1을 입력해 secret 프롬프트를 열어 구한 값을 입력하면 플래그를 획득할 수 있다.

- Flag: pascalCTF{sm00th_0rd3rs_m4k3_3cc_n0t_s0_h4rd_4ft3r_4ll}
