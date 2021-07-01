# 클라우드 AWS EC2를 이용한 리눅스 머신(서버) 구하기

---

> AWS의 EC2(Elastic Cloud Compute)를 사용하여 리눅스가 있는 서버 인스턴스를 사용할 수 있다.

![2-0](https://user-images.githubusercontent.com/69946102/124129108-69df1f80-dab8-11eb-8e55-c48b609eb2ab.png)

1) AWS([https://aws.amazon.com](https://aws.amazon.com/))에 접속한다.

![2-1](https://user-images.githubusercontent.com/69946102/124129195-8418fd80-dab8-11eb-9bbb-aef95b477146.png)

2) 무료 계정 생성을 클릭하여, 개인정보 및 신용카드 정보를 입력한다.

![2-2](https://user-images.githubusercontent.com/69946102/124129223-8aa77500-dab8-11eb-89fc-b8bd0a965b42.png)

3) 회원가입을 완료하고, 메인페이지로 이동한다.

![2-3](https://user-images.githubusercontent.com/69946102/124129240-8e3afc00-dab8-11eb-93b1-17f88a7a95f7.png)

4) 메뉴 중 Amazon EC2를 선택하여 페이지를 이동한다.

![2-4](https://user-images.githubusercontent.com/69946102/124129249-92ffb000-dab8-11eb-8bc1-e242577cdf53.png)

5) 가운데 주황색 '인스턴스 시작' 버튼을 클릭한다.

![2-5](https://user-images.githubusercontent.com/69946102/124129252-9430dd00-dab8-11eb-819b-ce7593eca338.png)

6) AMI로 'Ubuntu 20-04'를 선택한다.

![2-6](https://user-images.githubusercontent.com/69946102/124129256-9430dd00-dab8-11eb-8b04-7278bea934ac.png)

7) 설정을 마치고 '시작하기'버튼을 눌러 인스턴스를 선택하고, '새 키 페어 생성'을 할 수 있다. 현재까지의 설정을 거쳐 인스턴스를 생성하고, '.pem' 파일을 받을 수 있게 된다.

</br>

[https://docs.aws.amazon.com/ko_kr/AWSEC2/latest/UserGuide/putty.html](https://docs.aws.amazon.com/ko_kr/AWSEC2/latest/UserGuide/putty.html)

***cf. AWS공식 문서에서는 PuTTY를 이용해 Windows에서 Linux 인스턴스를 활용하는 방안을 제시한다. 위의 주소에 들어가면 자세한 설명을 볼 수 있다.***

![2-7](https://user-images.githubusercontent.com/69946102/124129260-94c97380-dab8-11eb-85e5-329189bdfb79.png)

8) 본인의 PC 환경에 맞는 PuTTY를 설치하고, 'PUTTYGEN.exe'를 실행한다.

![2-8](https://user-images.githubusercontent.com/69946102/124129262-94c97380-dab8-11eb-9568-618a1cf1a3c9.png)

9) 'Load'를 눌러, 다운받았던 '.pem'을 가져온 후, 'Save private key'를 클릭하여, '.ppk'파일을 생성할 수 있다.

![2-9](https://user-images.githubusercontent.com/69946102/124129264-95620a00-dab8-11eb-88d2-49dd0090010e.png)

10) 'PUTTY.exe'를 실행하여, 좌측 메뉴에서 'Connection > SSH > Auth'로 이동한다. 이후, 'Browse...' 버튼을 눌러 이전에 만든 '.ppk'파일을 선택한다.

![2-10](https://user-images.githubusercontent.com/69946102/124129266-95faa080-dab8-11eb-8009-0ecabbddf5c5.png)

11) 다시, PUTTY에서 맨 위의 'Session' 탭에 들어간다. 이후, AWS의 '인스턴스' 탭을 눌러, '퍼블릭 IPv4 DNS'를 찾아 'Host Name'에 입력한 후 'Open'을 클릭한다.

![2-11](https://user-images.githubusercontent.com/69946102/124129267-95faa080-dab8-11eb-90e4-cf513c83c507.png)

**실행 완료.**

---
![2-12](https://user-images.githubusercontent.com/69946102/124129269-96933700-dab8-11eb-84d2-db39172b98ba.png)

11번의 과정에서 위와 같은 에러를 볼 수 있었다. (PuTTY Fatal Error)

구글링을 통해 해결책을 찾을 수 있었다.

![2-13](https://user-images.githubusercontent.com/69946102/124129272-96933700-dab8-11eb-8dde-722e32ee5ee0.png)

다시 'PUTTYGEN.exe'를 실행해 'Import Key'를 하여, '.pem'을 불러와 'Parameters'를 'SSH-1'로 설정 하고, 'Generate' → ' Save private key'의 과정을 거쳐 새로운 key를 생성하여 다시 시도해본다.
