---
order: 2
title: propmt
---

包含输入普通文字, 密码, 登录信息样式

````__react
import { Modal, Button, WingBlank, WhiteSpace } from 'antd-mobile';

const prompt = Modal.prompt;

const App = React.createClass({
  render() {
    return (
      <WingBlank size="lg">
        <WhiteSpace size="lg" />
        <Button onClick={() => prompt('输入名字', '这是名字的 message', [
            { text: '取消' },
            { text: '提交', onPress: value => console.log(`输入的内容:${value}`) },
        ])}
        >输入框按钮按钮 </Button>

        <WhiteSpace size="lg" />
        <Button onClick={() => prompt('默认值', '默认值 defaultValue 类型', [
          { text: '取消' },
          { text: '提交', onPress: value => console.log(`输入的内容:${value}`) },
        ], 'plain-text', '100')}
        >输入框默认值 </Button>

        <WhiteSpace size="lg" />
        <Button onClick={() => prompt(
          '输入密码',
          '这是密码message,可以不要',
          password => console.log(`password: ${password}`),
          'secure-text',
        )}
        >输入框密码形式 </Button>

        <WhiteSpace size="lg" />
        <Button onClick={() => prompt(
          '输入密码',
          '这是密码message,可以不要',
          [
            { text: '取消' },
            { text: '提交', onPress: password => console.log(`密码为:${password}`) },
          ],
          'secure-text',
        )}
        >自定义按钮形式 </Button>

        <WhiteSpace size="lg" />
        <Button onClick={() => prompt(
          '登录',
          '输入用户名和密码',
          (login, password) => console.log(`login: ${login}, password: ${password}`),
          'login-password',
        )}
        >输入框登录形式 </Button>

        <WhiteSpace size="lg" />
      </WingBlank>
    );
  },
});


ReactDOM.render(
  <App />
, mountNode);

````
