# REACT NATIVE

Pour solutionner cette erreur : 

error Invalid regular expression: /(.*\\__fixtures__\\.*|node_modules[\\\]react[\\\]dist[\\\].*|website\\node_modules\\.*|heapCapture\\bundle\.js|.*\\__tests__\\.*)$/: Unterminated character class. Run CLI with --verbose flag for more details.

Le problème vient d'antislash dans \node_modules\metro-config\src\defaults\blacklist.js

- [Source](https://stackoverflow.com/questions/58120990/question-getting-error-on-react-native-start)



Pour solutionner l'erreur "font family roboto is not a system font and has not been loaded through font.loadasync" sur ios. Fermez votre serveur react native et dans la console tapez :
```bash
npm install expo-font
```
Ensuite, allez dans votre application react Native et dans votre fichier "App js", ajouter toutes ces lignes (A adapter suivant votre code déjà présent):

```bash
import * as Font from "expo-font";
import { ActivityIndicator } from "react-native";

export default class App extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      loading: true
    };
  }


  async componentWillMount() {
    await Font.loadAsync({
      Roboto: require("./assets/fonts/Roboto.ttf"),
      Roboto_medium: require("./assets/fonts/Roboto-Medium.ttf"),
    });
    this.setState({ loading: false });
  }


  render() {
    if (this.state.loading) {
      return <ActivityIndicator />;
    }
    return (
      ...
    );
  }
}
```
Lancez votre serveur.

