# RK-X3 json
----------------------
## 入网配置
### 网络配置
```
> LAN配置接口信息
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

```
> 获取人脸网关管理默认信息
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
> 配置人脸网关管理信息
{
    method: "post",
    data: {
        name: "require",   // 网关名称
        mqtt: "",         // MQTT
    }
}
```
### 摄像头管理
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

```
{
    method: "post",
    data: {

    }
}
```

### 通道信息