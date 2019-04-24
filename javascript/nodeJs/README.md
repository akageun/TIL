# Node.js

## NPM

#### npm init 
- -y 옵션 : package.json을 기본 값으로 채워주는 옵션
> npm init -y

#### 설치된 npm 제거
> npm uninstall {module_name}

- 글로벌 설치시에는 -g 옵션을 추가해주면 됨.
> npm uninstall -g {module_name}

#### 설치된 npm list
> npm list -g --depth=0

#### ENV 설정
> UNIX shell prompt : PORT=1234 node index.js
> WINDOWS : set PORT=1234 && node index.js

- Windows에서 개발할 경우 set을 붙여야해서 분기처리가 필요함.(cross-env를 사용하여 변경)
> npm install --save-dev cross-env

```json
{
  "scripts": {
    "start": "cross-env PORT=1234 node index.js"
  }
}
```