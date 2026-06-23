<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <!-- 移动端适配核心标签 -->
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>琚在熙 - 个人简历官网</title>
    <style>
        /* 全局重置 */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: "Microsoft YaHei", sans-serif;
        }
        html {
            scroll-behavior: smooth;
        }
        body {
            background-color: #f5f7fa;
            color: #333;
            line-height: 1.6;
        }
        ul {
            list-style: none;
        }
        a {
            text-decoration: none;
            color: inherit;
        }

        /* 导航栏 */
        header {
            position: fixed;
            top: 0;
            width: 100%;
            background: #2c3e50;
            color: #fff;
            z-index: 999;
            box-shadow: 0 2px 10px rgba(0,0,0,0.15);
        }
        .nav-container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            height: 60px;
        }
        .logo {
            font-size: 22px;
            font-weight: bold;
        }
        /* 桌面端导航 */
        .nav-list {
            display: flex;
            gap: 30px;
        }
        .nav-list li a {
            padding: 8px 0;
            position: relative;
            transition: color 0.3s;
        }
        .nav-list li a:hover {
            color: #3498db;
        }
        .nav-list li a::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 0;
            height: 2px;
            background: #3498db;
            transition: width 0.3s;
        }
        .nav-list li a:hover::after {
            width: 100%;
        }
        /* 移动端汉堡按钮 */
        .menu-btn {
            display: none;
            font-size: 26px;
            cursor: pointer;
        }

        /* 主体容器 */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
            padding-top: 80px;
        }
        section {
            background: #fff;
            border-radius: 12px;
            padding: 40px 30px;
            margin-bottom: 30px;
            box-shadow: 0 3px 15px rgba(0,0,0,0.06);
        }
        .section-title {
            font-size: 26px;
            color: #2c3e50;
            margin-bottom: 25px;
            padding-bottom: 10px;
            border-bottom: 3px solid #3498db;
            display: inline-block;
        }

        /* 个人简介头部 */
        .about-wrap {
            display: flex;
            flex-wrap: wrap;
            gap: 35px;
            align-items: center;
        }
        .avatar-box {
            width: 160px;
            height: 160px;
            border-radius: 50%;
            background: linear-gradient(135deg, #3498db, #2ecc71);
            display: flex;
            align-items: center;
            justify-content: center;
            color: #fff;
            font-size: 50px;
            font-weight: bold;
            flex-shrink: 0;
        }
        .info-text h2 {
            font-size: 32px;
            color: #2c3e50;
            margin-bottom: 10px;
        }
        .info-text p {
            font-size: 17px;
            margin: 8px 0;
            color: #555;
        }
        .info-text p span {
            font-weight: bold;
            color: #2c3e50;
            min-width: 100px;
            display: inline-block;
        }

        /* 教育板块 */
        .edu-item {
            border-left: 4px solid #3498db;
            padding-left: 20px;
            margin-bottom: 20px;
        }
        .edu-item h3 {
            font-size: 20px;
            color: #2c3e50;
        }
        .edu-item .time {
            color: #777;
            margin: 6px 0;
        }

        /* 技能板块 */
        .skill-wrap {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
            gap: 20px;
        }
        .skill-card {
            background: #f8fafc;
            padding: 20px;
            border-radius: 8px;
            border-left: 4px solid #2ecc71;
        }
        .skill-card h4 {
            margin-bottom: 10px;
            color: #2c3e50;
        }

        /* 项目经历 */
        .project-item {
            margin-bottom: 25px;
            padding-bottom: 20px;
            border-bottom: 1px dashed #ddd;
        }
        .project-item:last-child {
            border-bottom: none;
        }
        .project-item h3 {
            color: #3498db;
            margin-bottom: 8px;
        }

        /* 联系表单 */
        .contact-form {
            max-width: 700px;
        }
        .form-row {
            margin-bottom: 18px;
        }
        .form-row label {
            display: block;
            margin-bottom: 6px;
            font-weight: 500;
        }
        .form-row input, .form-row textarea {
            width: 100%;
            padding: 12px 15px;
            border: 1px solid #ddd;
            border-radius: 6px;
            font-size: 16px;
            transition: border 0.3s;
        }
        .form-row input:focus, .form-row textarea:focus {
            outline: none;
            border-color: #3498db;
        }
        textarea {
            min-height: 120px;
            resize: vertical;
        }
        .submit-btn {
            background: #3498db;
            color: #fff;
            border: none;
            padding: 13px 35px;
            border-radius: 6px;
            font-size: 17px;
            cursor: pointer;
            transition: background 0.3s;
        }
        .submit-btn:hover {
            background: #2980b9;
        }
        .contact-info {
            margin-top: 30px;
            padding-top: 20px;
            border-top: 1px solid #eee;
        }
        .contact-info p {
            margin: 10px 0;
            font-size: 17px;
        }

        /* 页脚 */
        footer {
            text-align: center;
            padding: 25px;
            color: #777;
            font-size: 15px;
        }

        /* 响应式手机适配 */
        @media screen and (max-width: 768px) {
            .nav-list {
                position: absolute;
                top: 60px;
                left: 0;
                width: 100%;
                background: #2c3e50;
                flex-direction: column;
                padding: 20px;
                gap: 18px;
                display: none;
            }
            .nav-list.show {
                display: flex;
            }
            .menu-btn {
                display: block;
            }
            .about-wrap {
                justify-content: center;
                text-align: center;
            }
            .avatar-box {
                margin: 0 auto;
            }
            .info-text h2 {
                font-size: 26px;
            }
            section {
                padding: 25px 20px;
            }
            .section-title {
                font-size: 22px;
            }
        }
    </style>
</head>
<body>
    <!-- 导航栏 -->
    <header>
        <div class="nav-container">
            <div class="logo">琚在熙 | 个人简历</div>
            <ul class="nav-list" id="navList">
                <li><a href="#about">个人简介</a></li>
                <li><a href="#edu">教育信息</a></li>
                <li><a href="#skill">专业技能</a></li>
                <li><a href="#project">项目经历</a></li>
                <li><a href="#contact">联系方式</a></li>
            </ul>
            <div class="menu-btn" id="menuBtn">☰</div>
        </div>
    </header>

    <div class="container">
        <!-- 个人简介 -->
        <section id="about">
            <h2 class="section-title">个人简介</h2>
            <div class="about-wrap">
                <div class="avatar-box">琚</div>
                <div class="info-text">
                    <h2>琚在熙</h2>
                    <p><span>学号：</span>2025381050</p>
                    <p><span>求职方向：</span>前端开发 / Web开发工程师</p>
                    <p><span>自我介绍：</span>热爱Web前端开发，熟练掌握HTML、CSS、JavaScript等基础技术，具备响应式页面开发能力，善于编写整洁、易维护的代码；学习能力强，乐于接受新技术，注重用户交互体验。</p>
                </div>
            </div>
        </section>

        <!-- 教育信息 -->
        <section id="edu">
            <h2 class="section-title">教育信息</h2>
            <div class="edu-item">
                <h3>XX大学 | 计算机科学与技术</h3>
                <p class="time">在读时间：2025年09月 - 至今</p>
                <p>在校学号：2025381050，主修课程：Web前端开发、计算机网络、数据结构、数据库原理、UI交互设计</p>
            </div>
        </section>

        <!-- 专业技能 -->
        <section id="skill">
            <h2 class="section-title">专业技能</h2>
            <div class="skill-wrap">
                <div class="skill-card">
                    <h4>前端基础</h4>
                    <p>HTML5 / CSS3 / 原生JavaScript</p>
                    <p>Flex、Grid响应式布局</p>
                </div>
                <div class="skill-card">
                    <h4>工具与框架</h4>
                    <p>VS Code、Git、Chrome调试</p>
                    <p>简单jQuery、Bootstrap</p>
                </div>
                <div class="skill-card">
                    <h4>其他能力</h4>
                    <p>基础MySQL数据库</p>
                    <p>图片切图、简单UI还原</p>
                </div>
                <div class="skill-card">
                    <h4>软技能</h4>
                    <p>团队协作、文档编写</p>
                    <p>自主学习、问题排查</p>
                </div>
            </div>
        </section>

        <!-- 项目经历 -->
        <section id="project">
            <h2 class="section-title">项目经历</h2>
            <div class="project-item">
                <h3>响应式个人简历网站（本网站）</h3>
                <p><strong>技术栈：</strong>HTML + CSS + 原生JavaScript</p>
                <p><strong>项目描述：</strong>独立开发个人简历展示官网，实现电脑/手机双端自适应；完成导航栏移动端折叠菜单、平滑滚动、表单交互；页面分层模块化，代码结构清晰，使用弹性布局与网格布局适配不同屏幕尺寸。</p>
            </div>
            <div class="project-item">
                <h3>校园新闻静态展示页面</h3>
                <p><strong>技术栈：</strong>HTML5、CSS3、JS</p>
                <p><strong>项目描述：</strong>制作校园资讯展示页，实现轮播图、新闻列表分页模拟、hover动态效果；兼容移动端，优化图片加载与页面排版。</p>
            </div>
        </section>

        <!-- 联系方式板块 -->
        <section id="contact">
            <h2 class="section-title">联系方式</h2>
            <!-- 留言表单 -->
            <form class="contact-form" id="contactForm">
                <div class="form-row">
                    <label for="name">您的姓名</label>
                    <input type="text" id="name" placeholder="请输入姓名" required>
                </div>
                <div class="form-row">
                    <label for="email">联系邮箱</label>
                    <input type="email" id="email" placeholder="请输入邮箱" required>
                </div>
                <div class="form-row">
                    <label for="msg">留言内容</label>
                    <textarea id="msg" placeholder="请输入留言..." required></textarea>
                </div>
                <button class="submit-btn" type="submit">提交留言</button>
            </form>
            <!-- 个人联系信息 -->
            <div class="contact-info">
                <p><strong>姓名：</strong>琚在熙</p>
                <p><strong>学号：</strong>2025381050</p>
                <p><strong>邮箱：</strong>zaixi2025@school.com（可自行修改）</p>
                <p><strong>微信：</strong>ZJX2025381050（可自行修改）</p>
            </div>
        </section>
    </div>

    <footer>
        © 2026 琚在熙 个人简历网站 | 全部代码由原生HTML+CSS+JS开发
    </footer>

    <script>
        // 1. 移动端汉堡菜单切换
        const menuBtn = document.getElementById('menuBtn');
        const navList = document.getElementById('navList');
        menuBtn.addEventListener('click', function () {
            navList.classList.toggle('show');
        });
        // 点击导航链接自动关闭移动端菜单
        const navLinks = navList.querySelectorAll('a');
        navLinks.forEach(link => {
            link.addEventListener('click', () => {
                if (window.innerWidth <= 768) {
                    navList.classList.remove('show');
                }
            })
        })

        // 2. 联系表单提交交互
        const contactForm = document.getElementById('contactForm');
        contactForm.addEventListener('submit', function (e) {
            e.preventDefault(); // 阻止默认刷新
            const userName = document.getElementById('name').value;
            const userEmail = document.getElementById('email').value;
            const userMsg = document.getElementById('msg').value;
            alert(`留言提交成功！\n姓名：${userName}\n邮箱：${userEmail}\n留言：${userMsg}`);
            contactForm.reset(); // 清空表单
        })

        // 3. 滚动时导航栏轻微变色增强视觉
        window.addEventListener('scroll', function () {
            const header = document.querySelector('header');
            if (window.scrollY > 30) {
                header.style.background = '#233140';
            } else {
                header.style.background = '#2c3e50';
            }
        })
    </script>
</body>
</html>
