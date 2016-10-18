# Application Lifecycle

The states in the lifecycle of a LibGDX application are

* create
* resize
* render
* pause
* resume
* dispose

These lifecycle events are represented in the *ApplicationListener* interface (https://libgdx.badlogicgames.com/nightlies/docs/api/com/badlogic/gdx/ApplicationListener.html)

```java
public interface ApplicationListener {
  public void create();
  public void resize(int width, int height);
  public void render();
  public void pause();
  public void resume();
  public void dispose();
}
```

A LibGDX application has to implement this interface to allow LibGDX to call the necessary methods when the corresponding events occur. 




