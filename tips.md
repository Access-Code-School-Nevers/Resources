# REACT NATIVE
Pour solutionner cette erreur : 

error Invalid regular expression: /(.*\\__fixtures__\\.*|node_modules[\\\]react[\\\]dist[\\\].*|website\\node_modules\\.*|heapCapture\\bundle\.js|.*\\__tests__\\.*)$/: Unterminated character class. Run CLI with --verbose flag for more details.

Le problème vient d'antislash dans \node_modules\metro-config\src\defaults\blacklist.js

- [Source](https://stackoverflow.com/questions/58120990/question-getting-error-on-react-native-start)
