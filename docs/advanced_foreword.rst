.. _advanced_foreword:

경험있는 프로그래머를 위한 머릿글
====================================

Flask에서 쓰레드 로컬
----------------------

Flask에 적용된 설계 원칙 중 하나는 단순한 업무는 단순해야한다는 것이다. 그런 종류의 업무들은 많은 코드를 요구하지 않아야 하지만, 여러분을 제약해서도 안된다. 그런 이유로 Flask는 몇몇 사람들을 놀라게 하거나, 정통적인 방식이 아니라고 생각할 수도 있는 몇개의 설계 원칙을 갖고 있다. 예를 들면, Flask는 내부적으로 쓰레드로컬방식을  사용해, 쓰레드-안전한 상태를 유지하기 위해 하나의 요청에서 함수들이 돌아가며 객체를 주고받을 필요가 없도록 했다. 이런 접근은 편리하지만, 의존 주입을 하거나 요청에 고정된 값을 사용하는 코드를 재사용하려할 때 유효한 요청 문맥을 요구한다. Flask 프로젝트는 쓰레드로컬에 대해 투명하고, 숨기지 않고, 심지어 사용되는 코드와 문서에서 드러내고 있다. 


웹개발에서 주의점
--------------------------------


웹 어플리케이션을 개발할때에는 항상 보안에 대해 신경써야한다.

여러분이 웹 개발을 할때, 개발된 어플리케이션의 사용자들은 여러분의 서버에 사용자의 정보가 등록되고 남겨지는 것을 허용할 것이다. 사용자는 데이타에 있어서 여러분을 신뢰한다는 것이다. 만약 여러분이 직접 작성한 어플리케이션의 유일한 사용자라 할지라도, 자신의 데이타가 안전하기를 원할 것이다.

불행히도, 웹 어플리케이션의 보안이 타협되는 여러 가지 경우가 있다. 프라스크는 현대의 웹 어플리케이션의 가장 일반적인 보안 문제인 XSS로 부터 여러분을 보호한다. 굳이 여러분이 안전하지 않게 작성된 HTML을 안전하게 변환하지 않더라도, Flask와 그 하부의 Jinja2 템플릿 엔진이 여러분을 보호해준다. 그러나 보안문제를 유발하는 더 많은 경우가 있다.

이 문서는 보안에 있어 주의를 요구하는 웹 개발의 측면을 여러분에게 당부하고 있다. 이런 보안 관점의 몇몇은 일부 사람이 생각하는것 보다 훨씬 복잡하고, 우리 모두는 때때로 취약점이 이용될것이라는 가능성을 뛰어난 공격자가 우리의 어플리케이션의 취약점을 찾아낼때까지 낮게 점치곤한다. 그리고 여러분의 어플리케이션이 공격자가 칩입할 만큼 중요하지 않다고 생각하지 마라. 공격의 종류에 따라, 자동화된 bot이 여러분의 데이타베이스에 스팸을 채우기 위해 탐색하거나, 악성코드를 링크하는 방식과 같은 기회들이 있다.

Flask는 여러분이 반드시 주의하며 개발해야하고, 요구사항에 맞춰 개발할때 취약점을 조심해야 하는 측면은 어느 다른 프레임워크와도 같다.


Python3의 상태
----------------------

요즘 파이썬 공동체는 파이썬 프로그래밍 언어의 새로운 버전을 지원하기 위한 라이브러리의 개선 과정중이다. 상황은 대단히 개선되고 있지만, 우리들이 파이썬3로 넘어가는데 걸림돌이 되는 몇가지 이슈가 있다. 이 문제들은 부분적으로 오래동안 검토되지 않은 언어의 변화에 의해 야기됐다. 부분적으로는 우리들이 저수준API가 파이썬3에서 유니코드의 차이점에 맞춰 어떤식으로 바뀌어야 하는지 해결해내지 못했다는 점도 있다. 

Werkzeug과 Flask는 그 변경에 대한 해결책을 찾는 순간 파이썬3로 포팅되고, 파이썬3으로 개발된 버전의 업그레이드에 대한 유용한 팁을 제공할 것이다. 그때까지, 여러분은 개발하는 동안 파이썬2.6이나 2.7을 파이썬3 경고를 활성화한 상태로 사용할 것을 권고한다. 여러분이 근래에 파이썬3로 업그레이드를 계획중이라면 `How to write forwards compatible
Python code <http://lucumr.pocoo.org/2011/1/22/forwards-compatible-python/>`_.를 읽는것을 적극 추천한다.

계속해서 :ref:`installation` 과 :ref:`quickstart` 살펴볼 수 있다.
