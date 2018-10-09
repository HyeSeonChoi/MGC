# music-genre-classification

</br>

## 시행착오

 * model(18_08_28): 데이터에 흰색 공백(테두리)이 있음.
 
 * model(18_08_29): 데이터의 흰색 공백(테두리)를 없앰.
 
 * model(18_08_30): dropout을 뺌.
 
 * model_inceptionResNetV2 : 파라미터 5400만.파라미터가 많아도 효과를 비슷한 수준의 결과를 내서 더 빠른 모델로 선택함.
 
 * DenseNet : 파라미터 700만 
 
 * DenseNet_next : DenseNet에서 40 epoch돌리고 16 epoch 더 돌렸음 즉 약 56 epoch 정도 돌림
 
</br>

## Modeling

 
![1](https://user-images.githubusercontent.com/42205410/46679966-ff5c6600-cc22-11e8-8641-220be7b678b4.PNG)

 * 'Google Colab' 사용. Google에서 제공해주는 GPU로 model을 학습시킴.
 
 
![2](https://user-images.githubusercontent.com/42205410/46679974-04b9b080-cc23-11e8-8bec-c8f30aa477dd.PNG)

 * Keras 사용.

![3](https://user-images.githubusercontent.com/42205410/46679982-08e5ce00-cc23-11e8-8d38-f00be246e78c.PNG)

 * Data Split. ImageDataGenerator사용-> Train, Validation, Test 정의
 
 
![4](https://user-images.githubusercontent.com/42205410/46679987-0d11eb80-cc23-11e8-9375-47084736684c.PNG)
![5](https://user-images.githubusercontent.com/42205410/46679991-0edbaf00-cc23-11e8-810d-1f061c5ff073.PNG)

</br>

### DenseNet
![kakaotalk_20181009_234246286](https://user-images.githubusercontent.com/42205410/46678876-983db200-cc20-11e8-9ed7-f14dbb98ee1f.png)

이전 레이어에서 다음 레이어를 이어주는 추가적인 Connection을 만들어 주어 레이어간의 의미있는 논리 전개 가능. 

</br>


![6](https://user-images.githubusercontent.com/42205410/46680000-156a2680-cc23-11e8-8851-191a827bed36.PNG)

 * Optimizer: Adam.
 
 * decay: 0.01
 
 * patience=10. 10번째 기다렸다가 학습 정도의 개선의 여지가 없어서 스탑시킴. 원래 40 epoch돌리고 이 코드에서 16 epoch 더 돌린것.

![7](https://user-images.githubusercontent.com/42205410/46680008-1a2eda80-cc23-11e8-8367-2ea363d64827.PNG)
![8](https://user-images.githubusercontent.com/42205410/46680021-1ef38e80-cc23-11e8-99b2-b3006418fcaa.PNG)
![9 1](https://user-images.githubusercontent.com/42205410/46683828-223f4800-cc2c-11e8-9a7e-66b72d893083.jpg)
![10 1](https://user-images.githubusercontent.com/42205410/46683948-75b19600-cc2c-11e8-85f5-128b24a76a79.PNG)

</br>

 # Evaluate The Model

![11](https://user-images.githubusercontent.com/42205410/46680047-2c107d80-cc23-11e8-8e32-4ee475b4300f.PNG)
![12](https://user-images.githubusercontent.com/42205410/46680068-33d02200-cc23-11e8-9f65-ac3326572cf1.PNG)

 * 최종 결과 : 57.25%
