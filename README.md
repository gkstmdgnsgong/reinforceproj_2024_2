# reinforceproj_2024_2
상명대학교 강화학습 2024-2 프로젝트

## 1. Introduction
환경에 따른 알고리즘  
비교 및 향상

•난이도에 따라 초급 환경, 중급 환경, 고급 환경을 선택하고 알고리즘 비교 분석 진행

	•초급 환경: CartPole-v1에서 DQN, REINFORCE, PPO, Actor-Critic 비교.

	•중급 환경: MountainCar-v0 에서 정책 기반(REINFORCE)과 값 기반(DQN) 비교.

	•고급 환경: BipedalWalker-v3에서 PPO와 Actor-Critic 비교.


## 2. Code
[초급 환경 DQN](https://github.com/gkstmdgnsgong/reinforceproj_2024_2/blob/main/code/cartpole_DQN.ipynb)

[초급 환경 REINFORCE](https://github.com/gkstmdgnsgong/reinforceproj_2024_2/blob/main/code/cartpole_REINFORCE.ipynb)

[초급 환경 Actor-Critic](https://github.com/gkstmdgnsgong/reinforceproj_2024_2/blob/main/code/cartpole_actor_critic.ipynb)

[초급 환경 PPO](https://github.com/gkstmdgnsgong/reinforceproj_2024_2/blob/main/code/cartpole_PPO.ipynb)

[중급 환경 DQN](https://github.com/gkstmdgnsgong/reinforceproj_2024_2/blob/main/code/mountain_DQN.ipynb)

[중급  환경 REINFORCE](https://github.com/gkstmdgnsgong/reinforceproj_2024_2/blob/main/code/mountain_REINFORCE.ipynb)

[고급 환경 DQN](https://github.com/gkstmdgnsgong/reinforceproj_2024_2/blob/main/code/bipedal_DQN.ipynb)

[고급 환경 Actor-Critic](https://github.com/gkstmdgnsgong/reinforceproj_2024_2/blob/main/code/bipedal_actor-critic.ipynb)

[고급 환경 PPO](https://github.com/gkstmdgnsgong/reinforceproj_2024_2/blob/main/code/bipedal_PPO.ipynb)


## 3. 결론

**초급 환경 결론**

	•각 알고리즘의 간단한 개요에 대해 알아봄

	•Cartpole 환경이 쉬운 환경이기에 별도의 튜닝 없이도 4가지 모두 최적에 도달함.

	•이후 비교적 심화된 환경에서 정책기반, 값 기반 알고리즘의 차이를 볼 예정

**중급 환경 결론**

	•Reinforce 결과 고찰

	•dqn은 off-policy 이고, Reinforce 의 경우 on-policy 이다. dqn은 학습의 target이 state 상에서 받을 수 있는 가장 큰 가치를 사용하여, 항상 최고의 상태값을 받지만, Reinforce은 확률적으로 정책을 선택하므로 상황에 맞는 다른 가치를 받게 된다.

	•상황에 따라 다른 가치를 받아 정책을 발전시키는 것이 Policy Gradient 의 의미인데 반해, Mountain car에서 문제는 상황에 따른 것이 아닌 꾸준한 보상이 쌓여 행동을 개선시켜 나가야 되는데, REINFORCE는 보상 자체가 쌓이기 어려운 환경이라는 것

**고급 환경 결론**

DQN 실패 사례 및 고찰

	• 일반적 방식의 DQN은 Bipedal Walker 환경에서 올바르게 작동하지 않았음

	•행동 이산화의 한계:  BipedalWalker-v3는 연속 행동이 필요한 환경이나 6단계로만 이산화 했기에 세밀한 조작을 반영하지 못해 학습이 어려워짐.

	•DQN은 일반적으로 상태-행동 쌍이 적고, 연속적이지 않은 문제에 더 적합한 알고리즘이기 때문에 예정된 문제일 수 있음

	•연속 행동 환경에서는 DDPG, SAC, PPO와 같은 연속 제어를 지원하는 알고리즘이 더 적합할 것으로 판단

Actor-Critic & PPO 고찰

	•결과적으로 PPO의 성능이 Actor-Critic에 비해 잘 나옴.

	•Actor-Critic의 파라미터 튜닝으로 성능 향상 가능성이 있지만 PPO를 사용함.

	•PPO알고리즘을 통해 학습 안정성을 개선시켰고, 좋은 성능을 보임.
