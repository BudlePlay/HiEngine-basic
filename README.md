# BWE
## BlackWindowEngine
## 검은 창 엔진

- [설명서](https://shsongs.github.io/BlackWindowEngine/)
## contributer
- [SHSongs](https://github.com/SHSongs) engine 제작
- [Hotteock3388](https://github.com/Hotteock3388) DemoGame 제작



## Example

![DemoGame GIF](https://user-images.githubusercontent.com/48788892/98504055-58cb6f00-2299-11eb-96f5-6d5adada5cfb.gif)

## 사용 방법 

### LifeCycle

Main

EngineManager

SceneManager

### SceneManager LifeCycle

Create

Render


#### How to use
```
class MyScene : public SceneManager
{
public:
    TestScene() : SceneManager()
	{
		mapPointer = new Map(30, 30);
	};

	void Create() {}

	void Resize(int x, int y) {}

	void Input(float dt) {}

	void Pause() {}
    
    ~MyScene() {}
}
```
### Object 

Constructor 

Work

#### How to use

```
class Canon : public Object
{
public:
    Canon(FPosition p, string name, string shape, Area area) : Object(p,name,shape,area) {}

    virtual void Work() {}

    virtual void OnCollision(Object* other) {}
}
```

### SceneChange
```
// TestScene.cpp
void TestScene::Render(float dt)
{
	if (Count < 0)
	{
		SceneChange(new BasicScene);		//BasicScene extend SceneManager
	}
	Count--;
}
// 향후 object에서도 사용 가능하게 개선 예정
```
