# React Dev Guide
- Typescript, React, Vitejs 기반 개발을 위해 사용을 위한 주요 가이드 모음
- [material-kit-react](https://github.com/devias-io/material-kit-react) 기반으로 구성됨

## 가이드 구성 진행 사항
- [ ] typescript 적용
- [ ] playwright 적용
- [ ] i18n 적용
- [ ] tailwind 적용 여부 결정
- [ ] Scss 적용방안 결정
- [ ] 필요하지 않은 패키지 제거
  - [ ] 차트 관련 라이브러리 D3로 대체
- [ ] [vue-dev-guide](https://github.com/socketbear/vue-dev-guide) 팔로우
- [ ] 타 스타트킷 논의
  - [ ] https://reactjs-kr.firebaseapp.com/community/starter-kits.html
  - [ ] 스타트킷 중 next, tailwind, playwright, scss, 18n, typescript, theme, auto import 모두 만족하는 패키지도 없으며
  일부 만족하되 불필요한 세팅이 많은 템플릿이 많아 직접 제작하는 방향으로 가야 할 것 같습니다.

### 스타트킷 관련 문서 목록
- https://github.com/dunky11/react-saas-template
- https://reactjs-kr.firebaseapp.com/community/starter-kits.html
- https://github.com/cruip/open-react-template/tree/master

## 프레임워크의 추가 될 기본 기능들

- ⚡️ [React](https://react.dev/), [pnpm](https://pnpm.io/), [Vite 3](https://github.com/vitejs/vite)

- 🗂 [File based routing](./src/pages)

- 📦 [Components auto importing](./src/components)

- 🍍 [State Management via Next](https://nextjs.org/docs/getting-started/installation)

- 📑 [Layout system](./src/layouts)

<!-- - 📲 [PWA](https://github.com/antfu/vite-plugin-pwa) -->

- 🎨 [UnoCSS](https://github.com/antfu/unocss) - the instant on-demand atomic CSS engine

- 😃 [Use icons from any icon sets with classes](https://github.com/antfu/unocss/tree/main/packages/preset-icons)

- 🌍 [I18n ready](./locales)

<!-- - 🗒 [Markdown Support](https://github.com/antfu/vite-plugin-vue-markdown) -->

<!-- - 📥 [APIs auto importing](https://github.com/antfu/unplugin-auto-import) - use Composition API and others directly -->

- 🖨 Static-site generation (SSG) via [vite-ssg](https://github.com/antfu/vite-ssg)

- 🦔 Critical CSS via [critters](https://github.com/GoogleChromeLabs/critters)

- 🦾 TypeScript, of course

- ⚙️ Testing with [Playwright](https://playwright.dev/) on [GitHub Actions](https://github.com/features/actions)

# 프레임 워크 기반 프로젝트 진행 계획
[vue-dev-guide](https://github.com/socketbear/vue-dev-guide)를 이용한 프로세스 기반으로 진행
1. (프론트엔드) 고객 산출물에 해당하는 기능 POC, 저장소 설정등 프로젝트 세팅
2. (프론트엔드) 저장소를 퍼블리셔에게 전달
3. (퍼블리셔)  화면설계서 기반 화면 구성(컴포넌트 추가, 디자인 및 테마 적용)
4. (퍼블리셔)  저장소 업데이트
5. (All)    결과물 리뷰
6. (All) 	퍼블리셔 수정사항 반영, 개발팀 상세 구현

### 논의해야 할 내용
- 기존 퍼블리싱 절차에 대한 문서가 있는지
- 아니라면 새로운 가이드라인 문서를 작성 및 제시 해야 하는 것인지


## [Material Kit - React](https://material-kit-react.devias.io/)

![license](https://img.shields.io/badge/license-MIT-blue.svg)

[![Material Kit - React](https://github.com/devias-io/material-kit-react/blob/main/public/assets/thumbnail.png)](https://material-kit-react.devias.io/)

> Free React Admin Dashboard made with [MUI's](https://mui.com/?ref=devias-io)
> components, [React](https://reactjs.org/?ref=devias-io) and of
> course [Next.js](https://github.com/vercel/next.js/?ref=devias-io) to boost your app development
> process!

## Demo

- [Dashboard Page](https://material-kit-react.devias.io)
- [Companies Page](https://material-kit-react.devias.io/companies)
- [Customers Page](https://material-kit-react.devias.io/customers)
- [Account Page](https://material-kit-react.devias.io/account)
- [Settings Page](https://material-kit-react.devias.io/settings)
- [Login Page](https://material-kit-react.devias.io/auth/login)
- [Register Page](https://material-kit-react.devias.io/auth/register)

## Free Figma Community File

- [Duplicate File](https://www.figma.com/community/file/1039837897183395483/Devias-Dashboard-Design-Library-Kit)

## Quick start
- [Download from Github](https://github.com/devias-io/material-kit-react/archive/master.zip)
  or [Download from Devias](https://devias.io/products/material-kit-react) or clone the
  repo: `git clone https://github.com/devias-io/material-kit-react.git`

- Make sure your Node.js and npm versions are up to date for `React 18`

- Install dependencies: `npm install` or `yarn`

- Start the server: `npm run dev` or `yarn dev`

- Views are on: `localhost:3000`

## File Structure

Within the download you'll find the following directories and files:

```
material-kit-react

┌── .eslintrc.json
├── .gitignore
├── CHANGELOG.md
├── LICENSE.md
├── next.config.js
├── package.json
├── README.md
├── public
└── src
	├── components
	├── contexts
	├── guards
	├── hocs
	├── hooks
	├── layouts
	├── sections
	├── theme
	├── utils
	└── pages
		├── 404.js
		├── _app.js
		├── _document.js
		├── account.js
		├── companies.js
		├── customers.js
		├── index.js
		├── products.js
		└── settings.js
		└──  auth
			├── login.js
			└── register.js
```

## License
- Licensed under MIT (https://github.com/devias-io/react-material-dashboard/blob/master/LICENSE.md)

## Contact Us

- Email Us: seongpil0948@gmail.com
