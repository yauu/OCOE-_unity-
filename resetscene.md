# 【OCOE筆記】ResetScene重新初始化同一場景

## 重製場景

 

```
public void ResetScene()
  {
    SceneManager.LoadScene(SceneManager.GetActiveScene().buildIndex);
  }
```

