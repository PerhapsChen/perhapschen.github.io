# Technical Blog

---



# Notebook to HTML file

**convert `.ipynb` file as `HTML` file.**

```bash
jupyter nbconvert --to html ./foobar.ipynb
```

The following formats are available: 

```bash
['asciidoc', 'custom', 'html', 'latex', 'markdown', 'notebook', 'pdf', 'python', 'qtpdf', 'qtpng', 'rst', 'script', 'slides', 'webpdf']   
```

In the HTML file, we can modify `jp-code-font-size` to change font size of codes.

---



# VSCode remote-ssh 免密

参考: [配置vscode 远程开发+ 免密登录 - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/222452460)

---



# 使用format参数加速pd.to_datetime转换

`pd.to_datetime` 会自己检测用了哪种格式，这种检测需要花费大量时间，可以给定固定格式进而加速。

```python
df.index=pd.to_datetime(df.index,format='%Y-%m-%d %H:%M:%S.%f')
```

