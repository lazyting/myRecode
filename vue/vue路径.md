vue项目import中出现的@  ./  ../
@:自定义
build文件夹下webpack.base.conf.js可找到@
resolve: {
    extensions: ['.js', '.vue', '.json'],
    alias: {
      'vue$': 'vue/dist/vue.esm.js',
      '@': resolve('src')
    }
  },
./: 当前目录下;
../: 父级目录;