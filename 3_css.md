# 在土地上种点花草美化一下

`html` 本身是一种标记语言。通过上一章学习，你可能已经制作出了一份简历。但是却感觉束手束脚，没办法施展开自己的文字排版技术。比如居中，换颜色和换字体。你还想要双列或者三列文字让字更加密集的排列。

不过这都需要基于自己看着顺眼，而不是违背自己的内心哦。

那么，接下来，我们就来学习如何在原来的 `html` 上进行润色吧！

完成这一章，我期待你至少能够将自己的简历做一定的美化。简历并不需要什么特效，所以如果想要实现特效，我建议是等到未来必要的时候再进行学习。因为会需要学习比较生涩的概念。

# 直接指定效果

接上文简历：

``` html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <header></header>
    <div>
      <h3>个人简历</h3>
      <span>姓&emsp;&emsp;名：后藤独<br/></span>
      <span>年&emsp;&emsp;龄：16 <br/></span>
      <span>籍&emsp;&emsp;贯：下北泽<br/></span>
      <span>社交账号：吉他英雄</span>
    </div>
    <footer></footer>
  </body>
</html>
```

我期望让标题个人简历居中。那么，接下来我们就需要给标签加一些属性，比如火属性能让它更烧，水属性能让它更水，土属性会像土妹子，草属性可能会引发大量生草内容。属性都会需要一个名字，而属性是什么，又需要额外规定。你可能还会想到如果有的属性只有开启和关闭。

`html` 标签是可以添加属性以做到更多效果的，在这章里，我们还会说到一种非常花哨的属性 `style`。用它你可以让自己的简历更加赛博。

那么，怎么写呢？一个属性基本是如下这种语法：

``` html
<!-- 这样字被包裹着的是是注释，不会显示在浏览器窗口里，但是可以在源码里看到 -->
<p  style="color: red;"></p>
<button disabled> 嘿嘿 </button>
```

有多种信息的，使用 `属性名称=属性内容`。如果是只有开启和关闭信息的 `bool` 值属性则是写进去是包含，没写就不包括。不过也会有一些属性是默认开启的，需要自己指明来修改展示情况。

这里，第一行是注释，仅仅用于解释程序员的想法，是特殊的标签。第二行是被指定 `style` 属性的段落标签。第三行，是一个被关闭的按钮。可以想见，只需要把 `disabled` 删除了就可以继续使用，那么到你设计的时候，你就会需要考虑在按钮 `disabled` 情况下，如何阻止用户通过修改属性点击按钮。

好，说明到此，接下来的问题就是都有什么属性。这问题是很不错，但是属性会随着版本变化而不同。有些会被抛弃，有些会被继续使用。所以属性不太能给出非常具体的简短的说明，需要查询手册。

非常推荐使用：

<https://developer.mozilla.org/zh-CN/docs/Web/HTML/Attributes>

# 今日主角 style

通过上面的例子，你会看见有一个属性，`style` 非常有趣，他可以修改颜色，而且它的使用方式也很独特，它会在内部有一个 `属性名称: 属性信息;` 的格式。（不知道是吧，这下知道了吧）

它来自于 CSS，也就是 Cascading Style Sheets，层叠样式表。名字看不懂捏，毕竟没有接触过，所以对这样的名字会有疏离感，而不像某些学过的人，他们会有非常亲切的感觉。层叠就是像被子一样一层一层的叠起来；样式就是 `style` 就是风格；表就是像表一样罗列。

它是前端最重要的黑魔法之一，你看到的非常多网页特性都是 CSS 制作出来的。很神奇吧，不需要用到 `JavaScript`，就可以做到特效。这就是 CSS 强大之处。

那么，古尔丹，代价是什么呢？非常的恼人，非常的抽象。属于精通前一直骂，精通后继续骂。但是精通后装逼非常的舒服，可以在 `b站` 录制视频，收获流量。

那么，从哪儿开始呢？这里选择自内向外进行学习。接下来将会是非常难记，但概念众多的内容。它不是必须的，但是没有它是万万不行的。

<!-- XD -->

# 回到属性

在 `html` 标签里，有些时候我们会想要给标签命名。但是，因为一些限制，我们不太想直接重命名标签，或者制造一个标签。我们可以用其他方式给他命名，比如属性 `id` 和 `class`。

这里，我个人有习惯，`id` 用于命名，而 `class` 用于标记标签属于的类。你可以形象地理解的我的习惯为，`id` 是标签的学号，`class` 是标签的班级。虽然不是很准确，但是确实是我的习惯缘由。

因此，简历就可以修改到下面这样：

``` html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <header></header>
    <div id="resume" class="a4paper">
      <h3>个人简历</h3>
      <span id="name">      姓&emsp;&emsp;名：后藤独</span><br/>
      <span id="age">       年&emsp;&emsp;龄：16</span><br/>
      <span id="hometown">  籍&emsp;&emsp;贯：下北泽</span><br/>
      <span id="social-account">社交账号：吉他英雄</span>
    </div>
    <footer></footer>
  </body>
</html>
```

可以测试发现，在浏览器的展示里没有什么变化。我们修改 `style` 属性，加一点乐趣。

``` html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <header></header>
    <div id="resume" class="a4paper" style="color: rgb(103, 65, 71);">
      <h3>个人简历</h3>
      <span id="name">      姓&emsp;&emsp;名：后藤独</span><br/>
      <span id="age">       年&emsp;&emsp;龄：16</span><br/>
      <span id="hometown">  籍&emsp;&emsp;贯：下北泽</span><br/>
      <span id="social-account">社交账号：吉他英雄</span>
    </div>
    <footer></footer>
  </body>
</html>
```

哎呀，所有字的颜色都变了。我不想让大标题变化，怎么办？两种办法，一种办法是用 `div` 包裹住四个 `span`，修改这个新 `div` 的属性。第二种办法就是直接修改标题的属性。我一般推荐第一种解决方案，但是为了展示效果，这里展示第二种方法。

``` html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <header></header>
    <div id="resume" class="a4paper" style="color: rgb(103, 65, 71);">
      <h3 style="color: rgb(36, 0, 36);">个人简历</h3>
      <span id="name">      姓&emsp;&emsp;名：后藤独</span><br/>
      <span id="age">       年&emsp;&emsp;龄：16</span><br/>
      <span id="hometown">  籍&emsp;&emsp;贯：下北泽</span><br/>
      <span id="social-account">社交账号：吉他英雄</span>
    </div>
    <footer></footer>
  </body>
</html>
```

会发现，除了自己指定的标题以外，其他内容依然保持原来的颜色。你可以理解成，内层的 `style` 对自己更加亲切，而外层的 `style` 对自己比较疏远，所以相信距离自己更近，更亲切的内层的 `style`。

实际就是距离自己越近的规则，优先级越高。这个近，体现在实际位置上，也体现在描述的具体程度上。前者在这里可以得到体现，后者则需要学习更多内容后才会有感触。

可能你已经跃跃欲试，想要给自己的个人简历上添上一抹亮色，不过记住，简历不是花里胡哨的海报，但是也需要能够捉住人的眼球。

> 我还是建议你看完下一节然后再考虑美化

你应该通过参考：

<https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Styling_text/Fundamentals>

这里进行学习，不过，从这篇文章可以看到，它使用了一个与我们改变 `style` 属性不一样的方法修改了样式。这也是我们接下来要说的内容。

# 使用 CSS

实际上，上一节我们已经在使用 CSS 的内嵌形式，你可以发现，如果要写非常长的 `style` 话，属性的值会长到无法估量。更何况你有可能需要对多个同样的项目有一样的类型，那么即便是复制粘贴，也是极难维护的。这里的难以维护意思是，如果要修改一种属性，你就需要重新手动复制一遍，还要保证不会复制出错。这是我们非常不希望的，与其花这点时间在复制上，还不如多看两眼番剧。

那么如何解决？这里我们引入一个标签块叫做 `<style>`。为了和之前的属性 `style` 作区别，这里我加了尖括号包裹。那么怎么使用呢？下面我们将上面的代码换成使用 `<style>` 的形式。

``` html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <header></header>
    <div id="resume" class="a4paper">
      <h3>个人简历</h3>
      <span id="name">      姓&emsp;&emsp;名：后藤独</span><br/>
      <span id="age">       年&emsp;&emsp;龄：16</span><br/>
      <span id="hometown">  籍&emsp;&emsp;贯：下北泽</span><br/>
      <span id="social-account">社交账号：吉他英雄</span>
    </div>
    <footer></footer>
  </body>
</html>

<style>
#resume span {
  color: rgb(103, 65, 71);
}

h3 {
  color: rgb(36, 0, 36);
}
</style>
```

糟了，这下嗝屁了，完全看不懂了。什么意思啊？也有可能我低估了大家的能力，实际上确实是在我已经这么明确表好 `id` 信息和标签以后，也可以猜到都是什么意思。

`<style>` 内的第一组属性它所适用的是在有 `id="resume"` 属性的标签下的所有 `span` 标签块都使用这个样式里的属性。而第二组属性则更加简单，就是所有的 `h3` 标签都会使用这个样式。

你可能会觉得很迷糊，或者会觉得自己的猜测中了。不过这里确实是使用了对新手比较难的样式选择。不过别担心，接下来会介绍比较简单的知识，比较难的知识会交给框架来解决，而你只需要专注于逻辑和排版即可。

`<style>` 标签内的内容就是 CSS 语言。它的语法可以理解成选择器+花括号包裹起来的属性。选择器就是在网页里挑选符合条件的标签，就是说，用于指明谁应该使用。而花括号包裹起来的部分则是一系列被选中内容应该使用的属性。

选中某种类，也就是说 `class` 中包含比如 `a4paper` 会使用 `.` 加上类的名称，例如下述代码就选中了所有类中包含 `a4paper` 的标签快：

``` html
<style>
.a4paper {
  width: 21cm;
  height: 29.7cm;
}
</style>
```

而选中 `id` 则是使用 `#`。就如 `resume` 一样。如果想要选择某种标签下的某些标签，就可以像 `#resume span` 或 `.a4paper #name` 的形式选择。

还有很多样式选择的方法，这些内容可以通过查阅手册了解：

<https://developer.mozilla.org/zh-CN/docs/Glossary/CSS_Selector>

而属性都可以通过如下网址学习：

<https://developer.mozilla.org/zh-CN/docs/Learn/CSS>

非常的多，很绝望的感觉。所以我们建议当你需要的时候去搜索，而不是直接去啃。CSS 还有很多非常有用的功能，如果要展开讲就会花费非常多的时间的空间。这里的建议是，如果对它们真的很感兴趣，就直接阅读文档。

下面是学长使用的简历模板，可以当作参考。不过，我们期望你会自己写出一份简历，这不仅对你的 `HTML + CSS` 基础内容学习很有帮助，对你未来需要简历的情况也很有帮助：

``` html
<!DOCTYPE html>
<html>
  <head>

  </head>
  <body style="margin: 0 auto; width: 21cm; font-family: 'Courier New', Courier, monospace;">
    <h1 style="text-align: center;"> 简历 </h1>
    <h2>个人信息</h2>
    <hr/>
    <table style="margin: 0 auto;">
    <tr>
      <td style="width: 4em;">姓&emsp;&emsp;名</td>
      <td>: 千反田爱瑠</td>
      <td></td>
      <td>学&emsp;&emsp;历</td>
      <td>: 本科</td>
    </tr>
    <tr>
      <td>性&emsp;&emsp;别</td>
      <td>: 女</td>
      <td></td>
      <td>就读院校</td>
      <td>: 东京大学</td>
    </tr>
    <tr>
      <td>籍&emsp;&emsp;贯</td>
      <td>: ？？</td>
      <td></td>
      <td>外&emsp;&emsp;语</td>
      <td>: 英语六级 <b>599</b></td>
    </tr>
    <tr>
      <td>年&emsp;&emsp;龄</td>
      <td>: <b>20</b>岁</td>
      <td></td>
      <td>专&emsp;&emsp;业</td>
      <td>: 计算机科学与技术</td>
    </tr>
    <tr>
      <td>联系电话</td>
      <td>: <b>???????????????</b></td>
      <td></td>
      <td>邮&emsp;&emsp;箱</td>
      <td>: <b>???????????????</b></td>
    </tr>
    <tr>
      <td>个人网站</td>
      <td>: <b>???????????????</b></td>
    </tr>
    </table>

    <h2>学习经历</h2>
    <hr/>
    <div>
      <p>
        本人现就读于东北大学计算机科学与工程学院。在校期间认真学习，目前课业上正在学习 Python 相关的人工智能课程，Verilog 搭建模型机，计算机网络，计算机组成原理，数据库等专业知识。<br/>
        本人对于 GCC 的 C 语言、Modern C++、Unix 系统编程、Makefile、CMake 等内容有所学习，并且非常热衷于相关内容。对 Windows 下编程，Win32 API、MSVC 有一定了解。
      </p>
    </div>

    <!-- <h2>科研经历</h2>
    <hr/> -->

    <!-- <h2>实习经历</h2>
    <hr/> -->

    <h2>获得荣誉</h2>
    <hr/>
    <div>
      <ul>
        <li>校一等奖学金</li>
        <li>中天二等奖学金</li>
        <li>大学生数学竞赛辽宁省一等奖</li>
        <li>校优秀学生</li>
        <li>英语六级成绩 <b>599</b> 分</li>
      </ul>
    </div>

    <h2>专业技能</h2>
    <hr/>
    <div>
      <table>
        <tr>
          <td>编程语言</td>
          <td><b>: C/C++, Python, Go, JavaScript 等</b></td>
        </tr>
        <tr>
          <td>后&emsp;&emsp;端</td>
          <td><b>: Flask, Gin, Nginx</b></td>
        </tr>
        <tr>
          <td>前&emsp;&emsp;端</td>
          <td><b>: Vue</b></td>
        </tr>
        <tr>
          <td>科学计算</td>
          <td><b>: C/C++, Python, Matlab/Octave</b></td>
        </tr>
        <tr>
          <td>硬件语言</td>
          <td><b>: Verilog</b></td>
        </tr>
        <tr>
          <td>汇编语言</td>
          <td><b>: x86</b></td>
        </tr>
      </table>
    </div>

    <h2>自我评价</h2>
    <hr/>

    <div>
      <p>
        热衷于寻找，钻研问题，更倾向于自学，当遇到毫无头绪问题时候也会向他人求助。<br/>
        对于问题喜欢刨根问底，从程序行为深入到底层代码，底层代码深入到编译原理实现以及汇编语言行为。<br/>
        非常喜欢探索问题的过程，每一次失败的尝试能够学习到更多内容，并对问题解决形成指导。喜欢阅读各种文献和文学，喜欢运动，是个乐观的人。
      </p>
    </div>
  </body>

</html>

<style>
hr {
    border: none;
    border-top: 3px solid #333;
    color: #333;
    overflow: visible;
    text-align: center;
    height: 2px;
}
</style>
```

是不是感觉很奇怪，用了非常多的表格？是的，学长早期在学 `html` 的时候还没有接触到 `html5`，所以排版的第一选择是使用表格帮忙分区。而当下，`html5` 的功能已经很强大了，我们期待你们能使用 `html5` 制作出更加优秀的简历。