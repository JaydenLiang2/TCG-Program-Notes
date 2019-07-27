# TCG Program-笔记

- First review at 27/7/2019





## 各个文件的作用

| 文件名       | 作用                             |
| ------------ | -------------------------------- |
| main.cc      | 调用各功能                       |
| hv_matrix.cc | H、V图数据结构定义               |
| f_plan.cc    | 布线数据结构基类                 |
| save_out.cc  | 写入执行文件                     |
| top_sort.cc  | 排序                             |
| clo_red.cc   | 功能类，对布局方法进行定义和操作 |



## main()

***程序的主要运行方式，包括输入当前布局，然后调用相关功能完成基于TCG的布局优化并计算出面积和线长***

- **库函数用法** 

  - atoi：将字符串里的数字字符转化为整形数。返回整形值。
  - atof：把字符串转换成浮点数，直至遇到第一个空格。

- **调用的类**

  - clo_Red_Graph：布线
  - time_t：

- **关键变量** 

  - times：次数
  - hill_climb_stage：爬坡率
  - avg_ratio：覆盖率

- **Simulated Annealing B*Tree Floorplanning函数** 

  即void SA_Floorplanning(Clo_Red_Graph &fp,float P,float r,float Term_T, float conv_rate,int k, char mode) 

  - P: probability to accept in avg. delta cost (0~1)
  - r: temperature decreasing rate (0~1)
  - t: terminating temperature
  - conv_rate: converge condition which is maximal fail rate (0~1)
  - k: factor of the number of permutation in one temperature