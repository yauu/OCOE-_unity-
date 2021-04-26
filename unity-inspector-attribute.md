---
description: 屬性修飾
---

# 【OCOE筆記】Unity Inspector Attribute屬性附加修飾

## **Inspector**  顯示部分

* \[HideInInspector\]
  * 將 public 變數從 Inspector 上隱藏。
* \[SerializeField\]
  * 將 private 變數顯示在 Inspector 上。
  * 註：本來的用意是序列化 \(serialize\) 變數成為可在 Inspector 編輯的參數，不過 Unity 本來就會對 public 變數執行序列化，所以通常會用於強制序列化 private 變數。

```
[HideInInspector]
public int Hide;

 
[SerializeField]
private string _SerializeText;

```

## **Inspector**  修飾部分

* \[Range\(float, float\)\]
  * 限制 int 或者 float 變數的範圍，並增加一個拉桿 UI。
* \[Multiline\]
  * 讓 string 的填寫欄位變成多行。
* \[TextArea\]
  * 讓 string 的填寫欄位變成多行。
  * 註：Multiline 與 TextArea 的差別，除了顯示的介面不同之外，前者是可以設定輸入框的行數；後者則是可以設定一個範圍，讓輸入框的高度隨內容彈性調整。

```bash
[Range(0, 100)]
public int Range;
[Multiline(3)]
public string lineText;
[TextArea(3, 5)]
public string TextArea;
```

## **Inspector**  註解部分

*  * \[Header\(string\)\]
    * 顯示 Header 文字。
  * \[Tooltip\(string\)\]
    * 當滑鼠移動到參數欄位上時，會顯示說明文字。

```bash
[Header("This is Header")]
[Tooltip("This is Tooltip")]
public string Tooltip;
```

othe

## **Othe** 

* *  * \[RequireComponent \(typeof \(ComponentType\)\)\]
      * 要求同一物件必須要有指定的 Component 存在。
    * \[DisallowMultipleComponent\]
      * 限制一個物件只能擁有一個此 Component。
    * \[AddComponentMenu\(string\)\]
      * 讓自己撰寫的 Component 腳本，出現在 “Add Component" 選單中。
    * \[ExecuteInEditMode\]
      * 本來 Update\(\) 等 message 接收函式只會在 Play Mode \(遊戲執行中\) 才有動作，加上這個 Attribute 則可以在 Editor Mode \(編輯器中\) 運用 Update\(\) 等部分函式。
      * 官方文件：[https://docs.unity3d.com/ScriptReference/ExecuteInEditMode.html](https://docs.unity3d.com/ScriptReference/ExecuteInEditMode.html)

```bash
[Header("This is Header")]
[Tooltip("This is Tooltip")]
public string Tooltip
```

