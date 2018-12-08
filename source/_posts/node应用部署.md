---
title: node应用部署
date: 2018-10-07 22:13:32
tags: node
---
1. 和正常开发没啥差别。
2. 使用云数据库会好很多。
3. 使用pm2项目管理工具。
    1. 安装
        npm install -g pm2 
    2. 启动
        cd 到项目目录下，使用： pm2 start [入口文件]
    3. 查看进程
        pm2 ls
    4. 监控
        pm2 monit
    5. 停止
        pm2 stop all
        pm2 stop [id]
    6. 重载
        pm2 reload all
        pm2 reload [id]
    7. 重启
        pm2 restart all 
        pm2 restart [id]
    8. 删除
        pm2 delete all
        pm2 delete [id]
    9. 日志
        pm2 logs [--raw]
        pm2 flush
        pm2 reloadLogs
    10. 升级
        pm2 updataPM2
    11. 帮助
        pm2 --help