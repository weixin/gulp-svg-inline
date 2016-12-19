
> 内联svg文件到css，节省一个请求并开启gzip

**NPM 官方主页:** [https://www.npmjs.com/package/gulp-svg-inline](https://www.npmjs.com/package/gulp-svg-inline)

## 安装

通过 [NPM](https://npmjs.org/) 安装*（也可使用 [CNPM](http://cnpmjs.org/) 等源）*

```javascript
npm install gulp-svg-inline --save
```

## 使用

配置 **gulpfile.js**

```javascript
var svgInline = require('gulp-svg-inline');

return gulp.src('./tmp/css/style-*.css')
.pipe(svgInline({
    maxImageSize: 1*1024*1024,
    extensions: [/.svg/ig],
}))
.pipe(postcss(postcssOption))
.pipe(gulp.dest('./tmp/css/'));
        	
```

**配置选项**  



```javascript
svgInline({
    maxImageSize: 1*1024*1024,
    extensions: [/.svg/ig],
})
```

## 效果

**CSS 输入**


```css
.svg{
	background-image:url(../icon/svg.svg);
}

```

**CSS 输出**

```css
.svg{
	background-image:url("data:image/svg+xml;charset=utf-8,%3Csvg width='51' height='52' viewBox='0 0 51 52' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Ctitle%3EGroup 6%3C/title%3E%3Cdefs%3E%3Cpath id='a' d='M.154 2.198h8.472V.476H.154z'/%3E%3Cpath id='c' d='M.07 8.541h1.8V.008H.07z'/%3E%3C/defs%3E%3Cg transform='translate(0 1);
}

```

_提示: 输出 CSS 可配合使用 SVGO POSTCSS 进一步处理_


## 参与贡献

此项目由 [TmT 团队](https://github.com/orgs/TmT/people) 创建和维护。  
如果你有 `Bug反馈` 或 `功能建议`，请创建 [Issue](https://github.com/weixin/gulp-lazyimagecss/issues) 或发送 [Pull Request](https://github.com/weixin/gulp-lazyimagecss/pulls) 给我们，感谢你的参与和贡献。