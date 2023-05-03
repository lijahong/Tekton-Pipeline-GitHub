# Tekton-Pipeline-Project
#### [ 상세 내용 링크 ](https://velog.io/@lijahong/series/0%EB%B6%80%ED%84%B0-%EC%8B%9C%EC%9E%91%ED%95%98%EB%8A%94-TEKTON-%EA%B3%B5%EB%B6%80)

### Project 설명

#### Tekton을 이용한 Pipeline 구축 &amp; Trigger를 이용한 Pipeline 자동 실행

#### 사용 Repository
> - Code Repository : GitHub Private Repo
> - Image Repository : DockerHub Private Repo

#### Tekton을 이용한 CI / CD Pipeline 구축
> 1. GitHub Private Repo Clone
> 2. Kaniko를 이용하여 Docker Image Build & DockerHub Private Repo에 Push
> 3. Push한 Image를 이용하여 Deployment & Service를 Eks Cluster에 배포

#### Trigger를 이용한 Pipeline 자동 실행
> 1. Push Event 발생
> 2. WebHook을 통해 Json Payload가 EventListenr에게 전송
> 3. Trigger를 이용하여 Pipeline 실행

---

### 파일 설명

```shell
├── auth
│   ├── auth-sa.yaml
│   ├── dockerhub
│   │   └── docker-config-se.yaml
│   ├── github
│   │   └── github-secret.yaml
│   ├── gitlab
│   │   ├── git-ssl-se.yaml
│   │   └── gitlab-se.yaml
│   └── rbac
│       ├── clusterole.yaml
│       └── clusterrolebind.yaml
├── authapply.sh
├── delete.sh
├── pipeline
│   ├── pipeline.yaml
│   └── pipelineRun.yaml
├── setpipeline.sh
├── task
│   ├── gitclone.yaml
│   ├── kaniko.yaml
│   └── kubecommand.yaml
└── trigger
    ├── auth-trigger
    │   ├── role.yaml
    │   ├── rolebinding.yaml
    │   └── sa-trigger.yaml
    ├── eventlistener.yaml
    ├── ingress-trigger.yaml
    ├── trigerbinding.yaml
    └── trigertemplate.yaml
```
