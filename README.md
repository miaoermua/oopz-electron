# oopz-electron
使用 electron 打包的 Oopz Linux 客户端

版权声明，本项目只是打包网页版 Oopz，并无做其他修改，服务和版权提供商依旧为: 绍兴未来山海科技有限公司

<img width="1322" height="959" alt="pages" src="https://github.com/user-attachments/assets/2472c155-2641-4d2c-8814-4020cf0c493c" />
<img width="1322" height="959" alt="login" src="https://github.com/user-attachments/assets/edc82a1d-2291-41bc-95c8-ee4bf07be20d" />

## 构建应用

需要安装 nodejs 环境，并且 clone 本项目

```bash
npm install
npm run build
```

## 安装

Archlinux(Arch 系):

> 待稳定后上传 AUR

```bash
wget https://github.com/miaoermua/oopz-electron/releases/download/v1.2.9/oopz-electron-1.2.9.pkg.tar.zst
sudo pacman -U oopz*
```

Debian/Ubuntu:

```bash
wget https://github.com/miaoermua/oopz-electron/releases/download/v1.2.9/oopz-electron-1.2.9_amd64.deb
sudo apt install oopz*
```
