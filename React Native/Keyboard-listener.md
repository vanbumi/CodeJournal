const updateListener = Platform.OS === 'android' ? 'keyboardDidShow' : 'keyboardWillShow';
  const resetListener = Platform.OS === 'android' ? 'keyboardDidHide' : 'keyboardWillHide';
  this._listeners = [
      Keyboard.addListener(updateListener, this.updateKeyboardSpace),
      Keyboard.addListener(resetListener, this.resetKeyboardSpace)
  ];

**Contoh props yang di buat**

static propTypes = {
    topSpacing: PropTypes.number,
    onToggle: PropTypes.func,
    style: PropTypes.style,
    dismiss : PropTypes.func
};

nah itu tinggal implemet ke function keyboardnya

init ke layout

tinggal <Keyboard/>

di scroll view tampak keyboardShouldPersistTaps={'always'}

Ref:

[How to make your React Native app respond gracefully when the keyboard pops up](https://medium.freecodecamp.org/how-to-make-your-react-native-app-respond-gracefully-when-the-keyboard-pops-up-7442c1535580)
