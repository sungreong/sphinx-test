# sphinx-test
sphinx 테스트 해보기

패키지 설치
```
pip install sphinx
pip install sphinx_rtd_them
```

1. 프로젝트 생성
```
mkdir sphinx-test

```
2. 프로젝트 집입 
```
cd sphinx-test
```
2. src 폴더 생성 및 여러개의 파이썬 코드 생성
```
mkdir src
## 코드 작성 
```
3. sphinx docs 생성
docs이 생성됨
```
sphinx-quickstart docs
```

4. conf.py  경로 수정 
* 자신이 상황에 맞게 path 수정이 필요함.
    * 현재 conf.py가 sphinx-test/docs/source안에 conf.py가 있음
    * 나의 소스 코드는 sphinx-test/src/my_package 안에 있음.

* 그러므로 아래와 같이 작성 해야함 (conf.py)
```
import os
import sys
sys.path.insert(0, os.path.abspath('../../src/my_package'))
```

5. conf.py enxteion 추가 하기 

```
extensions = ['sphinx.ext.autodoc']
```

나머지는 github project를 참고해서 수정

6.  Sphinx autodoc  적용하기

```
sphinx-apidoc -f -o docs/source/ src/my_package
```

7. index.rst에 modules 추가 하기 

* 6번 작업을 통해서 moudels.rst가 생성되면 index.rst에 추가해야 함.

* index.rst 참고 

8. html 만들기

```
cd docs
make html
```

9. github 페이지에 등록하기

* 아래 참고 

```
https://m.blog.naver.com/sooftware/221838103492
```