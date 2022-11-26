# Tyoecho美化登陆页面-Typecho-login-page
## 第一步：注释掉原来的代码，方便参考对比
我这是使用的是VS Code工具，打开样式表后第一步，先对代码格式化，这样方便查看代码
需要修改的文件在admin/css/style.css第776行，为了不破坏原始样式把原样式表先注释掉。

## 第二步：新建 /** new登录框 */
~~~
/** new登录框 */
.typecho-login-wrap {
  width: 100%;
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  background: linear-gradient(-225deg, #ffecb3 0%, #17a2b8 50%, #77216f 100%);
}
.typecho-login {
  width: 23rem;
  height: 25rem;
  box-shadow: 0.2rem 0.2rem 0.5rem rgb(0, 0, 0, 0.5);
  padding: 0 2rem;
  position: relative;
  z-index: 1;
}
.typecho-login::before {
  content: "";
  width: 100%;
  height: 100%;
  background: rgb(255, 255, 255, 0.6);
  border-radius: 1rem;
  position: absolute;
  z-index: -1;
  top: 0;
  left: 0;
  filter: blur(1rem);
}
.typecho-login input {
  border: 1px solid #77216f;
  border-radius: 0.3rem;
}
.typecho-login button {
  background: #77216f;
  border-radius: 0.3rem;
  letter-spacing: 2rem;
  text-indent: 1rem;
}
.typecho-login button:hover {
  background: #a96693;
}
.typecho-login h1 {
  text-align: center;
}
.more-link {
  border-top: 1px solid #77216f;
}
.typecho-login .more-link a {
  display: inline-block;
  text-align: center;
  width: 48%;
  padding-top: 1rem;
  color: #77216f;
}
~~~
最终效果

使用Css的flex布局登录框居中现实，使用伪类元素::before叠到登录框下方实现背景模糊。

### 注意 ：

在使用filter: blur(1rem);滤镜，效果不要加在内容元素上，它会是内容元素的内容全部模糊
