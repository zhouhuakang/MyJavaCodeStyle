# MyJavaCodeStyle
自己工作中实际使用的java风格

##参考：

1.<https://github.com/alfred-zhong/JavaCodeSpecification>
## 命名
1.键值对中 键值名：
	
	以KEY_xxx规范命名
  例子：
  ``` java
  	public static final String KEY_DOCTOR_ID = "dr_id"
  ```
  
2.Android中资源id－－>固定为 
``` java
	int resId
``` 
	
  例子：

``` java
 	public void loadBitmap(int resId, ImageView imageView) {
    	BitmapWorkerTask task = new BitmapWorkerTask(imageView);
    	task.execute(resId);
}
```
3.生成某种对象的 方法 的命名规则  格式：toXXX();
  例子：
``` java
	Gson gson = new Gson();
	gson.toJson(1);            ==> prints 1        通过整数1生成Json对象
	gson.toJson("abcd");       ==> prints "abcd"   通过字符串“abcd”生产Json对象
```
  

