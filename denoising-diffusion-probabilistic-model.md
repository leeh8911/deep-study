# Denoising Diffusion Probabilistic Models
## Introduction
* 모든 종류의 심층 생성 모델은 다양한 데이터 모달리티에 대해 높은 수준의 샘플을 보여줌
  * Generative Adversarial Networks
  * Autoregressive Model
  * Flow
  * Variational AutoEncoder
* Diffusion Probabilistic Model은 유한 시간동안 생성한 샘플과 데이터를 매칭하는 variational inference를 활용한 파라미터화 된 Markov chain
  * 이런 연쇄 작용으로부터 발생한 전이는 신호가 파괴될 때 까지 샘플링의 역방향으로 점진적으로 데이터에 노이즈를 가하는 Markov chain인 확산 프로세스의 역방향을 학습
  * 확산이 작은 양의 가우시안 노이즈로 구성 될 때 샘플링의 연쇄 작용이 조건부 가우시안임을 만족하고 이를 통해 신경망을 간단히 parameterization이 가능
* Diffusion model은 정의하기 쉽고 효율적으로 학습되지만 우리가 아는 한 충분히 높은 품질의 샘플을 생성하는 시연은 없음
  * 우리가 diffusion models이 실제로 충분히 높은 품질의 샘플을 생성할 수 있음을 보였고, 종종 다른 타입의 생성 모델들의 논문에서 말하는 결과보다 더 나음
  * diffusion models의 확실한 파라미터화가 학습 과정에서 여러 노이즈 레벨에 대한 잡음 제거 점수 매칭과 샘플링 과정에서 annealed Langevin dynamic의 동등함을 보임
  * 확실한 파라미터화를 통해 최선의 품질 결과를 얻었고, 이 파라미터화가 논문의 최고 기여
* 이러한 그들의 샘플 품질에도 불구하고, 우리의 모델은 다른 우도 기반의 모델들에 비해 경쟁적인 log-likelihood가 없음