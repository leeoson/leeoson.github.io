<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Gridea</title>
    <meta name="description" content="leeoson_blog">
    <link rel="shortcut icon" href="http://localhost:4000/media/images/eduifuns.png">
    <link rel="stylesheet" href="//fonts.loli.net/css?family=Arimo:400,700,400italic">
    <link rel="stylesheet" href="http://localhost:4000/media/css/icomoon.css">
    <link rel="stylesheet" href="http://localhost:4000/media/css/main.css?v=1650618437852">
  </head>

<body class="page-body">
    <!-- skin-white -->
    <div class="page-container">
        <div class="sidebar-menu toggle-others fixed">
            <div class="sidebar-menu-inner">
                <header class="logo-env">
                    <!-- logo -->
                    <div class="logo">
                        <a href="http://localhost:4000" class="logo-expanded">
                            <img src="http://localhost:4000/images/avatar.png"  style="height:68px" alt="" />
                        </a>
                        <a href="http://localhost:4000" class="logo-collapsed">
                            <img src="http://localhost:4000/media/images/eduifuns.png" width="40" alt="" />
                        </a>
                    </div>
                    <div class="mobile-menu-toggle visible-xs">
                        <a href="#" data-toggle="mobile-menu">
                            <i class="icon-bar"></i>
                        </a>
                    </div>
                </header>
                <ul id="main-menu" class="main-menu">
                    <!-- li 加 has-sub 开启分组-->
                    <li class="has-sub">
                        <a>
                            <i class="icon-globe"></i>
                            <span class="title">在线工具</span>
                        </a>
                        <!-- ul li 格式添加子分组-->
                        <ul>
                            <li>
                                <a href="#教学助手" class="smooth">
                                    <i class="icon-star"></i>
                                    <span class="title">教学助手</span>
                                </a>
                            </li>
                            <li>
                                <a href="#图文影音" class="smooth">
                                    <i class="icon-pencil"></i>
                                    <span class="title">图文影音</span>
                                </a>
                            </li>
                            <li>
                                <a href="#百科全书" class="smooth">
                                    <i class="icon-database"></i>
                                    <span class="title">百科全书</span>
                                </a>
                            </li>
                        </ul>
                    </li>
                    
                    
                    
                    <li class="submit-tag">
                        <a href="http://localhost:4000/about">
                            <i class="icon-heart"></i>
                            <span class="title">关于本站</span>
                        </a>
                    </li>
                </ul>
            </div>
        </div>
        <div class="main-content">
            <nav class="navbar user-info-navbar" role="navigation">
                <!-- User Info, Notifications and Menu Bar -->
                <!-- Left links for user info navbar -->
                <ul class="user-info-menu left-links list-inline list-unstyled">
                    <li class="hidden-sm hidden-xs">
                        <a href="#" data-toggle="sidebar">
                            <i class="icon-bar"></i>
                        </a>
                    </li>
                </ul>
            </nav>

            <!-- 今日诗词 -->
            <div id="poem_content">
                <h3 id="poem_sentence"></h3><span id="poem_info"></span>
            </div>
            <!-- 今日诗词 -->
            <br />
            <!-- 在线工具 -->
            
            
            
            <!-- END 在线工具 -->

            <!-- 实用软件 -->
            
            <!-- END 实用软件 -->

            <!-- 线上课程 -->
            
            <!-- END 线上课程 -->

            <!-- 素材资源 -->
            
            <!-- END 素材资源 -->


            <!-- Main Footer -->
            <!-- Choose between footer styles: "footer-type-1" or "footer-type-2" -->
            <!-- Add class "sticky" to  always stick the footer to the end of page (if page contents is small) -->
            <!-- Or class "fixed" to  always fix the footer to the end of page -->
            <footer class="main-footer sticky footer-type-1">
                <div class="footer-inner">
                    <!-- Add your copyright text here -->
                    <div class="footer-text">
                        Powered by <a href="https://github.com/getgridea/gridea" target="_blank">Gridea</a> <span id="busuanzi_container_site_pv" style='display:none'>总访问量<span id="busuanzi_value_site_pv"></span>次</span>
                    </div>
                    <div class="go-up">
                        <a href="#" rel="go-top">
                            <i class="icon-up"></i>
                        </a>
                    </div>
                </div>
            </footer>
        </div>
    </div>


    <script src="https://sdk.jinrishici.com/v2/browser/jinrishici.js" charset="utf-8"></script>
    <script type="text/javascript">
    jinrishici.load(function(result) {
        var sentence = document.querySelector("#poem_sentence")
        var info = document.querySelector("#poem_info")
        sentence.innerHTML = result.data.content
        info.innerHTML = '【' + result.data.origin.dynasty + '】' + result.data.origin.author + '《' + result.data.origin.title + '》'
    });
    </script>
    <script async src="//busuanzi.ibruce.info/busuanzi/2.3/busuanzi.pure.mini.js"></script>

    <script src="//cdnjs.loli.net/ajax/libs/jquery/1.11.1/jquery.min.js"></script>
    <!-- 锚点平滑移动 -->
    <script type="text/javascript">
    $(document).ready(function() {
         //img lazy loaded
         const observer = lozad();
         observer.observe();

        $(document).on('click', '.has-sub', function(){
            var _this = $(this)
            if(!$(this).hasClass('expanded')) {
               setTimeout(function(){
                    _this.find('ul').attr("style","")
               }, 300);
              
            } else {
                $('.has-sub ul').each(function(id,ele){
                    var _that = $(this)
                    if(_this.find('ul')[0] != ele) {
                        setTimeout(function(){
                            _that.attr("style","")
                        }, 300);
                    }
                })
            }
        })
        $('.user-info-menu .hidden-sm').click(function(){
            if($('.sidebar-menu').hasClass('collapsed')) {
                $('.has-sub.expanded > ul').attr("style","")
            } else {
                $('.has-sub.expanded > ul').show()
            }
        })
        $("#main-menu li ul li").click(function() {
            $(this).siblings('li').removeClass('active'); // 删除其他兄弟元素的样式
            $(this).addClass('active'); // 添加当前元素的样式
        });
        $("a.smooth").click(function(ev) {
            ev.preventDefault();

            public_vars.$mainMenu.add(public_vars.$sidebarProfile).toggleClass('mobile-is-visible');
            ps_destroy();
            $("html, body").animate({
                scrollTop: $($(this).attr("href")).offset().top - 30
            }, {
                duration: 500,
                easing: "swing"
            });
        });
        return false;
    });

    var href = "";
    var pos = 0;
    $("a.smooth").click(function(e) {
        $("#main-menu li").each(function() {
            $(this).removeClass("active");
        });
        $(this).parent("li").addClass("active");
        e.preventDefault();
        href = $(this).attr("href");
        pos = $(href).position().top - 30;
    });
    </script>
    <!-- Bottom Scripts -->
    <script src="http://localhost:4000/media/js/bootstrap.min.js"></script>
    <script src="http://localhost:4000/media/js/TweenMax.min.js"></script>
    <script src="http://localhost:4000/media/js/resizeable.js"></script>
    <script src="http://localhost:4000/media/js/xenon-toggles.js"></script>
    <script src="http://localhost:4000/media/js/xenon-custom.js"></script>
    <script src="http://localhost:4000/media/js/lozad.js"></script>
    <script src="http://localhost:4000/media/js/LetterAvatar.js"></script>
</body>



</html>
Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/leeoson/leeoson.github.io/settings/pages). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.
