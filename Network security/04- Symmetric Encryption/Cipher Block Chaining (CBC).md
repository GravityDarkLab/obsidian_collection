![[Pasted image 20240103072505 1.png]]

	$c_i =Enc_k (c_{i−1}\oplus m_i)$
⇔ $Dec_k(c_i) = Dec_k(Enc_k(c_{i−1} \oplus m_i))$
⇔ $Dec_k(c_i)=c_{i−1} \oplus m_i$
⇔ $Dec_k (c_i)\oplus c_{i−1} = m_i$
