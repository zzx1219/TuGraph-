# TuGraph 专业综合实践作业1

## 一、TuGraph平台启动与部署

### 1. 部署步骤

本次实验使用阿里云TuGraph图数据库平台进行实验。

首先完成阿里云TuGraph平台的部署，按教程进入部署入口，申请了试用服务，并创建服务，获得了部署的browser、password、ssh等。

![](https://github.com/zzx1219/TuGraph-/blob/main/%E5%BE%AE%E4%BF%A1%E5%9B%BE%E7%89%87_20260919101212_8_48.png)

### 2. 系统登录

点击browser进入登录界面，输入所给的账号密码。

![](https://github.com/zzx1219/TuGraph-/blob/main/%E5%BE%AE%E4%BF%A1%E5%9B%BE%E7%89%87_20260919134126_40_48.png)

---

## 二、模型建立、数据导入及增删改查

### 1. 模型建立

本次实验建立了person和movie两种点类型，以及连接点的边类型produce。

![](https://github.com/zzx1219/TuGraph-/blob/main/%E5%BE%AE%E4%BF%A1%E5%9B%BE%E7%89%87_20260919110214_13_48.png)

![](https://github.com/zzx1219/TuGraph-/blob/main/%E5%BE%AE%E4%BF%A1%E5%9B%BE%E7%89%87_20260919110246_14_48.png)

![](https://github.com/zzx1219/TuGraph-/blob/main/%E5%BE%AE%E4%BF%A1%E5%9B%BE%E7%89%87_20260919110305_15_48.png)

模型建立完成后的结果如下：

![](https://github.com/zzx1219/TuGraph-/blob/main/%E5%BE%AE%E4%BF%A1%E5%9B%BE%E7%89%87_20260919172242_42_48.png)

### 2. 数据导入

将csv进行导入，对应点和边的属性。

![](https://github.com/zzx1219/TuGraph-/blob/main/%E5%BE%AE%E4%BF%A1%E5%9B%BE%E7%89%87_20260919110429_16_48.png)

![](https://github.com/zzx1219/TuGraph-/blob/main/%E5%BE%AE%E4%BF%A1%E5%9B%BE%E7%89%87_20260919110530_17_48.png)

### 3. 增加数据

使用CREATE语句向图数据库中增加节点或关系。

运行结果如下：
1.创建person节点

![](https://github.com/zzx1219/TuGraph-/blob/main/%E5%BE%AE%E4%BF%A1%E5%9B%BE%E7%89%87_20260919120320_32_48.png)

2.创建movie节点

![](https://github.com/zzx1219/TuGraph-/blob/main/%E5%BE%AE%E4%BF%A1%E5%9B%BE%E7%89%87_20260919125515_34_48.png)

3.给person添加照片



### 4. 查询数据

使用MATCH等Cypher语句对图数据库中的数据进行查询。

运行结果如下：

1.查询所有节点

![](https://github.com/zzx1219/TuGraph-/blob/main/%E5%BE%AE%E4%BF%A1%E5%9B%BE%E7%89%87_20260919110838_19_48.png)

2.根据标签匹配节点

![](https://github.com/zzx1219/TuGraph-/blob/main/%E5%BE%AE%E4%BF%A1%E5%9B%BE%E7%89%87_20260919111104_20_48.png)

3.根据标签和属性匹配节点

![](https://github.com/zzx1219/TuGraph-/blob/main/%E5%BE%AE%E4%BF%A1%E5%9B%BE%E7%89%87_20260919111237_22_48.png)

4.匹配任意关系

![](https://github.com/zzx1219/TuGraph-/blob/main/%E5%BE%AE%E4%BF%A1%E5%9B%BE%E7%89%87_20260919111530_24_48.png)

5.过滤匹配

### 5. 删除数据

使用DELETE等语句删除指定节点或关系。

运行结果如下：

（此处插入删除数据截图）

---

## 三、聚合查询

### 1. 查询目的

设计聚合查询，显示导演们的名字出生年份，以及创作的电影数量。

### 2. 查询语句

```cypher
MATCH (p:person)-[produce]-(mnmovie) RETURN p.name AS 人名, p.born AS 出生年份, count(m) AS 制作电影数 ORDER BY 制作电影数 DESC
```
### 3. 查询结果
