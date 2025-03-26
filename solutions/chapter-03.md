# Chapter 03

> I used to solve falstad for solve some of the exercises. Those shared links created with [Falstad](falstad.com). This site has an online circuit simulator and I use it for solving exercises and test the correctness of my solutions. If you came across this kind of problem, I highly recommend due to very easy use and share features of site.

1. Solution:
	1. n-type
		1. closed
		2. opened
	1. p-type
		1. opened
		2. closed
---
2. Solution:
	1. top = P-type
	2. bottom = N-type
---
3. Every input can be 0 or 1. So there are total of 4 pair of possibility. And those pairs can produce 2 different outcomes (0 or 1). So 2^4 = 16 possible functions are possible.
---
4. Solution:
	1. A = 0, B = 0, C = 1
	2. A = 1, B = 0, C = 0
	3. A = 0, B = 1, C = 0
	4. A = 1, B = 1, C = 0
---
5. Solution:
	1. A = 0, B = 0, C = 0, OUT = 1
	2. A = 1, B = 0, C = 0, OUT = 1
	3. A = 0, B = 1, C = 0, OUT = 1
	4. A = 0, B = 0, C = 1, OUT = 0
	5. A = 1, B = 1, C = 0, OUT = 0
	6. A = 1, B = 0, C = 1, OUT = 0
	7. A = 0, B = 1, C = 1, OUT = 0
	8. A = 1, B = 1, C = 1, OUT = 0
---
6. Solution:
	1. A B | C D Z
	2. 0 0   1 1 0
	3. 0 1   1 0 0
	4. 1 0   0 1 0
	5. 1 1   0 0 1
    Z in terms of A and B is output of logical function AND
---
7. There is ambiguity at output when A = 1 and B = 1. Output voltage is threshold voltage, so it's keep switching.
---
8. Solution:
![Solution](_attachments/Pasted%20image%2020241106101858.png)
---
9. When A supplied with 0, OUT will be 0. Otherwise OUT will be 1.
	1. [falstad link | Live Circuit](https://www.falstad.com/circuit/circuitjs.html?ctz=CQAgjCAMB0l3BWcMBMcUHYMGZIA4UA2ATmIxAUgoqoQFMBaMMAKAHcQAWTvL4wiil6d+UdoOGiEQkNjycQKcZzACRa1SDx4qkZZu1UwkFAsNiOx01p3JrhBAL0AzCbPkhC1uQoTZw0EgwJuJeCtiEvGGK2hae1kK8YGhUiXHJcDFJKbKRYq7GGCjuChlUPhT+YIFQsEqWOZyZZRTciiwAsuA5CG1g2BgCvQqpgaHWTVTRw3HSkkMyhE3trnOey9FLtMXVQXXjvm2b1noc0214Um1KAObxCg4C0UW67RyXQxeiFada3x6FYoVJQFEwPRzdTKPQQBPYhBqZGYtLayFh3ZFFSFUHBOOLceZcTTqMQAGUJalEmGKxNezgAhgAbADOdGov1wCjS0TSvxaaTAnASsT0ACVwILObEwH4BDyoFxaPLdGMgA)
---
10. A = 0, B = 0, C = 1, D = 1, E = 1, F = 0
---
11. When A supplied with 0, Out will be 1. Otherwise OUT will be 0.
---
12. Solution:
![Solution](_attachments/Pasted%20image%2020241106131024.png)
---
13. It depends on what IR value is. If it is 0 then OUT is 0, otherwise it is 1.
---
14. 0, 1, 1, 0, 1, 0, 0, 1
---
15. 0, 0, 0, 1. AND
---
16. 1, 0, 0, 0
---
17. Solution:
	1. AND [falstad link | Live Circuit](https://www.falstad.com/circuit/circuitjs.html?ctz=CQAgjCAMB0l3BWcMBMcUHYMGZIA4UA2ATmIxAUgoqoQFMBaMMAKAHcLCrcAWTqnjzwgU7fiEHDCPAUKhihVMFwl5aKyArXjp6qpo4Y0FQSCMDp8jjO4oJcEITzCD9qk6kzHzq2eMIMQj93I3kAc2CzSD5zEDV9ETFY3kcvFNddEBTMsGI7VwQVFMKlDTEcvNSlQPkAJSrwU0zLBK8kBJgELVKBbWVfRXAg2P7RQ2N+kbL6+Ma+WZaoe2oO6C6OWbAa2fSk4xSd6IGHbDsbEAZT46pLu2cbq7G47VvnnrqQYlMwUy++RYEtCW+jWYj+4Bq4N2HChR0OfFcySckWhKORsR4V00ABlxJIssj8UoQAAzACGABsAM50FYsXGDEoE4RM4nk6m09r0hoeZneFzgUmUml08bcZFgODCbDI1yS-B8+XCFCFXxKxVS1T6Fgk5AKlVBSU+A0UbDgNZQWCiXXqwZG4SMuxgC0wSCier2kReT1bIKtIGrdbIY2hT0ylxiMMS-AOlosCKenjEQ0xkwIxIAWWD0olKCu4aWKFBusy+IxcgQTpdVp1DSZsSZlfN7RrJa8vNivKbzpbbtrTOU7m9KgQZp7lr7uqmVE2I7H1cnbyGVHBg9NzYnoiAA)
		1. Solution:
![Solution](_attachments/Pasted%20image%2020241106134646.png)
	2. OR [falstad link | Live Circuit](https://www.falstad.com/circuit/circuitjs.html?ctz=CQAgDOB0YzCsICMZICYaoOyYMxgByoBsAnCZiHBAlZQKYC0iiAUAGYgAsiRIqcvIgL7C4OJJAQowqdlyKcQOfIqG9lisRKnRZHTgsqJUINUZNbEkqDJYB3LjyUr5ijeHuPecY6-MeAJVNhVE4IMxJeCAgwynB4lDhPMywTMxwifA8HM05I4N4w6OTRVCyzAWKc0SJw0RITMBLvBpB8HAtWpuqWtOEzboLKVrze7K58uBH8gc92zpN5oaaOTDg0zEWO003KEysdWw4pjb7BXfXtGz0ubaJd0Z2LfetpWQdUkV5P+8bPH4ed12g243xCu34UU8oOcbku7kGOHhLiRJkwmXGqJA6KylWxGMGeJxwzRBM8J3xuNav3Ga1O2MuKiyIKcPhMMKZ4w5nCydLaPI8AHM2nd8FklrgonwWMKzJlysJJfFZMLHvKJrwlRB3kM8SRfHimgAZPgQkKhL4JEBsACGABsAM50OLGpTIxSoC0I+K2x3OqQsE0wtl8C0h6LW+1Ol2efUWWogON+QZJvW+WYcJMGRTkQqGSyvXRyJMRdG6l6HHW5ygJ6sKKqJst6ss84pBaucAXVrER2JSBKSFgAWUb3gTyAuCe1g+Fdd21b52pYQA)
		1. Solution:
![Solution](_attachments/Pasted%20image%2020241106133258.png)
	3. AND
		1. A = 1, B = 0, C = 0, OUT = 0
		2. A = 0, B = 0, C = 0, OUT = 0
		3. A = 1, B = 1, C = 1, OUT = 1
	4. OR
		1. A = 1, B = 0, C = 0, OUT = 1
		2. A = 0, B = 0, C = 0, OUT = 0
		3. A = 1, B = 1, C = 1, OUT = 1
---
18. [falstad link | Live Circuit](https://www.falstad.com/circuit/circuitjs.html?ctz=CQAgjCAMB0l3BWcMBMcUHYMGZIA4UA2ATmIxAUgoqoQFMBaMMAKDEpEJQBYQ08QeQr35QQ2agjYcuvbIQFC5CsRNrSqsiikXDtAqmoobOPTnl28FB8WKntNZvNhSC9z14bsmtpV0pA-VW8HU15mFQCImyMpAEkKbnDiVy0wFLEYJHjEkXwwvnyqLOMEhCS+My0UM2LobJYyiuwEVLMWzyh60tzxFS15GxKc8t4EMDaxiczukYrRgoW6hqarCwLrGZXejEgrM13eZZ6FvDBCArOL47neIN8Mm8be5jx98LA3reNQtOxpqL-TqxFgAd16NSmrkhUDBEPy3DwVFEkDhSQE6VcC0xsPBCw6IHR4lauN6g0JSL6BjhAy+41c2C+qLx82mRPppK0rQEiNoOlJC0F0yWNKqGFcRMI4oFFU2vPM1JZvEOFGmKuZvSuhMRgnOnKcLgpVA8+t4bwEHPNpsCGAuRLI1zhCyC8qCGrScAt0zAnutzBJRP9nlFHxU8uiMo+dO9nyOIfAKGIdp1EyTpPDQIKYEz7rM2f5HPzitV0LMHMZcbx0wrJd6Go5Qtc6qdAJ1HObVf8be9vvrMejrh9RRbg5cXsHsfTlOzbOn52L4fnRsCjzRlJdlJNGvlJvlm23lLllO5U75PMp5IPhjDlJRaJTGSJBO3OoJ7OmL-H2oEUuD4Ml0pElqn66smAgOumOoQYG7B-t+CZpjBJKogAMvBOIwjixQgAAZgAhgANgAznQ1CocuoguMiRRiPhxGkUg5EcjC3BwJURy0YRJFkSwAAegh4OQaAXMQrGFMQhJ8EcAA0kCyXxAk-oJgTcBAJBUCI4SyfJ-EWBACD-IE2BjMZkm1NJYA6QJhgYBAxDYBI2AYLwmlQNprC6QQ4BgLZRlIMwzlmVplmorpGASaQ5D2YO8BBeA7kKRYFzOOB2ASW8ECuXJlkedZ4D-CJDn5ekcU5RZLBAA)
	1. Solution:
![Solution](_attachments/Pasted%20image%2020241106140912.png)
---
19. Output of decoder can be calculated with number base as a base and input count as a exponent. Which in this case 2^5 = 32.
---
20. Just one output line. The number of select lines is the base-2 logarithm of the number of input lines. Which in this case 4.
---
21. Solution:
	1. Solution:
![Solution](_attachments/Pasted%20image%2020241106153936.png)
	2. Addition overflowed due to required one more bit.
---
22. [falstad link | Live Circuit](https://www.falstad.com/circuit/circuitjs.html?ctz=CQAgjCAMB0l3BWcMBMcUHYMGZIA4UA2ATmIxAUgoqoQFMBaMMAKDEpEJQBYQ08QeQr35QQ2agjYcuvbIQFC5CsRNrSqsiikXDtAqmoobOPTnl28FB8WKkBJCt15hiKUy7diYSB05H4HnyBVD7GjgjOfGZaKGah0L4sEVHYCO5aae4JSSnKApkqOeH+FGAZZgjl3oklkbz1QY3Ffo3WQe0tyaUYkFZmvbxdAO6lcQ3V41Aso42i3HhUopAzIM4Cru6Nm9OzqelrC+IHK3v5a4viRauZeBPu2He7pVXu62XZN5U6F7Q-py8oq9SgCtIQMG8juDPmdzAIFpoLM9GoMPiBUQDgVNgY8hqscU9gc18dVGsCMasEXDfvpnlT0vDLvIDJSmSoqctKUcdu8snSjnz3sCAULqu9odMADKHDZeXCebJiABmAEMADYAZzo1BW0o5gT5y2V6q1OpY0qxZm4cGiQ2Nmu1SBW7HceGIhDW2HcYEgVq9YgaxlGbo91qoIeCLOD7sjgj0nODemZcd43DAHoBSjW6cEMbTGdWEfeWfemb0xb0DOeRb0Ec6hZj7Sz9YAssg-d7IAhQ-6lokWEA)
	1. Solution:
![Solution](_attachments/Pasted%20image%2020241106154707.png)
---
23.
	1. | A | B | C | D | Z |
	     | 1 | 1 | 0 | 0 | 1 |
	     | 0 | 1 | 0 | 1 | 1 |
	     | 0 | 0 | 1 | 1 | 1 |
	     | 0 | 0 | 1 | 1 | 1 |
	     | 0 | 1 | 1 | 1 | 1 |
	     | 1 | 0 | 1 | 1 | 1 |
	     | 1 | 1 | 0 | 1 | 1 |
	     | 1 | 1 | 1 | 0 | 1 |
	2. [falstad link | Live Circuit](https://www.falstad.com/circuit/circuitjs.html?ctz=CQAgjCAMB0l3BWcMBMcUHYMGZIA4UA2ATmIxAUgoqoQFMBaMMAKDEpEJQBYQUeQeQr368qYimw5de2QnkHCQcheKiT2VGRTApFvBLvUSEUrQMIJC+zlePrTmzgLxhrQ3q+traZ572JCKg8QQKofSQBJCm5eMGI9bXi9cOgkU2iEWOUERIFsXPUYdJZM7NyFbQqitKiY3nlKizxVKFqM+pAMPAaBboliuqzPOH9BUdSSsoCUJpnWwdMAd07kkG5A8ASoFhXtFDthvjtIXbGeWlm+bnCz-fwdPTRVO-y5dc3sd9O9gRvabL-HYrI4FPSGPRg4FjbA9ChXWFiV68bh4cSbVG3X4ozYQj7eM5HarEq4-MZE8rZMnabQbazaakWG6PTjMxkNDDgq6ETnQ7Q9BRHAV8lzYLkKPBi6FC0Z4tFYzr9fFdOFko4JBR00KkwnZYjlIz6pHY0LbdXbNXZA7WI5Ay0o2WU42dRqdI72zgtTrCj2kcHZH2Eq5kG1XSUpIMSqXVHkRkHc3kkl7xwVXaqI6UI+TwhQXaVGZ4sqFqoxQvFakt6LV44QKuWyoy1-N6I0s+XQrUa5VKsla2kYtEdgfo6zFs5aqET77jzZrKcEgAynWt60HK-CIAAZgBDAA2AGc6NRTkvqnnuEo8xudwej0gTyzC7Fcw8qBAb4fjywl1q51K1m+W57p+95SC2GA2tszDZggFpdNQyw2KIoQQZ0ZIhCoKE2kEOwALLgG4gpQSg0ZwSgaRnCEeIhhQqHoUoljWDRsFxjYXhYZwr4ztYYD4JqmxdpWBGQAYhpUpGBHvNUNEeswhTmqxRzMCJLLKc6Sl8cqvFeqcThJLowRKMwaD2CUKxakqfYCLJvG9HEtk7NMkn0gIzDfG0Zk5s5qxgNOKwhGEHEMpRRkGUFbISRm6bZr62TaK2pyZMGqHxXRHmSCC2TaXMyA6aUPmFPphSTJIQA)
		1. Solution:
![Solution](_attachments/Pasted%20image%2020241106161724.png)
---
24. [falstad link | Live Circuit](https://www.falstad.com/circuit/circuitjs.html?ctz=CQAgjCAMB0l3BWcMBMcUHYMGZIA4UA2ATmIxAUgoqoQFMBaMMAKABkQUUAWEQ3rr254oogGYBDADYBnOtUgsAkpx58BasISo7oSBCzCVOGFOG0mzKPCKpn9LAO6reWuwkLmdTzja8hsNH9FDkCqNwCg4VEISVl5JEUAWUtfEUwzMNEUPRYAD3AECDAgsAxilGw+Tl4JaHyQbkhirUaUFuJqtQAjeoL28nbObCq1AV4AQQbsZk4IQMGhGpAAIQaPQYgEPFGltTWC7hw5xrxOseWplIRrNIpbrLtc5wRuVwsEDE8IxWdhcI+JWChmMNxEETBdzs1AMHH+6lOVGi4RAcTkCmUFC+CM+3wsugcHFxOOxyPE0nRiR88Ii8P4UBBVGwN0a9O4bPp0IcRiZLMIY3p-N40NomOsIjeImZZklohgDhU4vUvLM-B0UD0FB80r4+Du2ls2pZ8KV8N+rKE9NeluFIPsbwoFkIHkd6vsWpSzs8HiohFMruyzwoDvZvGtwdtf0FanDQoZLwdcfDxPNKBdBv1etT6b1ac8suz+eipuRPlNeDsfjVDI45bserN4FRFISNc4LtlZSLtnJ8QxBWwhAg3CB2AwnRHSE8agAxvUgA)
	1. Solution:
![Solution](_attachments/Pasted%20image%2020241106163512.png)
	2. If we use same copy of *c* part, the carry will be lost.
---
25. Solution;
	1. The first figure is a *mux*, used to select one of the inputs. The selected output will not be stored.
	2. The second figure is an *R-S Latch*, used to store the binary value inside. The output will be stored.
---
26. [falstad link | Live Circuit](https://www.falstad.com/circuit/circuitjs.html?ctz=CQAgjCAMB0l3BWcMBMcUHYMGZIA4UA2ATmIxAUgoqoQFMBaMMAKABkRtC8QU8eUKACy9+UcCABmAQwA2AZzrVI7EELCFOaUT2zaqEGQqVIVYShTApOkEYXw2RVa7RbnrGbmr0hifby5q1AgsAO4gnrq2EV5CcFAsALK+-kI+xEIiaYEo0CHhXAJihZx4TmFqGlpU6prYZQkAkpWa2ZbWbVQwSPntavElcV0VgwNe9eXhtaVZVZ0szfY80xja0115FG4I1ghWLSBLB87BFdNt0wiZCQWxYzx7LmdCD-sljzcUfhT+q7T+KnCf0cMSikwiayqkWOFWBmR40Phn2BOwRaxeCXM-we-gQ31R4kCIWal2uBKuTigm16SI+5P2gMODlwImBLKaBz0tDe+ipPQWBz4r2sQvE3S2UyqopKorMFgJhDiX2siq6vFO4TxKqV0NVyK8esRis+7zeBuEJvNIgVFsZpNmmkICE0dqqTs0CudCSAA)
	1. Solution:
![Solution](_attachments/Pasted%20image%2020241106165501.png)
---
27. 14 bit address can store 2^14 byte. If the nibble takes half the space of the byte, this memory can store 2^14 * 2 = 2^15 nibbles.
---
28. [falstad link | Live Circuit](https://www.falstad.com/circuit/circuitjs.html?ctz=CQAgjCAMB0l3BWcMBMcUHYMGZIA4UA2ATmIxAUgoqoQFMBaMMAKDDwBYQPCvsEUFQlX6CqrAO7deIbJ25hCs+ZBZSefAcs1iWAGW2yt2QniNioIAGYBDADYBnOtVUGOiwybNyuVKrcdnJFcFJQQOPlMKCMt-eycXfUMEMEEvClTY63igqDVpLhS0+SK89RlwrncwmNV2KorMhGEMi0khES0MNG4OM1UpZtpM7qo+vxYAWRA8PDG+kGJMiP6QFGgENnlR3rMMeRXLdrwPQ9n5-vyBM0Pq3bKKFDNhG48Xh7v3u8OQ74X0n6WAIJYJJfaFGLgkCEFC+IE5RJAA)
	1. Solution:
	![Solution](_attachments/Pasted%20image%2020241106171556.png)
	2. Solution:
	| S0 | S1 | OUT |
	   | -  | -  | -  |
	   | 0  | 0  | LEFT TOP I0 |
	   | 1  | 0  | LEFT TOP OR BOTTOM I1 |
	   | 0  | 1  | LEFT BOTTOM I0 |
	   | 1  | 1  | LEFT BOTTOM I1 |
---
29. [falstad link | Live Circuit](https://www.falstad.com/circuit/circuitjs.html?ctz=CQAgjCAMB0l3BWcMBMcUHYMGZIA4UA2ATmIxAUgoqoQFMBaMMAKAHcQ8qAWbvT2in6R2AikLGEU3KCzAIIXEN2woQmNSrVU1SBHIRqlhbjoxqTVHVAqiNIS+vMUMhWfKrZsbhIR58KPxtdWw57LSddXlkw5wj7bDwZEVi1RJlfTyT3BGxAnjgHOMLrWlFefkz86pTq7jAfIKraqtagv2FRKo6ii3wY3uVCwmcFbQMqEd0JPFVxYXUbfQ4ph37VhGiRAFlOOcN+PBN54Oh9AElIlzcvH1cbGD1RW4po+03klgAZSV9wN0IfysIAAZgBDAA2AGc6NQRD8lAd-idgeDobCkPCxPU3A1lHjUZCYXCWEA)
	1. Solution:
	![Solution](_attachments/Pasted%20image%2020241116001424.png)
	2. Solution: 
	| A | B | C | Z |
	| - | - | - | - |
	| 0 | 0 | 0 | 0 |
	| 0 | 0 | 1 | 0 |
	| 0 | 1 | 0 | 0 |
	| 0 | 1 | 1 | 0 |
	| 1 | 0 | 0 | 0 |
	| 1 | 0 | 1 | 0 |
	| 1 | 1 | 0 | 0 |
	| 1 | 1 | 1 | 0 |
---
30. Solution:
	1. It is selector of a *mux*. If x = 0, operands of adding operation will be A + B; if x = 1, operands of adding operation will be A + C.
	2. Can't solve.
---
31. Solution:
	1. 2 propagation delay due to some inputs propogate through 2 gates.
	2. 3 propagation delay due to Ci propogate through 3 gates.
	3. 12 propagation delay due to Ci propogate through 12 gates.
	4. 96 propagation delay due to Ci propogate through 96 gates.
---
32. [falstad link | Live Circuit](https://www.falstad.com/circuit/circuitjs.html?ctz=CQAgjCAMB0l3BWcMBMcUHYMGZIA4UA2ATmIxAUgoqoQFMBaMMAKABkQUAWK7qsFHk49OUEADMAhgBsAznWqR2w3hhThBnNaKpS5CpEo58QuLhqFmdEmfMXKT2bIQunn1vXcMORzoQMtCIXVdWwMoHyoefk1ojzD7YxEubHUAkBT1EJt9RJUMwnN0rkL43O8ADxAMc25scAFhFyLzSAAaAB1ZSC62pSqarSRmLIwhFqhO7qnWAfNcchHTMCjwVpmp-ur57GIG9WwudQn2rrAZljnTDAgl7EGJ867T7svtjMh6pZ5mtfBNi5XFLDRopcZ-J6ySFbB6ERagjCrMBFDZnFhgBAHIKcPBCBCNQRCKguWjozGmbFcMAufHHaliEkUFgAWQoBNxFEIvA5WWgCBZbLpNK5GXpvP5AHc3M1Sk4XHKIlKFcrsQqlFKTCUdjLWiwle4tRTxqV1flMlpjqlFRaMlbMMcuES9TauI6jRk3abNXAceMfV6OXFCbaQs7g+a-CHrY53FY1c647HIOY4qarHFI6mw75sfb3V7tJG86kqAWDmh3SXo75k5Xa16RMXc9ojKZyY5yWAMIzQuVrdh2zngiI04OqAOsggSQn21P3Sg56PJ-LyZGl5XVdj15GJ6Y8Lqlav95Xj0ogA)
    ![Solution](_attachments/Pasted%20image%2020241116001406.png)
	1. yes, we can.
---
33. [falstad link | Live Circuit](https://www.falstad.com/circuit/circuitjs.html?ctz=CQAgjCAMB0l3BWcMBMcUHYMGZIA4UA2ATmIxAUgoqoQFMBaMMAKDEpDTxGzR8gAsPPlRRQKLAJLgBQ3EK78hVGEgQsA7jLmDtIAWEJQ2HRQN5L9F0ePVb5VsQ4Fxj93byoPshbpE2WPtzYCE6+bpYuXqH6rv7sTjHYeEIChHIp4mK0LACy+uk8maHBmaLQdgUZqYUCeCoBaan14MRidQ1aYG36Ld3tdRH9+oNmg-4AMpz4PD4gLdhzKiAAZgCGADYAznTU-l2y+obT3AZGk3pneghg2eLr27tI-kA)
	1. a.
		1. A = Z
	2. Circuit preserve previous valie.
	3. Yes, it is.
---
34. Solution:
	1. 11 = 3
	2. 11 = 3
	3. 3 (11) x 3 (11) = 9
	4. 4 bit requires for representing 9 in binary (1001).
	5. | A\[1] | A\[0] | B\[1] | B\[0] | Y |
	    |   0  |   0  |   0  |   0  | 0 |
	    |   1  |   0  |   0  |   0  | 0 |
	    |   0  |   1  |   0  |   0  | 0 |
	    |   0  |   0  |   1  |   0  | 0 |
	    |   0  |   0  |   0  |   1  | 0 |
	    |   1  |   1  |   0  |   0  | 0 |
	    |   0  |   1  |   1  |   0  | 2 |
	    |   0  |   0  |   1  |   1  | 0 |
	    |   1  |   0  |   1  |   0  | 4 |
	    |   0  |   1  |   0  |   1  | 1 |
	    |   1  |   0  |   0  |   1  | 2 |
	    |   1  |   1  |   1  |   0  | 6 |
	    |   0  |   1  |   1  |   1  | 3 |
	    |   1  |   1  |   0  |   1  | 3 |
	    |   1  |   0  |   1  |   1  | 6 |
	    |   1  |   1  |   1  |   1  | 9 |
	6. [falstad link | Live Circuit](https://www.falstad.com/circuit/circuitjs.html?ctz=CQAgjCAMB0l3BWcMBMcUHYMGZIA4UA2ATmIxAUgoqoQFMBaMMAKAA8QmQUAWPEHhBQIIPbmICCAbTABddpxTc8VHlRR5sA8SGmR5HBkrX81A5tt4gAQlP0Ku2DIXMgnxS2NtyWAWRCEGMaEYkGqIVDc0AgsYJRukGLCLmrqCC7q1DFxVLhi2HhiqW6FkUpIMQCS4upBCUl1VDAVLNW8uYT8eW6dkc0UsfE82EojtM5uaGVZLADuAnDc6QIjSxlzK0rJm-VQG8UFRauHe-PDo73nbtjr893tNY+QG93FD8XP82Aajw8Pz3FyhMeBFAsExJkWndEhQfg8ED9PrtCMsHij1m0zDxiC5Xji+tEBpiqJ0ujDSQSWjldiJjItadNaINcuS6sUwYyBmdjpdjqUkWBgfj3vikX86mAeA0lAK4WZvqZRRsFQJ8YKUkqvlLuBLtQj+AK9XLaIjlYQOvwHjcDWaLeBzQFlgKHejHq6xVjFuqFk1lcCvRMKQLA3hLWYg8ydghiECXNGZdxIjEzvTvlG00irgysxNM6tzaZ8419kW6STi-MEBMxhRgXxTrW4zHGwIVHsADLgY0BJJmKgQABmAEMADYAZzo1Gencl0p7OoTVGH48nSGn9rtEWtfRAy4nU5YM-9JKKi37u9H+7XLCAA)
	   ![Solution](_attachments/Pasted%20image%2020241116001323.png)
---
35. Old value can't be recovered when overwrite on it.
---
36. Solution:
	1. | A | B | G E L |
	   | - | - | ----- |
	   | 0 | 0 | 0 1 0 |
	   | 0 | 0 | 0 0 1 |
	   | 0 | 0 | 1 0 0 |
	   | 0 | 0 | 0 1 0 |
	2. [falstad link | Live Circuit](https://www.falstad.com/circuit/circuitjs.html?ctz=CQAgjCAMB0l3BWcMBMcUHYMGZIA4UA2ATmIxAUgoqoQFMBaMMAKABkRCMUKNDOUAFl78qVAGYBDADYBnOtUjtO3TvgHDC6sSClyFSJWEogc-BMR55BeCpaggetFgA9TeJAmwRr57MOEhEABRAEcAVxkWAElTbH4MSGE8OFMkhxhPFmMqFKpuKmIwHgKHHizYszj+POqM6CyAdxUeLVtEzW0WZq5yvk48WwR+pR7BkQH29NG0zqnhKpnCceGE+ImZjrV29baobtm6qsWD5fmj6eyEHiLWhH4wSFVCe7LqBAPb0zQQL9795rWIb2L4WJyfYqcQSFSFg-YAWWQz1ezB+L1Ejgayi22DRQVxOgkMnkiiuJWuIFwyRslOmjnep1UKHGGApzNsm3SBNMFO5Sg4-3ZGkc4yoED0JMMBxxPy2gjAokZPCF-2w1n2OR5PGhuRpOrezmacoVWpA8sVPVUaoWvPVSliQNpwi+VPqWWMN0h2Apj2hlIpVCcFAhPGw6xdl2aLuWv0h+pmX31jvjMWQfu9PGYXIDUAawbceG8jmGseVWjNjmEAHEAE50SQAFzoNaVlPV-xsYlbnfAvrNKQ1JizARNxVS5reTV72czfZTzWHZtx04CA6UiLHVAnxWXE8DWI3aEK-R3NxGmI+C77pFn6V9Xav6S+i+I5aMQ+vJ6Pv3P5WDRrvJIxT7e99gLIs8DAchiEgbAQAILdKxANg6FkeQW1iUDn2vSExDzS9S1+ctHVfB9CMsWwvlIgFCLwV9aMIYR309Fi0xhIMgw+B0aTwRiGKY3Mp3+YhBBtG5RJorYyASClpMHfJZOImlqMDBwCP+R1hIkzlkgHKSRmUDSaUIIJHR0CUDEk9JBgUqw11bR1WSsGlmNNXjqVsdzJ2DDgths4V-LFXRiUsnSfwSQC-SUIA)
	   ![Solution](_attachments/Pasted%20image%2020241117112619.png)
	3. [falstad link | Live Circuit](https://www.falstad.com/circuit/circuitjs.html?ctz=CQAgjCAMB0l3BWcMBMcUHYMGZIA4UA2ATmIxAUgoqoQFMBaMMAKDEpB0JFwBYQ8vPD0j8qKKBRYAPTniQoExAb25EJ-FPwCiARwCuAQwA2LAJKds3XmG544IG9yowkCNh3tVe2CcTAavpISbuaW1kICDryRLtChAO4ghBgSvlQYojxoUCxJKRIoeMKExSBFwpB5yWUVNcJOuUmZ-OmcWTGV1aXCdVzlZVXNWW39bUPt-J3hjrHdZY39jVXsfgE8pcipG5Xl1O5J-oFraYJNKsJ8IEciYtU32Agnt+c3zM+Ed0mCJfw3n691mBiM8wDFcqtrkCilsJAFdiEpPkymAMNx+qjnNUWuV8DM0F1hvx7DMSRMeo5hEtCZMorSCecKZEKZjGdtmQsaQU6TiyWF+gyvLjdq4pOwqELgaCQcF9vyrOA0VEqKy4qFZBh5LiVGpsI5yjoDCYPBkFQCfskxHtaCwADIUGGRVRTEUgABmJgAznRqFV7U9egsAXUXO6vT6kH7LVQ2ggleNJB7jN7fXbo3S43ZQ1QkynIzJHMQ9UQaMoUMpNPwAIIFwiQciYZIoPW4fVaEAAITTAc4m2dvdduYjuX9MJ7-Z7oaHqftn1odYoSoQC6n4Zn6aFmeVkhza-z4pmCHBFqPVokNo1WsoEtUND1lZAeiMpgs-UIy+37+cUHiYs8Dm5f5tnEOVXzNMohQpNUkWSbZlwyLJ4LZEIYQpSd5mEHsKS-c4cSQnEoIwh0qQVdCiQoBd+iQiYCLKN9BiInC3w-FYnihCQ62EMB6w4vEQMSdjYI+dsJhPcEblPQEQhlCTwQmG48CCG5NS+C45D+dYVKkwSFIBVjngtbjtgtfiYIpPBiHRBULKxciQRI7h7NwrIhX6IVyTozZ+jRGleQcHEnI8qlNnMyzkIHeoIvJYz-JchwqjAxyYSFQKf1CA8UvWG4blM9xEoEMKhRsndf3cS8kBwZRBHRXgNANR8jVMA9vLOC0tJAm0knHEp2RpHs6m5ENqh7LC4JhCYex8oSou6XgJQAmKXFm+cqG5ajluyVbtnGDaSW5PkDwCaIwrAXwGjC7w5SSIy4RhI7vD06obp2cA0G8Plrp45I8Xuih1gmX6e2ekyWAAWXAM7C24U6lV4C7yniFggA)
	   ![Solution](_attachments/Pasted%20image%2020241120102417.png)
---
37. Needs to three bits to access a location in memory which means 2^3 = 8 unique location can be addressed. So 8 byte * 8 possible unique address = 64 byte total size of memory.
---
38. Memory addressability defines smallest unit of memory(data) that can be accessed. Memory address is a unique identifier for a specific location in the computer's memory.
---
39. Solution:
	1. In order to obtain the fourth memory location the value on the address lines A[1:0] should be 1,1 respectively. WE is 0.
	2. We should increase more than 2^5 = 32, so we need one more, 6 address lines are required. Addressability of the memory won't be changed.
	3. We need 4 more address from 64-60.
---
40. Solution:
	1. The number of addressable memory locations is 4.
	2. 4 bits for addressability.
	3. Last one, 0001.
---
41. 2^22 * 3 = 12582912
---
42. There is no effect of current output. Inputs just cycle between them, one and another.
---
43. If one incorrect operation performed after one correct operation, this is can be a state to resetting current state to "no relevant operations have been performed" state.
---
44. Texas = 30 | Oklahoma = 28 => Texas = 30 | Oklahoma = 30
---
45. Solution:
	1. It can be. If there will be free throw happens two times in a row there will be a progression like this.
		1. Texas = 30 | Oklahoma = 28 => Texas = 30 | Oklahoma = 29 => Texas = 30 | Oklahoma = 30
---
46. Not solved. Because drawing take too much and will helped too little.
---
47.  Solution:
![Solution](_attachments/Pasted%20image%2020241120155022.png)
---
48. Because Y is the input of W and it stores state information of 1 state and 2 state.
---
49. Solution:
	1. | S1 | S0 | X | D1 | D0 | Z |
	   | 0  | 0  | 0 | 0  | 0  | 0 |
	   | 0  | 0  | 1 | 0  | 0  | 0 |
	   | 0  | 1  | 0 | 0  | 0  | 1 |
	   | 0  | 1  | 1 | 1  | 0  | 1 |
	   | 1  | 0  | 0 | 1  | 1  | 1 |
	   | 1  | 0  | 1 | 1  | 1  | 1 |
	   | 1  | 1  | 0 | 1  | 0  | 1 |
	   | 1  | 1  | 1 | 1  | 0  | 1 |
	2. Solution:
![Solution](_attachments/Pasted%20image%2020241120161816.png)
---
50. [falstad link | Live Circuit](https://www.falstad.com/circuit/circuitjs.html?ctz=CQAgjCAMB0l3BWcMBMcUHYMGZIA4UA2ATmIxAUgoqoQFMBaMMAKDAQlwBYQvCeu2FL35Rw1BCwAyIFHjwieaBXx5UqAMwCGAGwDOdapBYBZXkMW88VVWJTRJADxDZcvFMRfXzwpTwByAPIAKmwcLpA8CBiEvGCx0bFUwkiS7BBc8RQxFGApOVQQtKa5+QlcUQWyDizOrtgU2Jx4DQjYArI8AIL+ACJhnJEghBi+WSPChRIDETwYQ5mx82riqTOLw-IUcpsKyWKSZgg7hFsIhFSne9WSMpi+xLHKvI9imroGRiwA7rOW3BQLlAfn8EMRhPcKODgb8ActZKMQPDjLChucqACJjCEQ8noiwZMQZCCTikUMUbItrYAbZjHVsJ5+JwMEh+B0UDxAgAlFhAA)
    ![Solution](_attachments/Pasted%20image%2020241120162832.png)
---
51. Flip-flop
---
52. Just for the A = 1, B = 0 values. [falstad Link | Live Circuit](https://www.falstad.com/circuit/circuitjs.html?ctz=CQAgjCAMB0l3BWcMBMcUHYMGZIA4UA2ATmIxAUgoqoQFMBaMMAKDAQgBZjCRvfCKTnx5QQKMQhYB3EQM5V+FDL0gy5FMBM6FhHCWtk69WvrpCF8UdcYtXBwy3muyHd528IJVN0QhUWQso+rkH+AkFKagAyGpx4inB8CWIQAGYAhgA2AM501DEahBjaScUGYpm5+UiGgcJK5RpqALIWJRoliqJUKNBS7NhF3vUWI73UUkA)
---
53. Solution:
	1. 3 bit decrementor.
    2. Solution:
![Solution](_attachments/Pasted%20image%2020241120172251.png)
	[falstad link | Live Circuit](https://www.falstad.com/circuit/circuitjs.html?ctz=CQAgjCAMB0l3BWcMBMcUHYMGZIA4UA2ATmIxAUgpABZsKBTAWjDACgwEk09xCrMKPlSoI2AGWEhB4MEJlCqAMwCGAGwDODapDYB3KTLD9wxRfqlgz0-KfMBJaXl6t5KGrMVRoSMZyTYhC4mdELGIhQcXBQowaLW4VCRALIg2GjSGELpVNiB0tI+bKk0xISZQqXleeXyRamECLVZII3V+XViBrgeiTlSut0ZfcNyUBb9rk4uY4PS7p42M+YGPItriXOT1v0yW8Mm2ytpwztBduOONDTLaedTIj6Rjvy3CLGLj74T92OBceMDO83h9NhYaIReiEygNwTDElULnNEVYhMCkXDygj4bNMYtrrdkfDrIi9hZCAtEm1YQZqVSmp9yQypq9GbTmSZqWSAB5pSD0bB4AV5NJ4coeBYAEV0vJuEEFEAQrFFHglHkl7F5hHy2AwxFahGqBFo0nVKDYQA)
	Scheme of each cycle:
![Solution](https://github.com/EdmanCoding/solutions-of-introduction-to-computing-systems/blob/patch-10/solutions/_attachments/3.53%20MS%20set.png)
---
54. Solution:
![Solution](_attachments/Pasted%20image%2020241120205404.png)
---
55. Solution:
	1. Solution:
![Solution](_attachments/Pasted%20image%2020241120204630.png)
	2. [falstad link | Live Circuit](https://www.falstad.com/circuit/circuitjs.html?ctz=CQAgjCAMB0l3BWcMBMcUHYMGZIA4UA2ATmIxAUgoqoQFMBaMMAKABlwNCQUAWKsCjw9+PKCABmAQwA2AZzrVI7Tt0wpwQnhg0aq0+YqTKOYLiFy9Nwy2P2yFSlWe7Zs3QTfd3JDo1Gdzd2FPC0JhPV9DJ1NzfgEteJ8DR2NA7l5sDVDM3XEU-xNVEF5CKxyy5L8nAA8QDCs+bHBBEQzwK0gAGgAdOUg+ruU6hu0kZl0MYXLO3v651hGrXHIJizAqGagFueH65exiFo1sXg0t7r6wBZYliwwINexRreu+y-7b-ZLIZrX+dpgcq7G53TLjVqZaYdcA7d5fF6EVaQjCbGFvOQY1hgBAncIWSBWXjEVyE8SdCgsHF46ZgDIkkp08niBAsADuxXUFjQ2j07O5VC5wV5AQAsiUGbYELxlmTBdBWRyXATGngbHL+UIImqBTwdcoOVlBTrhVqAoaycLbEbzSrdVaeQbiqVljyXbabe6bW5uE7vd4rd4nWaQyaNRyzbZI3hOpqTTGwjYE07lT6RWngzoLN4uUlM+c4ImflRgwhXPjrfiU0F8Sgy0XS+WIvXcra6xkskXW9WMoW+JtC8HREl+yVeMIh5tx13p8pxcSMkzpUSmfLWUA)
	   ![Solution](_attachments/Pasted%20image%2020241120205334.png)
---
56. Solution:
	1. Solution:
![Solution](_attachments/Pasted%20image%2020241120210044.png)
	2. State machine has 5 states, so with using 3 bits we can represent all of them. Need only three variables.
---
57. Solution:
![Solution](_attachments/Pasted%20image%2020241120211432.png)
---
58. Solution:
![Solution](_attachments/Pasted%20image%2020241120213447.png)
---
59. Solution:
![Solution](_attachments/Pasted%20image%2020241120214409.png)
---
60. Solution:
	1. Solution:
![Solution](_attachments/Pasted%20image%2020241120214924.png)
	2. It will be 011. Because clearly it's looping.
---
61. Solution:
	1. Solution:
![Solution](_attachments/Pasted%20image%2020241120225041.png)
	2. Solution:
![Solution](_attachments/Pasted%20image%2020241120230432.png)
---
62. *This exercise requires a lot of energy, but gives very little. That's why I didn't try it.*
