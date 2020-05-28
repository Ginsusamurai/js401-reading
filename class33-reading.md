# Context API

## Context

- a way to pass state down through the tree in a `provider/consumer` relationship
- at as high a level as needed, you can make a `provider`
- you create a `<SettingsContext.Provider>` element and at the app level you can wrap that around your component

## ways to get context

- wrapper and use a `get` function to pull in context
- declare the connection directly and access `this` of the provider
- function components can access via `useContext()`


### Resources

#### Articles

- [context api](https://reactjs.org/docs/context.html)
- [hooks and context example](https://medium.com/swlh/snackbars-in-react-an-exercise-in-hooks-and-context-299b43fd2a2b)

```javascript
export const SnackBarContext = createContext()

export function SnackBarProvider({ children }) {
  const [alerts, setAlerts] = useState([])

  return (
    <SnackBarContext.Provider value={{ setAlerts }}>
      {children}
      {alerts.map((alert) => <SnackBar key={alert}>{alert}</SnackBar>)}
    </SnackBarContext.Provider>
  )
}
```

```javascript
import { useContext } from 'react'

import { SnackBarContext } from 'components/snack-bar-provider'

const useSnackBars = () => useContext(SnackBarContext)

export default useSnackBars
```

- [react context links](https://github.com/diegohaz/awesome-react-context)