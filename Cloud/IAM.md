# IAM

root 사용자: AWS계정을 생성한 email, 무한 권한을 가지고 있으므로 계정공유는 바람직 하지 않음

root 사용자로 로그인을 하는 것도 권장하지 않음   
권한을 부여하는 위치

 IAM: **인증 및 권한제어**

 User, Group, Policy: 최소권한 원칙

필수 키워드
- Effect –허용, 거부(Allow, Deny)
- Action–서비스특정작업
- Resource–리소스이름

```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "FullAccess",
            "Effect": "Allow",
            "Action": ["s3:*"],
            "Resource": ["*"]
    },
    {
        "Sid": "DenyCustomerBucket",
        "Action": ["s3:*"],
        "Effect": "Deny",
        "Resource": ["arn:aws:s3:::customer",       "arn:aws:s3:::customer/*" ]
    }
    ]
}
```


```json
{

    "Version": "2012-10-17",
    "Statement": [
        {
            "Action": [         //이 행동들에 대해서
                "ec2:RunInstances",
                "ec2:StartInstances",
                "ec2:StopInstances",
                "ec2:RebootInstances"
        ],
        "Resource": "*",
        "Effect": "Allow",      //권한허락이 된다.
        "Condition": {
            "StringEquals": {
                "ec2:Region": "us-east-2"  // us-east-2 region안에 있는 ec2에 대해서만
                }
            }
        }
    ]
}
```

us-east-2에 있는 ec2에 대해서만 Action을 Allow

IAM 그룹설정으로 그룹내 사용자들에세 상속의 방식으로 부여가능

정책생성기에서 생성가능

**암시적 deny대신 명시적 deny를 하는 이유**
- 여러 권한을 가지다 보면 생각치 못한 부분에서 Allow를 받게 됨
- 중요한 부분에서는 명시적 deny가 필요함

###### MFA 설정

User
- console : username/ password
- cli, sdk: accesskey/ secretaccesskey

Group

Policy
- 관리형 정책: 반복부여 -> AWS, 고객
- 인라인 정책: 1회성

role: 임시권한행사
- user (계정내/계정내)
- 서비스 -> 서비스
- 자격증명연동