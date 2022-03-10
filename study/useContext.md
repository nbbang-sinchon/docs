# useContext

## useContext를 사용하는 이유 

- context를 이용하면 단계마다 일일이 props를 넘겨주지 않고도 컴포넌트 트리 전체에 데이터를 제공할 수 있다.
- context는 React 컴포넌트 트리 안에서 전역적(global)이라고 볼 수 있는 데이터를 공유할 수 있도록 고안된 방법.
- 본 프로젝트에서는 login state와 socket을 전역적으로 관리하기 위해 사용함.

## createContext : Context 생성 

- Context를 생성하기 위해서는 createContext 함수를 사용한다.
- createContext의 파라미터에는 해당 Context에 initilaValue값을 입력한다.
- 기본값을 따로 지정하지 않을 경우에는 파라미터를 비워두거나 null을 입력.
 

```
export const LoginStoreContext = createContext();
```

## Provider : Context의 값을 설정

- 생성된 Context 내부에는 Provider 라는 컴포넌트가 존재한다.
- Provider 컴포넌트는 value prop을 받아서 이 값을 하위에 있는 컴포넌트에게 전달한다. 
- Context의 값을 설정할 때는 이 Provider의 value prop에 전달해주면 된다.
- 저장된 값을 사용할 컴포넌트들을 Provider로 감싸준다. 

```
<LoginStoreContext.Provider value={{ isLoggedin, setIsLoggedin }}>{children}</LoginStoreContext.Provider>;
```
```
<LoginStore>
    <Routes>
        <Route path="/" element={<IndexPage />} />
        <Route path="/login" element={<LoginPage />} />
    </Routes>
</LoginStore>
```
## useContext

- Provider 컴포넌트로 감싸져 있는 컴포넌트에서는 Context를 사용할 수 있다. 
- 이때 useContext를 이용하고 인자로는 맨 처음에 만든 Context를 넘겨줘야 한다. 
- 따라서 Context 를 import하고 useContext를 사용한다.
```
const { isLoggedin } = useContext(LoginStoreContext);
```


