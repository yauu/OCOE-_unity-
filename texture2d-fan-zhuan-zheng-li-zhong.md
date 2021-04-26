# texture2d翻轉 \(整理中\)

## //水平翻转图片



```text

public static Texture2D horizontalFlipPic(Texture2D texture2d)
{ 
    int width = texture2d.width; 
    int height = texture2d.height;
    Texture2D texture = new Texture2D(width, height);
    for (int i = 0; i < width; i++)
    {
        texture.SetPixels(i, 0, 1, height, texture2d.GetPixels(width - i - 1, 0, 1, height));
    } texture.Apply(); 
    return texture;
}
```



## //垂直翻转图片

```text
public static Texture2D verticalFlipPic(Texture2D texture2d)
{
    int width = texture2d.width;
    int height = texture2d.height;
    Texture2D texture = new Texture2D(width, height);
    for (int i = 0; i < height; i++)
    {
        texture.SetPixels(0, i, width, 1, texture2d.GetPixels(0, width - i - 1, width, 1));
    }
    texture.Apply();
    return texture;
}
```

