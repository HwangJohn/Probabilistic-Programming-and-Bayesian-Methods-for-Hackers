# 프로그래머를 위한 베이지안 with 파이썬

Created: Jul 1, 2020 7:09 AM

저자: 

캐머런은 캐나다 온타리오 주 궬프에서 성장하였으며 워털루대학교와 모스크바독립대학에서 수학하였다. 유전자와 질병의 진화역학부터 금융상품 가격에 대한 확률적 모델링까지 여러 응용수학 분야를 거쳐 왔다. 현재는 온타리오 주 오타와에 살면서 온라인 상거래 선두 업체인 쇼피파이(Shopify)에서 일하고 있다.

[https://camdavidsonpilon.github.io/Probabilistic-Programming-and-Bayesian-Methods-for-Hackers/](https://camdavidsonpilon.github.io/Probabilistic-Programming-and-Bayesian-Methods-for-Hackers/)

- 원저자 github: [https://github.com/CamDavidsonPilon/Probabilistic-Programming-and-Bayesian-Methods-for-Hackers](https://github.com/CamDavidsonPilon/Probabilistic-Programming-and-Bayesian-Methods-for-Hackers) (PyMC2/3, TFP)
- 한글 번역 github: [https://github.com/nu-ree/006775-Bayesian-Methods-for-Hackers](https://github.com/nu-ree/006775-Bayesian-Methods-for-Hackers) (PyMC2)

그외 tools

- (TF) tfp.edward2: [https://github.com/tensorflow/probability/blob/master/tensorflow_probability/python/experimental/edward2/README.md](https://github.com/tensorflow/probability/blob/master/tensorflow_probability/python/experimental/edward2/README.md)
- (Torch) Pyro:
[https://eng.uber.com/modeling-censored-time-to-event-data-using-pyro/](https://eng.uber.com/modeling-censored-time-to-event-data-using-pyro/)
    - (Etcs) PyStan, emcee, Numpyro, Brancher, PyProb: [https://colcarroll.github.io/ppl-api/](https://colcarroll.github.io/ppl-api/)

Using Python and PyMC

![http://i.imgur.com/6DKYbPb.png?1](http://i.imgur.com/6DKYbPb.png?1)

### Probabilistic Programming & Bayesian Methods for Hackers

### *Using Python and PyMC*

The Bayesian method is the natural approach to inference, yet it is
hidden from readers behind chapters of slow, mathematical analysis. The
typical text on Bayesian inference involves two to three chapters on
probability theory, then enters what Bayesian inference is.
Unfortunately, due to mathematical intractability of most Bayesian
models, the reader is only shown simple, artificial examples. This can
leave the user with a *so-what* feeling about Bayesian inference. In fact, this was the author's own prior opinion.

베이지안 방법은 자연스럽게 추론에 접근하지만 느리고 수학적 분석의 장 뒤에있는 독자에게는 숨겨져 있습니다. 베이지안 추론에
대한 전형적인 텍스트는 확률 이론에 대한 2 ~ 3 개의 장으로 구성되어 있으며 베이지안 추론이 무엇인지를 입력합니다. 불행히도, 대부분의 베이지안 모델의 수학적 난 도성으로 인해 독자에게는 단순한 인공적인 예만 표시됩니다. 이것은 사용자에게 베이지안 추론에 대한 느낌을 남길 수 있습니다. 실제로 이것은 저자 자신의 사전 의견이었습니다.

After some recent success of Bayesian methods in machine-learning
competitions, I decided to investigate the subject again. Even with my
mathematical background, it took me three straight-days of reading
examples and trying to put the pieces together to understand the
methods. There was simply not enough literature bridging theory to
practice. The problem with my misunderstanding was the disconnect
between Bayesian mathematics and probabilistic programming. That being
said, I suffered then so the reader would not have to now. This book
attempts to bridge the gap.

최근 머신 러닝 경쟁에서 베이지안 방법이 성공한 후 다시 주제를 조사하기로 결정했습니다. 나의 수학적 배경에도 불구하고, 3 일 동안 예제를 읽고 그 방법들을 이해하기 위해 조각들을 모으려고 노력했습니다. 실천하기위한 이론을 제시하는 문헌이 충분하지
않았다. 내 오해의 문제는 베이지안 수학과 확률 적 프로그래밍 사이의 분리입니다. 그렇기 때문에 나는 그때 고통을 겪었으므로
독자는 지금 할 필요가 없습니다. 이 책은 격차를 해소하려고합니다.

If Bayesian inference is the destination, then mathematical analysis
is a particular path towards it. On the other hand, computing power is
cheap enough that we can afford to take an alternate route via
probabilistic programming. The latter path is much more useful, as it
denies the necessity of mathematical intervention at each step, that is, we remove often-intractable mathematical analysis as a prerequisite to
Bayesian inference. Simply put, this latter computational path proceeds
via small intermediate jumps from beginning to end, where as the first
path proceeds by enormous leaps, often landing far away from our target. Furthermore, without a strong mathematical background, the analysis
required by the first path cannot even take place.

베이지안 추론이 목적지라면, 수학적 분석은 그쪽으로 향하는 특별한 길입니다. 반면에 컴퓨팅 성능은 확률이 낮은 프로그래밍을
통해 대체 경로를 취할 수있을 정도로 저렴합니다. 후자의 경로는 각 단계에서 수학적 개입의 필요성을 부정하기 때문에 훨씬
유용합니다. 즉, 베이지안 추론의 전제 조건으로 종종 다루기 어려운 수학적 분석을 제거합니다. 간단히 말해서, 후자의 계산 경로는 처음부터 끝까지 작은 중간 점프를 통해 진행되며, 첫 번째 경로는 종종 우리의 목표에서 멀리 떨어진 거대한 도약으로 진행됩니다. 또한, 수학적 배경이 강하지 않으면 첫 번째 경로에 필요한 분석도 수행 할 수 없습니다.

*Bayesian Methods for Hackers* is designed as a introduction
to Bayesian inference from a computational/understanding-first, and
mathematics-second, point of view. Of course as an introductory book, we can only leave it at that: an introductory book. For the mathematically trained, they may cure the curiosity this text generates with other
texts designed with mathematical analysis in mind. For the enthusiast
with less mathematical-background, or one who is not interested in the
mathematics but simply the practice of Bayesian methods, this text
should be sufficient and entertaining.

해커를위한 베이지안 방법 (Bayesian Methods for Hackers)은 계산 / 이해-첫 번째, 수학-두 번째
관점에서 베이지안 추론에 대한 소개로 설계되었습니다. 물론 입문 서적으로는 서적으로는 입문 서적 정도 만 남길 수 있습니다. 수학적으로 훈련 된 사람들은 이 텍스트가 수학 분석을 염두에 두고 고안된 다른 텍스트로 생성 된 호기심을 치료할 수
있습니다. 수학적 배경이 적은 애호가 또는 수학에 관심이 없지만 단순히 베이지안 방법을 연습하려는 애호가에게는 이 텍스트가
충분하고 재미 있어야합니다.

The choice of PyMC as the probabilistic programming language is
two-fold. As of this writing, there is currently no central resource for examples and explanations in the PyMC universe. The official
documentation assumes prior knowledge of Bayesian inference and
probabilistic programming. We hope this book encourages users at every
level to look at PyMC. Secondly, with recent core developments and
popularity of the scientific stack in Python, PyMC is likely to become a core component soon enough.

확률 적 프로그래밍 언어로 PyMC를 선택하는 것은 두 가지입니다. 이 글을 쓰는 시점에서 현재 PyMC 유니버스에는 예제와 설명을위한 핵심 리소스가 없습니다. 공식 문서는 베이지안 추론 및 확률 적 프로그래밍에 대한 사전 지식을 전제로합니다. 이 책이 모든 수준의 사용자가 PyMC를 보도록 독려하기를 바랍니다. 둘째, 최근 핵심 개발 및 Python의 과학 스택 인기로 인해
PyMC는 곧 핵심 구성 요소가 될 가능성이 높습니다.

PyMC does have dependencies to run, namely NumPy and (optionally)
SciPy. To not limit the user, the examples in this book will rely only
on PyMC, NumPy, SciPy and Matplotlib.

PyMC에는 NumPy 및 (선택적으로) SciPy와 같은 종속성이 있습니다. 사용자를 제한하지 않기 위해이 책의 예제는 PyMC, NumPy, SciPy 및 Matplotlib에만 의존합니다.