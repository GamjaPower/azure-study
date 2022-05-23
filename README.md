# azure-study

## 사전 준비물
- azure 계정
- 노트북 

## 스터디 내용
- AWS / Azure 비교 설명  
https://docs.microsoft.com/ko-kr/azure/architecture/aws-professional/services
- 과금정책 
- Azure에서 Terraform으로 인스턴스 생성 : terraform apply
- Key 생성 : terraform output -raw tls_private_key > id_rsa
- IP 확인 : terraform output public_ip_address
- ssh 접속 ssh -i id_rsa azureuser@x.x.x.x 
- 
- ansible hosts 생성 : VM_IP=&#96;terraform output public_ip_address&#96;; echo $VM_IP "ansible_ssh_user=azureuser" > ansible.hosts
- ansible ping : ansible -i ansible.hosts all  -m ping --private-key  ./id_rsa
- ansible create file : ansible-playbook -i ansible.hosts  --private-key ./id_rsa playbook.yml
- Terraform 할당된 자원들 모두 삭제 : terraform destroy

