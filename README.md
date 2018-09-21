# RK-X3 json
----------------------
## 入网配置
### 网络配置
> LAN配置接口信息
```
{
    method: "post",
    data: {
        ip: "require",  // Ip地址
        subnet: "require",   // 子网掩码
        faultGateway: "require"   // 默认网关
    }
}
```
------------------------
## 设备配置
### 人脸网关管理

> 获取人脸网关管理默认信息
```
{
    method: "get",
    response: {
        type: "require",   //网关型号
        name: "require",   // 网关名称
        mac: "require",   //网关MAC
        version: "require",   //固件版本
        mqtt: "",         // MQTT
        supportLinesNum: "require"  //支持路数
    }
}
```
> 配置人脸网关管理信息
```
{
    method: "post",
    data: {
        name: "require",   // 网关名称
        mqtt: "",         // MQTT
    }
}
```
### 摄像头管理
> 获取摄像头管理列表信息
```
{
    method: "get",
    response: [
        {
            type: "in",      // 进
            name: "require",  // 摄像头名称
            maker: "require",  // 摄像头厂商
            id: "require",   // 摄像头序列号
            ip: "require",    //摄像头ip
            port: "requre"      //端口号
            protocol: "require",        //勾流方式
            linkStatus: "require",      //连接状态
        },
        {
            type: "out",      // 进
            name: "require",  // 摄像头名称
            maker: "require",  // 摄像头厂商
            id: "require",   // 摄像头序列号
            ip: "require",    //摄像头ip
            port: "requre"      //端口号
            protocol: "require",        //勾流方式
            linkStatus: "require",      //连接状态
        }
    ]
}
```
> 配置摄像头信息
```
{
    method: "post",
    data: {
            type: "require",      // 进/出
            name: "require",  // 摄像头名称
            ip: "require",    //摄像头ip
        }
}

```
-------------------------

## 功能管理
### 位置信息
> 获取位置列表信息
```
{
    method: "get",
    response: [
        {
            position: "require"    // 位置信息
        }
    ]
}
```
### 人脸库信息
> 下载人脸库信息
```
{
    method: "post",
    data: {
        serverIP: "require",  // server-ip
        id: "require"         // 人脸库ID
    }
}
```
> 获取人脸库列表信息
```
{
    method: "get",
    response: [
        {
            name: "require",   // 通行库名称
            type: "require",   //库类型
            soure: "require",  //库来源
            position: "require",  //位置信息
            count: {
                peopleNum: "require",   //人数
                photoNum: "require"    //照片数
            }
        }
    ]
}
```
> 查看人脸库人员信息列表
```
{
    method: "get",
    response: [
        {
            faceId: "require"     // 人员的face-id
        }
    ]
}
```
> 查看对应人脸库图片
{
    method: "get",
    param: {
        faceId: "require"  // 人员的face-id
    },
    response: [
        {
            imgUrl: "require"  // 人脸库图片
        }
    ]
}

### 通道信息
> 获取通道列表信息
```
{
    method: "get",
    response: [
        {
            type: "in",  // 进/出
            position: "require",  //位置信息
            carmeraIp: "require",   //摄像头IP
            relayIp: "require",    //继电器IP
            relayWay: "require",   //继电器通道信息
        }
    ]
}
```
> 配置通道信息
{
    method: "post",
    data: {
        type: "in",   // in进/out出
        ip: "require",    //摄像头IP
        liminal: "require"   //阀值
    }
}

-------------------
## 工程操作
### 工程测试
> 上传图片
```
{
    method: "post",
    data: {
        imgData: "require"   //FormData对象
    }
}
```
> 通道测试 
```
{
    method: "post",
    data: {

    }
}
```
--------------------------------
## 系统管理
### 抓拍日记
> 获取抓拍日记列表信息
```
{
    method: "get",
    response: {
        totalNum: "requre",      //总数
        list: [
            {
                time: "require",   // 操作日期
                wayInfo: "require",   // 通道信息
                type: "require",     //进或出
                imgUrl: "require"      // 图片地址
            }
        ]
    }
}
```
>  查询接口
```
{
    method: "get",
    param: {
        time: "require",   //根据时间筛选列表
    },
    response: {
        totalNum: "requre",      //总数
        list: [
            {
                time: "require",   // 操作日期
                wayInfo: "require",   // 通道信息
                type: "require",     //进或出
                imgUrl: "require"      // 图片地址
            }
        ]
    }
}
```
### 通信日记
> 获取通信日记列表信息
```
{
    method: "get",
    response: {
        totalNum: "requre",      //总数
        list: [
            {
                time: "require",   // 操作日期
                wayInfo: "require",   // 通道信息
                type: "require",     //进或出
                imgUrl: {
                    captureUrl: "require",    // 抓拍图片地址
                    lib: [                  // 对比列表
                        {
                            url: "reuqire",   // 来源库图片地址
                            semblance: "require",   //相识度
                            source: "require",   // 库来源
                        }
                    ]
                }      
            }
        ]
    }
}
```
>  查询接口
```
{
    method: "get",
    param: {
        time: "require",   //根据时间筛选列表
    },
    response: {
        totalNum: "requre",      //总数
        list: [
            {
                time: "require",   // 操作日期
                wayInfo: "require",   // 通道信息
                type: "require",     //进或出
                imgUrl: {
                    captureUrl: "require",    // 抓拍图片地址
                    lib: [                  // 对比列表
                        {
                            url: "reuqire",   // 来源库图片地址
                            semblance: "require",   //相识度
                            source: "require",   // 库来源
                        }
                    ]
                }      
            }
        ]
    }
}
```
### 存储