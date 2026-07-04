<!DOCTYPE html> <!-- 声明文档类型为HTML5 -->
<html lang="zh-CN"> <!-- 网页根元素，设置语言为中文 -->
<head>
    <meta charset="UTF-8"> <!-- 设置字符编码为UTF-8，保证中文正常显示 -->
    <meta name="viewport" content="width=device-width, initial-scale=1.0"> <!-- 视口设置，适配手机屏幕 -->
    <title>沙市里约游泳馆 | 荆州本地水上运动中心</title> <!-- 网页标题，显示在浏览器标签页 -->
    
    <!-- 内联CSS样式，控制整个页面的外观 -->
    <style>
        /* 全局样式重置，清除浏览器默认的边距 */
        * {
            margin: 0; /* 清除外边距 */
            padding: 0; /* 清除内边距 */
            box-sizing: border-box; /* 宽高包含边框和内边距，方便布局计算 */
        }
        
        /* 页面主体样式 */
        body {
            font-family: 'Microsoft YaHei', 'PingFang SC', sans-serif; /* 优先使用中文字体 */
            line-height: 1.6; /* 行高1.6倍，阅读更舒适 */
            color: #333; /* 文字默认深灰色 */
            background-color: #f5f7fa; /* 页面背景为浅蓝灰色，呼应水的主题 */
        }
        
        /* ========== 顶部导航栏样式（图片背景版） ========== */
        .header {
            /* 
                === 自定义图片背景设置说明 ===
                方式1：使用网络图片，直接把下面url()里的链接换成你的图片地址
                方式2：使用本地图片，把图片放在与HTML同目录下，url()里写 "./你的图片名.jpg"
            */
            background-image: url('https://images.unsplash.com/photo-1530549387789-4c1017266636?ixlib=rb-4.0.3&auto=format&fit=crop&w=1200&q=80'); /* 背景图片链接，替换这里即可自定义 */
            background-size: cover; /* 背景图片覆盖整个导航栏，保持比例裁剪 */
            background-position: center; /* 背景图片居中显示 */
            background-repeat: no-repeat; /* 背景图片不重复平铺 */
            position: relative; /* 相对定位，为伪元素叠加层做准备 */
            color: white; /* 头部文字白色 */
            padding: 1rem 0; /* 上下内边距1rem */
            position: sticky; /* 粘性定位，滚动时固定在顶部 */
            top: 0; /* 距顶部0 */
            z-index: 1000; /* 层级最高，防止被其他元素遮挡 */
            box-shadow: 0 2px 10px rgba(0,0,0,0.3); /* 底部阴影，增加层次感 */
        }
        
        /* 半透明叠加层（让背景图上的文字更清晰可读） */
        .header::before {
            content: ""; /* 伪元素必须有content属性 */
            position: absolute; /* 绝对定位，覆盖在背景图上 */
            top: 0; /* 顶部对齐 */
            left: 0; /* 左侧对齐 */
            width: 100%; /* 宽度占满 */
            height: 100%; /* 高度占满 */
            background: rgba(0, 0, 0, 0.4); /* 黑色半透明遮罩，0.4为透明度 */
            z-index: 1; /* 层级在背景之上，文字之下 */
        }
        
        /* 头部内容容器，需要放在遮罩层之上 */
        .header-content {
            max-width: 1200px; /* 最大宽度1200像素 */
            margin: 0 auto; /* 上下0，左右自动实现居中 */
            display: flex; /* 弹性布局 */
            justify-content: space-between; /* 两端对齐，左右各一个元素 */
            align-items: center; /* 垂直居中 */
            padding: 0 20px; /* 左右留20像素，防止小屏幕贴边 */
            position: relative; /* 相对定位 */
            z-index: 2; /* 层级高于遮罩层，保证文字可见 */
        }
        
        /* 游泳馆名称Logo样式 */
        .logo {
            font-size: 1.6rem; /* 字体大小 */
            font-weight: bold; /* 加粗 */
            letter-spacing: 2px; /* 字间距2像素 */
            text-shadow: 1px 1px 3px rgba(0,0,0,0.5); /* 文字阴影，让Logo在图片上更清晰 */
        }
        
        /* Logo中特殊文字用金色突出 */
        .logo span {
            color: #ffd700; /* 金色 */
        }
        
        /* 导航栏列表样式 */
        .nav ul {
            list-style: none; /* 去掉列表圆点 */
            display: flex; /* 横向排列 */
        }
        
        /* 导航项间距 */
        .nav ul li {
            margin-left: 25px; /* 每个导航项左边留25像素间距 */
        }
        
        /* 导航链接样式 */
        .nav ul li a {
            color: white; /* 链接白色 */
            text-decoration: none; /* 去掉下划线 */
            font-weight: 500; /* 中等粗细 */
            transition: color 0.3s; /* 颜色过渡动画0.3秒 */
            text-shadow: 1px 1px 2px rgba(0,0,0,0.3); /* 文字阴影，让导航在图片上更清晰 */
        }
        
        /* 导航链接悬停效果 */
        .nav ul li a:hover {
            color: #ffd700; /* 悬停时变为金色 */
        }
        
        /* 主横幅区域，用渐变模拟水的感觉 */
        .hero {
            background: linear-gradient(135deg, #0077b6 0%, #00b4d8 50%, #90e0ef 100%); /* 三层蓝色渐变 */
            height: 50vh; /* 高度占视口50% */
            display: flex; /* 弹性布局 */
            align-items: center; /* 垂直居中 */
            justify-content: center; /* 水平居中 */
            text-align: center; /* 文字居中 */
            color: white; /* 文字白色 */
            margin-bottom: 2rem; /* 下方留白2rem */
            position: relative; /* 相对定位 */
            overflow: hidden; /* 隐藏溢出内容 */
        }
        
        /* 装饰性水波纹效果 */
        .hero::before {
            content: "〰️〰️〰️〰️〰️〰️〰️〰️〰️〰️〰️〰️〰️〰️〰️"; /* 用波浪字符模拟水纹 */
            position: absolute; /* 绝对定位 */
            bottom: 20px; /* 距底部20像素 */
            left: 50%; /* 水平居中 */
            transform: translateX(-50%); /* 向左偏移自身宽度的一半，实现精确居中 */
            font-size: 2rem; /* 字符大小 */
            opacity: 0.4; /* 半透明 */
            letter-spacing: 5px; /* 字符间距 */
        }
        
        /* 横幅标题样式 */
        .hero-content h1 {
            font-size: 3rem; /* 大标题字号 */
            margin-bottom: 1rem; /* 下方间距 */
            text-shadow: 2px 2px 8px rgba(0,0,0,0.4); /* 文字阴影 */
        }
        
        /* 横幅副标题样式 */
        .hero-content p {
            font-size: 1.2rem; /* 副标题字号 */
            max-width: 600px; /* 最大宽度 */
            margin: 0 auto; /* 居中 */
        }
        
        /* 主内容区域容器 */
        .container {
            max-width: 1200px; /* 最大宽度 */
            margin: 0 auto; /* 居中 */
            padding: 0 20px; /* 左右留白 */
        }
        
        /* 各个内容区块通用样式 */
        .section {
            background: white; /* 白色背景 */
            margin-bottom: 2rem; /* 区块下方间距 */
            padding: 2rem; /* 内边距 */
            border-radius: 12px; /* 圆角 */
            box-shadow: 0 4px 20px rgba(0,0,0,0.08); /* 轻柔的卡片阴影 */
            transition: transform 0.3s; /* 位移过渡效果 */
        }
        
        /* 区块悬停时微微上浮 */
        .section:hover {
            transform: translateY(-3px); /* 向上移动3像素 */
        }
        
        /* 区块标题样式 */
        .section h2 {
            color: #0077b6; /* 海洋蓝色 */
            margin-bottom: 1.5rem; /* 下方间距 */
            border-bottom: 3px solid #00b4d8; /* 底部蓝色边框 */
            padding-bottom: 0.5rem; /* 文字与边框的间距 */
            display: inline-block; /* 行内块元素，让边框只包裹文字 */
        }
        
        /* 设施卡片网格布局 */
        .facilities-grid {
            display: grid; /* 网格布局 */
            grid-template-columns: repeat(auto-fit, minmax(220px, 1fr)); /* 自适应列数 */
            gap: 1.5rem; /* 网格间距 */
            margin-top: 1.5rem; /* 上方间距 */
        }
        
        /* 单个设施卡片样式 */
        .facility-card {
            background: #f0f8ff; /* 爱丽丝蓝背景 */
            padding: 1.5rem; /* 内边距 */
            border-radius: 10px; /* 圆角 */
            border-left: 4px solid #0077b6; /* 左侧蓝色装饰线 */
            text-align: center; /* 文字居中 */
            transition: all 0.3s; /* 所有属性过渡 */
        }
        
        /* 设施卡片悬停效果 */
        .facility-card:hover {
            background: #e0f0ff; /* 背景变深 */
            box-shadow: 0 4px 15px rgba(0,119,182,0.2); /* 蓝色阴影 */
        }
        
        /* 设施卡片内的图标样式 */
        .facility-icon {
            font-size: 2.5rem; /* 图标放大 */
            margin-bottom: 0.8rem; /* 下方间距 */
        }
        
        /* 设施卡片标题 */
        .facility-card h3 {
            color: #0077b6; /* 蓝色标题 */
            margin-bottom: 0.5rem; /* 下方间距 */
            font-size: 1.1rem; /* 字号 */
        }
        
        /* 设施卡片描述文字 */
        .facility-card p {
            font-size: 0.9rem; /* 稍小字号 */
            color: #555; /* 灰色文字 */
        }
        
        /* 课程和票价表格样式 */
        .info-table {
            width: 100%; /* 表格占满容器 */
            border-collapse: collapse; /* 合并边框 */
            margin-top: 1rem; /* 上方间距 */
        }
        
        /* 表格单元格样式 */
        .info-table th, .info-table td {
            border: 1px solid #ddd; /* 浅灰色边框 */
            padding: 12px 15px; /* 内边距 */
            text-align: center; /* 文字居中 */
        }
        
        /* 表格头部样式 */
        .info-table th {
            background: #0077b6; /* 蓝色背景 */
            color: white; /* 白色文字 */
            font-weight: bold; /* 加粗 */
        }
        
        /* 表格偶数行背景色，形成斑马纹 */
        .info-table tr:nth-child(even) {
            background: #f0f8ff; /* 浅蓝色背景 */
        }
        
        /* 表格行悬停效果 */
        .info-table tr:hover {
            background: #d4e6ff; /* 悬停时背景加深 */
        }
        
        /* 注意事项列表样式 */
        .notice-list {
            list-style: none; /* 去掉默认圆点 */
            padding-left: 0; /* 去掉默认缩进 */
        }
        
        /* 注意事项每一项 */
        .notice-list li {
            background: #fff8e1; /* 浅黄色背景 */
            margin-bottom: 8px; /* 项与项之间间距 */
            padding: 12px 15px; /* 内边距 */
            border-radius: 6px; /* 圆角 */
            border-left: 4px solid #ff9800; /* 左侧橙色装饰线 */
            font-size: 0.95rem; /* 字号 */
        }
        
        /* 地图容器样式 */
        .map-container {
            width: 100%; /* 宽度占满 */
            margin-top: 1rem; /* 上方间距 */
            border-radius: 10px; /* 圆角 */
            overflow: hidden; /* 隐藏溢出，让圆角生效 */
            border: 2px solid #00b4d8; /* 蓝色边框 */
        }
        
        /* 地图iframe样式 */
        .map-container iframe {
            width: 100%; /* 宽度占满 */
            height: 300px; /* 高度300像素 */
            border: none; /* 去掉边框 */
            display: block; /* 块级元素，消除底部空隙 */
        }
        
        /* 页脚样式 */
        .footer {
            background: #023e8a; /* 深蓝色背景 */
            color: white; /* 白色文字 */
            text-align: center; /* 文字居中 */
            padding: 1.5rem 0; /* 上下内边距 */
            margin-top: 2rem; /* 上方间距 */
            font-size: 0.9rem; /* 字号 */
        }
        
        /* 手机屏幕响应式调整 */
        @media (max-width: 768px) {
            .header-content {
                flex-direction: column; /* 纵向排列 */
                text-align: center; /* 居中 */
            }
            
            .nav ul {
                margin-top: 0.8rem; /* 上方间距 */
                flex-wrap: wrap; /* 允许换行 */
                justify-content: center; /* 居中 */
            }
            
            .nav ul li {
                margin: 5px 8px; /* 缩小间距 */
            }
            
            .hero {
                height: 40vh; /* 手机端高度减小 */
            }
            
            .hero-content h1 {
                font-size: 2rem; /* 缩小字号 */
            }
            
            .hero-content p {
                font-size: 1rem; /* 缩小字号 */
            }
            
            .table-wrapper {
                overflow-x: auto; /* 横向溢出时出现滚动条 */
            }
        }
    </style>
</head>
<body>
    <!-- ==================== 头部导航栏（图片背景） ==================== -->
    <header class="header">
        <div class="header-content">
            <div class="logo">
                🏊 沙市<span>里约游泳馆</span>
            </div>
            <nav class="nav">
                <ul>
                    <li><a href="#home">首页</a></li>
                    <li><a href="#about">场馆简介</a></li>
                    <li><a href="#facilities">设施服务</a></li>
                    <li><a href="#price">票价课程</a></li>
                    <li><a href="#contact">联系方式</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <!-- ==================== 首页横幅 ==================== -->
    <section id="home" class="hero">
        <div class="hero-content">
            <h1>沙市里约游泳馆</h1>
            <p>荆州本地专业游泳健身场所 | 四季恒温 | 专业教练团队</p>
        </div>
    </section>

    <!-- ==================== 主内容区域 ==================== -->
    <main class="container">
        
        <!-- 场馆简介区块 -->
        <section id="about" class="section">
            <h2>📍 场馆简介</h2>
            <p><strong>沙市里约游泳馆</strong>位于湖北省荆州市沙市区<strong>职工文化活动中心</strong>内，是本地知名的室内恒温游泳馆。场馆以“里约”命名，传递热情、活力、健康的运动理念，致力于为沙市及周边居民提供安全、舒适、专业的游泳环境。</p>
            <p>场馆拥有<strong>标准半标泳池</strong>，水温常年保持在<strong>26℃-28℃</strong>，采用先进的水循环过滤系统，水质清澈卫生。馆内配备专业救生员团队和完善的更衣淋浴设施。</p>
            <p style="margin-top: 10px;">📍 <strong>地址：</strong>湖北省荆州市沙市区职工文化活动中心</p>
        </section>

        <!-- 设施服务区块 -->
        <section id="facilities" class="section">
            <h2>🏟️ 设施与服务</h2>
            <div class="facilities-grid">
                <div class="facility-card">
                    <div class="facility-icon">🏊‍♂️</div>
                    <h3>室内恒温泳池</h3>
                    <p>25米标准半标池，水温恒定26-28℃，全年开放不受天气影响。</p>
                </div>
                
                <div class="facility-card">
                    <div class="facility-icon">👶</div>
                    <h3>儿童戏水池</h3>
                    <p>专为儿童设计的浅水区，水深0.5-0.8米，水温适宜，安全有趣。</p>
                </div>
                
                <div class="facility-card">
                    <div class="facility-icon">🚿</div>
                    <h3>更衣淋浴室</h3>
                    <p>男女分区独立更衣室，配备热水淋浴、储物柜，干净整洁。</p>
                </div>
                
                <div class="facility-card">
                    <div class="facility-icon">🛟</div>
                    <h3>专业救生团队</h3>
                    <p>持证救生员全场巡视，保障每位泳客的安全，让您游得放心。</p>
                </div>
                
                <div class="facility-card">
                    <div class="facility-icon">🎓</div>
                    <h3>游泳培训课程</h3>
                    <p>开设成人班、儿童班、私教课，教练持证上岗，包教包会。</p>
                </div>
                
                <div class="facility-card">
                    <div class="facility-icon">🅿️</div>
                    <h3>免费停车位</h3>
                    <p>场馆门前设有免费停车位，方便驾车前来锻炼的顾客。</p>
                </div>
            </div>
        </section>

        <!-- 票价与课程区块 -->
        <section id="price" class="section">
            <h2>💰 票价与课程</h2>
            <div class="table-wrapper">
                <table class="info-table">
                    <thead>
                        <tr>
                            <th>项目</th>
                            <th>价格</th>
                            <th>说明</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>单次游泳票</td>
                            <td>¥35/次</td>
                            <td>不限时，含淋浴</td>
                        </tr>
                        <tr>
                            <td>10次次卡</td>
                            <td>¥300</td>
                            <td>有效期3个月，可多人使用</td>
                        </tr>
                        <tr>
                            <td>月卡</td>
                            <td>¥260</td>
                            <td>30天有效，仅限本人使用</td>
                        </tr>
                        <tr>
                            <td>季卡</td>
                            <td>¥680</td>
                            <td>90天有效，仅限本人使用</td>
                        </tr>
                        <tr>
                            <td>年卡</td>
                            <td>¥1880</td>
                            <td>365天有效，赠送私教课一节</td>
                        </tr>
                        <tr>
                            <td>儿童一对一私教</td>
                            <td>¥1200/10节</td>
                            <td>包教包会，6岁以上可报名</td>
                        </tr>
                        <tr>
                            <td>成人一对一私教</td>
                            <td>¥1500/10节</td>
                            <td>零基础教学，时间灵活预约</td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </section>

        <!-- 入馆须知区块 -->
        <section id="notice" class="section">
            <h2>📋 入馆须知</h2>
            <ul class="notice-list">
                <li>🩱 入池必须穿着泳衣、佩戴泳帽，否则谢绝下水。</li>
                <li>🕐 开放时间：<strong>夏季 09:00-21:00</strong>，<strong>冬季 10:00-20:30</strong>，节假日另行通知。</li>
                <li>🩴 请自备拖鞋、浴巾等个人用品，馆内也有售卖。</li>
                <li>🚫 酒后、皮肤病、心脏病等患者谢绝入池，安全第一。</li>
                <li>👧 1.3米以下儿童须由家长全程陪同入场。</li>
                <li>📱 泳池区域请勿使用手机拍照，保护他人隐私。</li>
            </ul>
        </section>

        <!-- 联系方式区块 -->
        <section id="contact" class="section">
            <h2>📞 联系方式</h2>
            <p><strong>📞 联系电话：</strong>0716-XXXXXXX（示例号码，请替换为真实号码）</p>
            <p><strong>📱 微信咨询：</strong>shashi_rio_swim（示例微信号）</p>
            <p><strong>📍 场馆地址：</strong>湖北省荆州市沙市区职工文化活动中心</p>
            
            <!-- ==================== 高德地图嵌入区域（已更新为你分享的精准坐标） ==================== -->
            <div class="map-container">
                <iframe 
                    src="https://uri.amap.com/marker?position=112.255329,30.318942&name=沙市里约游泳馆(职工文化活动中心)&callnative=1" 
                    frameborder="0">
                </iframe>
            </div>
            <!-- ==================== 地图区域结束 ==================== -->
            <p style="margin-top: 8px; font-size: 0.85rem; color: #888; text-align: center;">📱 点击地图可跳转至高德地图进行实时导航</p>
        </section>

    </main>

    <!-- ==================== 页脚 ==================== -->
    <footer class="footer">
        <p>&copy; 2024 沙市里约游泳馆 | 健康生活，从这里开始</p>
        <p style="margin-top: 5px; opacity: 0.7;">本站为示例展示页面，信息请以场馆实际公告为准</p>
    </footer>
</body>
</html>
