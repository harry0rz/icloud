# rpi-nextcloud

## 简介
在Raspberry Pi上使用docker-compose编排nextcloud、Mariadb、redis、nginx

## 使用方法

1. 前期准备

   * 树莓派系统安装
   * docker安装
   * docker-compose安装
   * git

2. 部署

   * 拉取代码

   ```bash
   $ git clone https://github.com/WhisperChi/rpi-nextcloud.git
   ```

   * 修改配置文件

   db.env

   修改为

   ```
   MYSQL_PASSWORD=<your-db-passwd>
   MYSQL_DATABASE=nextcloud
   MYSQL_USER=nextcloud
   ```

   docker-compose.yml

   修改为

   ```
   MYSQL_ROOT_PASSWORD=<your-mariadb-root-passwd>
   ```

   * 部署

   ```bash
   $ cd rpi-nextcloud
   $ bash init_dir.sh
   $ docker-compose up -d
   ```

3. 数据迁移

   * 硬盘拷贝
   ```bash
   cp icloud/nc_config/nextcloud/data/{user} /media/XXXXX


   拷贝
   cp -R /media/XXX/data/{user}
   sudo docker exec -u www-data -ti icloud_app_1 php occ files:scan zonebi
   ```

   
