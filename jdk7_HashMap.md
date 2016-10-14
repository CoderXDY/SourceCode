## jdk7中的源码分析 ##
### 1 基础知识 ###
##### 1.1 散列表 #####
> 解决散列表的两个问题
> + 哈希函数
> + 冲突处理
>   + 链表法
>   + 线性探测法

##### 1.2 字符串散列 #####
jdk7中的string转成hash的值的方法如下：
```Java
    public int hashCode() {
        int h = hash;
        if (h == 0 && value.length > 0) {
            char val[] = value;

            for (int i = 0; i < value.length; i++) {
                h = 31 * h + val[i];
            }
            hash = h;
        }
        return h;
    }
```
