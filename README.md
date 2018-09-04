# 소개

이 프로젝트는 지시, 코드, 그리고 움직이는 로봇을 만들기 위한 아티팩트들을 포함하고 있습니다. 특히 우리는 숲처럼 불규칙한 환경에서 자동으로 비행하는 드론을 연구합니다. 우리의 장비들은 엔비디아의 젯슨 임베디드 플랫폼에서 동작하는 딥러닝 AI를 사용합니다. 코드들은 [참고](#참고)을 보시면, arXiv라는 논문에서 사용한 아이디어를 사용하고 있습니다.

이 프로젝트는 크게 다음 부분으로 나뉩니다. **모델링** 그리고 **플랫폼 구현** 으로요.

## 모델링

자율 주행을 가능하게 하는 이 프로젝트의 AI는 딥 뉴럴 네트워크(DNN)에 기반하고 있습니다. 또한, 여기서 이 DNN은 공개되어 이용가능한 데이터들을 사용하여, 아무것도 없는 상태서부터 훈련(train)되어질 수 있습니다. 아주 적은 [미리 훈련된 DNNs](https://github.com/NVIDIA-Jetson/redtail/tree/master/models/pretrained/)들은 이 프로젝트의 일부로써 이용가능합니다. 처음부터 TrailNet DNN을 학습시키고 싶으실 경우에는, 이 [Step](./Models.md)을 따라 주세요.

## 플랫폼

다음 플랫폼들이 현재 지원됩니다 :
* [TBS Discovery Platform](./Skypad-TBS-Discovery-Setup.md)
* [3DR IRIS+, older](./3DR-Iris-Setup.md)
* 특이한 이동체들은 지원이 곧 될 예정이랍니다.

일반적으로, [Pixhawk](https://pixhawk.org/) autopilot을 사용하는거면 어떤 플랫폼이든 작동할거에요.

APM기반의 이동체를 위해서 실험적으로 지원하는 것도 존재합니다:
* [Erle Rover](./Erle-Rover-Setup.md)

# 시작하기
완벽히 자율적으로 움직이는 드론 플랫폼(운항 계기 시스템)을 만드는 것은 적절한 하드웨어와 소프트웨어 설정을 필요로 합니다.

## Jetson 준비
NVIDIA Jetson 플랫폼은 DNN을 이용한 추론, 컨트롤러, 비디오 스트리밍 같은 대부분의 것들을 위해 사용되곤 합니다. [Jetson setup guide](./Jetson-Setup.md)는 SW간의 의존성을 고려하여 필요한 모든 소프트웨어를 설치하는 방법을 기술하고 있습니다.

## Drone 준비
드론 플랫폼에 따라서 몇몇의 추가적인 단계가 필요할지도 모릅니다. 당신의 플랫폼에 따라 각 문서에 있는 단계를 따라주세요.
* [TBS Discovery Platform](./Skypad-TBS-Discovery-Setup.md)
* [3DR IRIS+, older](./3DR-Iris-Setup.md)

## GCS (Ground Control Station) setup
노트북은 [QGroundControl](http://qgroundcontrol.com/)같은 GCS 소프트웨어를 실행하는 것뿐만아니라 NVIDIA 쉴드나 XBOX 컨트롤러를 사용하는 드론을 제어하기에도 편리한 방법입니다. GCS 장치를 설정하기 위해서는 [이 과정들](./GCSSetup.md)을 따르세요.

## 시뮬레이션
시뮬레이터에서 당신의 코드를 시험해보는 것은 좋은 생각입니다. Gazebo를 사용하여 시뮬레이션을 실행시키려면 [이 과정](./testing-in-simulator.md)을 따르세요.

## 비행
일단 하드웨어와 소프트웨어의 설정 단계가 완료되면, 이륙할 시간입니다! 드론을 날리기 위해 [이 과정](./Launch-Sequence-and-Flying.md)을 따르세요.

## 참고
* [arXiv paper](https://arxiv.org/abs/1705.02550)
* Our GTC 2017 talk: [slides](http://on-demand.gputechconf.com/gtc/2017/presentation/s7172-nikolai-smolyanskiy-autonomous-drone-navigation-with-deep-learning.pdf), [video](http://on-demand.gputechconf.com/gtc/2017/video/s7172-smolyanskiy-autonomous-drone-navigation-with-deep-learning%20(1).PNG.mp4)
* [Demo video showing 250 m autonomous flight, DNN activation and control](https://www.youtube.com/watch?v=H7Ym3DMSGms)
* [Demo video showing our record making 1 kilometer autonomous flight](https://www.youtube.com/watch?v=USYlt9t0lZY)
* [Demo video showing generalization to ground vehicle control and other environments](https://www.youtube.com/watch?v=ZKF5N8xUxfw)
* Stereo DNN, GTC18 talk: [arXiv paper](https://arxiv.org/abs/1803.09719), [Stereo DNN video demo](https://youtu.be/0FPQdVOYoAU)
