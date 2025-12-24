# GCP-ALB-PSC-to-ILB-with-gke-pod-backend

## 建立服務
1. 建立 nginxdeploy.yaml
2. 建立nginxsvc.yaml
建立完成後即可創建出 微服務 及neg 後續會使用ilb 當前端 再將ilb 透過 psc與不同vpc Alb串接


## 建立ILB
1. 建立ILB 後端使用 GKE SVC 建立出的NEG

```text
kubectl describe svc nginx-psc-svc 
```
<img width="2299" height="554" alt="image" src="https://github.com/user-attachments/assets/c46a43e9-c1fb-482f-bcf7-408f7762d476" />

## 建立PSC 

1.先行建立發布服務
<img width="1788" height="641" alt="image" src="https://github.com/user-attachments/assets/a12ec931-d7ca-4765-b1f1-51f72ccafc2b" />
<img width="1395" height="1193" alt="image" src="https://github.com/user-attachments/assets/48e62c8e-b10c-4cfc-9af7-e77e151d4df3" />

2.發布後在使用PSC NEG 方式建立先留存稍早發布的服務連結如下順序

<img width="2037" height="1056" alt="image" src="https://github.com/user-attachments/assets/394dc8d2-f51a-4a80-9520-a81255e0b7ac" />
<img width="1400" height="940" alt="image" src="https://github.com/user-attachments/assets/a66ca066-fb19-4c98-a766-c8b010391a5d" />

3. 建立ALB放入稍早建立的psc neg後端(使用PSC就是為了不同VPC 所以要與ilb vpc不同)
<img width="2156" height="1211" alt="image" src="https://github.com/user-attachments/assets/fb88a1b2-1687-4d20-bf53-49c8d59709f6" />


<img width="2211" height="700" alt="image" src="https://github.com/user-attachments/assets/c101800d-4fd9-4eb5-9707-4ce5938fba1d" />

### 備註
1.若是發布服務沒有選自動接受，要回自己發布的服務進去點選接受
<img width="1121" height="1134" alt="image" src="https://github.com/user-attachments/assets/4283260d-eb0f-4e4b-b3b6-454f64bc094f" />

