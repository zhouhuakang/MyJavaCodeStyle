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
4.与3相对应，从某种固定对象 生成其他对象的 方法 的 命名规则 格式：fromXXX();
  例子：
``` java
	int one = gson.fromJson("1", int.class);
	Integer one = gson.fromJson("1", Integer.class);
```
5.资源索引的命名规则
``` java
   颜色： 取前两位做名字的后缀   例如：颜色值  #d8d8d8  取名为 gray_d8   
```
## 方法命名

1.方法的意思是“是否＋动词＋名词”,返回值为 true 或者  false 
 方法名字格式一般为 “is+动词＋名词”,返回值类型为Boolean
``` java
	例子：pulltorefresh库中的“是否已经准备好下拉开始”方法，动词为“准备”
   	protected abstract boolean isReadyForPullStart();
```

## 注释部分

1.代码片段的分隔
利用如下注释格式
``` java
        // ===========================================================
	// xxx
	// ===========================================================
``` 
将一个java文件中的同种属性的代码分隔起来
比如：pulltorefresh库中的代码片段
``` java
	// ===========================================================
	// Constants
	// ===========================================================

	static final boolean DEBUG = true;

	static final boolean USE_HW_LAYERS = false;

	static final String LOG_TAG = "PullToRefresh";

	static final float FRICTION = 2.0f;

	public static final int SMOOTH_SCROLL_DURATION_MS = 200;
	public static final int SMOOTH_SCROLL_LONG_DURATION_MS = 325;
	static final int DEMO_SCROLL_INTERVAL = 225;

	static final String STATE_STATE = "ptr_state";
	static final String STATE_MODE = "ptr_mode";
	static final String STATE_CURRENT_MODE = "ptr_current_mode";
	static final String STATE_SCROLLING_REFRESHING_ENABLED = "ptr_disable_scrolling";
	static final String STATE_SHOW_REFRESHING_VIEW = "ptr_show_refreshing_view";
	static final String STATE_SUPER = "ptr_super";

	// ===========================================================
	// Fields
	// ===========================================================

	private int mTouchSlop;
	private float mLastMotionX, mLastMotionY;
	private float mInitialMotionX, mInitialMotionY;

	private boolean mIsBeingDragged = false;
	private State mState = State.RESET;
	private Mode mMode = Mode.getDefault();

	private Mode mCurrentMode;
	T mRefreshableView;
	private FrameLayout mRefreshableViewWrapper;
``` 
