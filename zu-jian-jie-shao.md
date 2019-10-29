## 问题反馈

### 效果展示

### ![](/assets/b1.png)![](/assets/b2.png)

### [安装依赖](https://baidu.com)

```
npm i feedback-qrcode --save -S
```

### 调用

```
import feedbackQrcode from 'feedback-qrcode/libs/index.js';

/**
 * isOpen: 是否展开，默认收起
 * tabAction: 初始显示的界面
 * ----值为：form 问题反馈(表单提交界面)
 * ----值为：qrcode 语音反馈(小程序二维码界面)
 * ----值为：list 历史反馈(已反馈的列表界面)
 * feecBackQrcode: 问题反馈二维码图片地址(注：需要带来源参数)
 * uploadApi: 上传图片接口
 * ----url：String 上传图片接口地址
 * ----parseResponseData: 编辑接口返回的数据，(如果业务方封装的接口的响应数据与原始接口的响应数据不同，则业务方前端需要用这个方法把响应数据编辑成原始接口的响应数据)
 * ----原始接口响应数据：{code: 0, msg: '上传成功', data: {contentUrl: '/group1/**.png', contentType: 4}}
 * --------code: Number 接口状态，0为成功，-1为失败
 * --------msg: String 成功/失败信息
 * --------data: Object 存放成功的数据 url为图片地址
 */ 
feedbackQrcode.config({
    source: 'TMS',
    isOpen: false,
    tabAction: 'form',
    feecBackQrcode: 'https://image.tf56.com/dfs/group1/M00/18/12/CiFCLl2OqO2AREG5AACAZj11-vk823.png',
    uploadApi: {
        url: '/api/atmsCore/basecs/uploadCustAttachment',
        parseResponseData: (res) => {
            return {
                code: res.code,
                msg: res.msg,
                data: {
                    contentType: 4,
                    contentUrl: res.data && res.data[0] && res.data[0].attachmenturl ? res.data[0].attachmenturl : '',
                }
            }
        }
    },
    submitApi: {
        url: '/tfAppletsWeb/helpdesk/upload',
        parseResponseData: (res) => {
            return {
                code: res.code,
                msg: res.msg
            }
        }
    }
});
```

### 



